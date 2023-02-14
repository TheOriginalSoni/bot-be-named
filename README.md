# BBN (Bot-Be-Named)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

- [BBN (Bot-Be-Named)](#bbn-bot-be-named)
  - [What is Bot-Be-Named](#what-is-bot-be-named)
  - [How to install](#how-to-install)
  - [Current Modules](#current-modules)
  - [Acknowledgements](#acknowledgements)
  - [Contributing/Issues](#contributingissues)

## What is Bot-Be-Named

A Discord bot that interoperates with Google Sheets to smoothen solving puzzle hunts. 
If you would like to add Bot-Be-Named to your server, please contact `@kevslinger#9711` or `@Soni#3662` on discord. 

Bot-Be-Named is currently set up with our own configurations and environment variables, so might have assumptions that don't work for you. Please contact us if you need **a Bot invite link**, or to set up your own fork/instance of the bot.

## Inviting the Bot to your server

- Message `@kevslinger#9711` or `@Soni#3662` on discord to get Bot invite link.

- Use the Link and add the Bot to your discord server. Note that you need "Manage Server" permission to do that.

- Use `~about` to get a quick guide to the bot, and `~startup` for all the commands that will come in very handy for you.

- In case of any problems, message us on discord or [open a new issue on Github](https://github.com/kevslinger/bot-be-named/issues/new)

## How to install your own instance

### Prerequisites - 

- [python3.10 or newer](https://realpython.com/installing-python/)

- [Git](https://github.com/git-guides/install-git)

- [Postgresql for storing data](https://www.postgresql.org/download/)

- [Heroku CLI client for hosting](https://medium.com/analytics-vidhya/how-to-install-heroku-cli-in-windows-pc-e3cf9750b4ae)

- [Pip package installer for Python](https://phoenixnap.com/kb/install-pip-windows)

Note that you may use another Python installer (instead of Pip), Host (instead of Heroku) or Database (instead of Postgresql) but that will require you figuring out the required setup and configuation changes yourself.

### Installation

We recommend using [virtual environments](https://docs.python.org/3/tutorial/venv.html) to manage python packages for our repo. To clone the repo and install dependencies, run the following on the Command Line

```bash
#Clone the bot locally
git clone https://github.com/kevslinger/bot-be-named.git
cd bot-be-named
virtualenv venv -p=3.10 
#Technically optional, but using virtualenv is usually a good idea
pip install -r requirements.txt && pre-commit install
#This installs all the python dependancies the bot needs
```

The bot uses [Heroku Postgres](https://www.heroku.com/postgres) for storing data.

To run the bot locally, you will need a `.env` file which is used by [python-dotenv](https://github.com/theskumar/python-dotenv) to load `ENV` variables. Copy `.env.template` into `.env` with  

```bash
cp .env.template .env
```

and fill in the blanks in order to get the bot running. You also need to set up the Postgresql database for the bot using Heroku's PostgresSQL add-on (To be finished). First [install the add-on](https://elements.heroku.com/addons/heroku-postgresql) then [set it up](https://devcenter.heroku.com/articles/heroku-postgresql) to attach your app to the Postgres. Now you can look at `Heroku - Dashboard - Resources - Add Ons` to look at the app on Heroku, and copy the URI given from Postgres add-on to the respective line in the `.env file`

Once you do all that, run


```bash
source venv/bin/activate
python bot.py
```

and the bot will run on the supplied discord token's account.

### Hosting

Once you have the bot running and basic commands (like `~help`) run properly, you can host it externally. Our instance of the bot is [hosted on Heroku](https://medium.com/@linda0511ny/create-host-a-discord-bot-with-heroku-in-5-min-5cb0830d0ff2)


### Other useful things

If you have github + heroku, using Heroku's [Github integration](https://devcenter.heroku.com/articles/github-integration) allows you to automatically push Github pushes to also deploy on Heroku. (Using `git push` to push to both Github and Heroku)

When deploying on heroku, any variables stored in .env locally cannot be pushed to any public repos. It's advisable to use [Heroku Config Vars](https://devcenter.heroku.com/articles/config-vars) to store them.

## Current Modules

- [Admin](./modules/admin) for administrator commands
- [Archive](./modules/archive) for downloading channel/category/server contents into a Zip file
- [Channel Management](./modules/channel_management) for cloning, creating, and moving channels - [Cipher Race](modules/cipher_race) Race against the clock decoding ciphers!
- [Custom Command](./modules/custom_command) for making custom commands in different servers
- [Discord](modules/discord) for discord utility commands (e.g. roles, stats)
- [Error Logging](./modules/error_logging) for printing error logs
- [Help](./modules/help) is an updated help command which automatically pulls docstrings for `~help`
- [Lookup](./modules/lookup) for Searching the internet via google and wikipedia
- [Misc](./modules/misc) for misc. random (fun) commands
- [Music Race](./modules/music_race/) Help! Our tunes have been sawed apart and put back incorrectly!
- [Perfect Pitch](./modules/perfect_pitch) Become a composer and write tunes in mp4
- [Role Management](./modules/role_management) for managing roles and similar
- [Sheets](./modules/sheets) for working with Google Sheets during puzzlehunts
- [Solved](./modules/solved) for marking Discord Channels as solved, backsolved, solvedish etc.
- [Time](./modules/time) for finding the time anywhere in the world

## Acknowledgements

Big thanks to [Jonah Lawrence](https://github.com/DenverCoder1) and his [Professor Vector](https://github.com/DenverCoder1/professor-vector-discord-bot)
repo for much inspiration and code, specifically on the [Channel Management](./modules/channel_management), [Error Logging](./modules/error_logging), [Help](./modules/help), and [Solved](./modules/solved) modules. 

## Contributing/Issues

If you find any issues, bugs, or improvements, please feel free to open an issue and/or pull request! Thank you!

Feel free to find me on discord, `@kevslinger#9711` with any questions you may have!
