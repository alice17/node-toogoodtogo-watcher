# node-toogoodtogo-watcher [![build](https://github.com/alice17/node-toogoodtogo-watcher/workflows/Node%20Build/badge.svg)](https://github.com/alice17/node-toogoodtogo-watcher/actions)

This is a fork of the original [Too Good To Go watcher](https://github.com/marklagendijk/node-toogoodtogo-watcher/) created in order to run it on Heroku.

Node.js cli tool for monitoring your favorite TooGoodToGo businesses. Notifications are shown when the stock of any of the businesses changes. The following notification types are supported:

- Console output
- Telegram chat message
- Heroku intergration

## Installation

1. Install Node.js 8.x or higher ([Windows](https://nodejs.org/en/download/current/) | [Linux](https://github.com/nodesource/distributions#debinstall) | [OSx](https://nodejs.org/en/download/current/)).
2. `npm install -g toogoodtogo-watcher`
3. `toogoodtogo-watcher config`. Fill in your TooGoodToGo account details. Optionally enable / disable certain notifications. See [Configuring Telegram notifiations](#configuring-telegram-notifiations) for instructions on setting up the Telegram notifications.
4. `toogoodtogo-watcher watch`

## CLI documentation

```
Usage: toogoodtogo-watcher <command>

Commands:
  config        Edit the config file.
  config-reset  Reset the config to the default values.
  config-path   Show the path of the config file.
  watch         Watch your favourite busininesses for changes.

Options:
  --help     Show help                                                 [boolean]
  --version  Show version number                                       [boolean]
```

## Configuring Telegram notifications

1. Open a Telegram chat with `BotFather`.
2. Follow the instructions to create your own bot.
3. Copy the token and enter it in the configuration via `toogoodtogo-watcher config`, and set `enabled` to `true`.
4. Start the application `toogoodtogo-watcher watch`
5. Click the `t.me/BOTNAME` link from the `BotFather` chat message.
6. Press `BEGIN`.
7. Your bot should greet you, and show a notification about your favorites. Note: the bot will show the favorites which you configured. Multiple people can connect to the bot to get updates about these favorites.

## Heroku integration

Create a new app and set these Config Vars (in App > Settings):

- TELEGRAM_BOT_TOKEN
- TGTG_EMAIL
- TGTG_PASSWORD

### Test locally

Create an `.env` file and add the environment variables, then run:

```
heroku local
```

## TODO

- [ ] List favourite business command
