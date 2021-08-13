<div align="center">
<h1>Deploying slam-mirrorbot on Heroku with Github Workflows.
</h3>
</div>

## Pre-requisites

- Give stars and Fork this repo then upload **token.pickle** to your forks, or you can upload your **token.pickle** to your Index and put your **token.pickle** link to **TOKEN_PICKLE_URL** (**NOTE**: If you didn't upload **token.pickle** uploading will not work). How to generate **token.pickle**? [Read here](https://github.com/breakdowns/slam-tg-mirror-bot#getting-google-oauth-api-credential-file)
- Recommended to use 1 App in 1 Heroku accounts
- Don't use bin/fake credits card, because your Heroku account will banned

## Deployment

1. Go to Repository `Settings` -> `Secrets`

	![secrets](https://raw.githubusercontent.com/arghyac35/aria-telegram-mirror-bot/main/.github/secrets.png)

2. Add the below Required Variables one by one by clicking `New Repository Secret` everytime.

	```
	HEROKU_EMAIL
	HEROKU_API_KEY
	HEROKU_APP_NAME
	BOT_TOKEN
	TELEGRAM_API
	TELEGRAM_HASH
	OWNER_ID
	GDRIVE_FOLDER_ID
	DOWNLOAD_DIR
	DOWNLOAD_STATUS_UPDATE_INTERVAL
	AUTO_DELETE_MESSAGE_DURATION
	UPSTREAM_REPO
	UPSTREAM_BRANCH
	```

	### Description of the above Required Variables
	* `HEROKU_EMAIL` Heroku Account email Id in which the above app will be deployed
	* `HEROKU_API_KEY` Go to your Heroku account and go to Account Settings. Scroll to the bottom until you see API Key. Copy this key and add it
	* `HEROKU_APP_NAME` Your Heroku app name, Name Must be unique
	* `BOT_TOKEN` The Telegram bot token that you get from https://t.me/BotFather.
	* `TELEGRAM_API` This is to authenticate to your Telegram account for downloading Telegram files. You can get this from https://my.telegram.org DO NOT put this in quotes
	* `TELEGRAM_HASH` This is to authenticate to your Telegram account for downloading Telegram files. You can get this from https://my.telegram.org
	* `OWNER_ID` The Telegram user ID (not username) of the Owner of the bot
	* `GDRIVE_FOLDER_ID` This is the folder ID of the Google Drive Folder to which you want to upload all the mirrors
	* `DOWNLOAD_DIR` The path to the local folder where the downloads should be downloaded to
	* `DOWNLOAD_STATUS_UPDATE_INTERVAL` A short interval of time in seconds after which the Mirror progress message is updated. (I recommend to keep it `5` seconds at least)
	* `AUTO_DELETE_MESSAGE_DURATION` Interval of time (in seconds), after which the bot deletes it's message (and command message) which is expected to be viewed instantly. (**Note**: Set to `-1` to never automatically delete messages)
	* `UPSTREAM_REPO` Link for Bot Upstream Repo, if you want default update, fill `https://github.com/breakdowns/slam-tg-mirror-bot`
	* `UPSTREAM_BRANCH` Branch name for Bot Upstream Repo, fill `master`
	### For Optional Variables you can get from [Here](https://github.com/breakdowns/slam-tg-mirror-bot#setting-up-config-file) 

3. After adding all the above Required Variables go to Github Actions tab in your repo

4. Select `Manually Deploy to Heroku` workflow as shown below:

	![Example Manually Deploy to heroku](https://raw.githubusercontent.com/arghyac35/aria-telegram-mirror-bot/main/.github/manually_deploy_workflow.png)

5. Then click on Run workflow

	![Run workflow](https://raw.githubusercontent.com/arghyac35/aria-telegram-mirror-bot/main/.github/run_workflow.png)

6. _Done!_ your bot will be deployed now.

## Credits
- [arghyac35](https://github.com/arghyac35) for Tutorial