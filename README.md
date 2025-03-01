[![Build Status](https://travis-ci.org/binary-com/binary-bot.svg?branch=master)](https://travis-ci.org/binary-com/binary-bot)
[![Coverage Status](https://coveralls.io/repos/github/binary-com/binary-bot/badge.svg?branch=master)](https://coveralls.io/github/binary-com/binary-bot?branch=master)

# Binary Bot Franklin Otema

Visual automation for binary 

Binary Bot uses [Google Blockly](https://developers.google.com/blockly) to provide a puzzle like automation environment to trade using binary.com API version 3.
## Pre-installation
Ensure that your environment contains the following packages.
``` 
 - node
 - npm
 - git (for contribution)
 ```
 ## Installation

### 1. Setup the project on local machine

In order to work with Binary-Bot application, you must create your own version of this project. Please fork the project - https://github.com/binary-com/binary-bot to your git account.

You will need to perform the following on your development machine:
1. Change the current working directory to the location where you want the cloned directory.
2. Clone the forked repo using ```git clone [URL for the forked repo]```
3. Run ```cd binary-bot```
4. Create a feature branch from master -  ```git checkout -b [branchName]```.
5. Run ```npm install```

    >**Note:** - [issue with installing packages](#q1)
### 2. Configuring Hosts file
In order to run our application for the first time, you need to configure your hosts file:

If you are using a UNIX based system (Mac or Linux), Do the following:

1. Open terminal.
2. Open hosts file in your preferred text editor using ``` sudo vim /etc/hosts```.
3. Add a new entry pointing to ```127.0.0.1  localbot.binary.sx```
4. Save the file

For Windows:

 1. Run Microsoft Notepad as an administrator. 

 2. From Notepad, open the file: ```c:\Windows\System32\Drivers\etc\hosts```

 3. Add a new entry pointing to ```127.0.0.1  localbot.binary.sx```

 4. Save the file

### 3. Preparing environment variables
If you want to use *Google Drive features* in the project (**to Save/Load strategies**)
you need to create a file called `.env` at the project root with the following content:
```
GD_CLIENT_ID=GOOGLE_DRIVE_CLIENT_ID
GD_API_KEY=GOOGLE_DRIVE_API_KEY
GD_APP_ID=GOOGLE_DRIVE_APP_ID
```
Here comes useful links for more information on how to configure your project
with Google Drive integration:
- [Enabling the Google Drive API](https://developers.google.com/drive/api/v3/enable-drive-api)
- [Creating API Key](https://developers.google.com/maps/documentation/javascript/get-api-key)
- [Generating Client ID](https://developers.google.com/identity/gsi/web/guides/get-google-api-clientid)

### 4. Starting a Development Server
Make sure to set the endpoint for running the application on the localhost

 1. Run ```npm start``` on the binarybot directory. This will open the application in your default browser.
 
     >**Note:** - [Getting Permission Denied Error](#q2)

1. Now we have to set the endpoint for running the application on the localhost.
   For this, Go to ```http://localbot.binary.sx/endpoint.html```. Make sure the Server is set to ```blue.binaryws.com``` and O Auth App ID is ```16014```
   Click submit.
   
2.  Navigate to ```http://localbot.binary.sx/bot.html``` (Note that the protocol is ```http``` and not ```https```)

    >**Note:** - [Getting error "This site can’t be reached" on localhost](#q3)

3. And now you are ready with your setup.Login to the binary account using the Binary.com account credentials. Run the bot


## Pushing changes to github

1. Make your changes to the source code
2. Run test command to make sure your changes are correct
```npm run test```
3. Push your changes to your forked repo:
```
git add .
git commit -m "describe your changes"
git push origin BRANCH_NAME
```
## Deploying to local gh-pages
You can set up your GitHub Pages to deploy your repository.

1. First you need to set up custom domain. Go to ```https://github.com/YOUR_GITHUB_USERNAME/binary-bot/settings/pages``` and set your custom domain to ```YOUR_GITHUB_NAME.binary.sx```

2.  Run the command below in your project directory.
```
npm run release --branch [branchname] # can contain /
```
3. Now, your repository can be found at ```https://YOUR_CUSTOM_DOMAIN/BRANCH_NAME```
## Deployment/Release

```
gulp test-deploy # for local test deploy
npm run release --branch <branch-name> # to deploy a branch (eg., beta)
npm run release-production # to release it to production
```
## To update to latest version

```
git pull --rebase upstream master
npm install
```
## Running the CLI command

```
npm i -g binary-bot
bot -h // For a quick help
bot bot-example.js
```

### Running with a specific endpoint **Use only if you know what you're doing**

```
ENDPOINT='wss://ws.binaryws.com/websockets/v3?l=en&app_id=1169' bot bot-example.js
```

### CLI examples:
[`speed-test.js`](https://github.com/binary-com/binary-bot/blob/master/cli-examples/speed-test.js)

## Think you found a bug?
 start```

### <a name='q3'>3. Cannot access the site</a>
 Make sure to use HTTP instead of HTTPS: https://localbot.binary.sx/bot.html  => http://localbot.binary.sx/bot.html

