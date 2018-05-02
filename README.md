# slackbot-joinchannelnotifications

This bot notifies users or channels when someone joins a channel the bot is present in.  Small fork of https://github.com/nanobox-io/nanobox-slackbot, basically just adding instructions for running via docker instead.

**HEADS UP** - A Slack bot must be *invited* (`/invite @bot_name`) to a channel before it can listen for events in that channel.

## Environment Variables

The bot makes use of two environment variables:

```bash
# This is your Slack bot api token.
BOT_API_TOKEN=slackbot-api-token

# This is a space delimited list of channels|groups|usernames/id's
# which will get notified when someone joins the channel.
SUBSCRIBERS=@username #channel etc.
```

## Run the app

```bash
# clone the code
git clone https://github.com/benjaminjbachman/slackbot-joinchannelnotifications.git

# cd into the app
cd slackbot-joinchannelnotifications

# edit run.sh to add your api key and the users/channels to receive notifications
vi run.sh

# run via docker
docker run -d --restart always -it --name slackbot-joinchannelnotifications -v "$PWD":/usr/src/app -w /usr/src/app node:10 bash /usr/src/app/run.sh

```
