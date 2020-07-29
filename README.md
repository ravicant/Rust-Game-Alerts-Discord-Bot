# Rust Alerts

**A bot that sends user's online status for the game Rust**

Rust (the game not the language) alerts is a discord bot made in JavaScript/Node using the Discord.js library. My friends and I like to play Rust and we make enemies. We would periodically check Steam to see if they were online or not. This bot changed that. It periodically checks battlemetrics.com to see who's on and updates our discord server.

![Example](https://i.imgur.com/BBmAsan.png)

To set it up yourself you need to first go to discord.com/developers and create a new application, a new bot, and copy the bot token.

Clone the repo and run `npm init` to download the required dependencies.

In the configs folder make a new file called `bot.json` and put
`{"token": "paste your token here"}`
and save.

Run `index.js` with `npm start` and the bot will be online

Create a new text channel dedicated to the bot because the bot will delete messages. Inside that channel run the `!setup` command.

| Command | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  | Example                              |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------ |
| !setup  | Runs the setup for the bot. It'll ask for the battlemetrics link to the Rust server. The setup also sets the channel that you ran the command in as its dedicated channel. Running the setup command after setup has been completed will ask for a confirmation and if yes is selected; it'll run through the setup again.                                                                                                                                                                                                   | `!setup`                             |
| !add    | Adds usernames to list that the bot checks for. Use a comma to separate names.                                                                                                                                                                                                                                                                                                                                                                                                                                               | `!add username1, username2`          |
| !remove | Removed usernames. Only removed one name at a time. Putting "all" as username removes all users without warning.                                                                                                                                                                                                                                                                                                                                                                                                             | `!remove username2` or `!remove all` |  |
| !help   | Sends message with all commands.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | `!help`                              |
| !list   | Lists all the username added by the add command.                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | `!list`                              |
| !start  | Starts the rust alerts. Most commands will still work while this is on.                                                                                                                                                                                                                                                                                                                                                                                                                                                      | `!start`                             |
| !stop   | Stops rust alerts. Often necessary when bot settings have changed.                                                                                                                                                                                                                                                                                                                                                                                                                                                           | `!stop`                              |
| !status | Check if rust alerts are on or off.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | `!status`                            |
| !time   | Sets update rate in milliseconds. Default is 10000 (10 seconds). If command is typed without argument it'll display current time setting.                                                                                                                                                                                                                                                                                                                                                                                    | `!time 20000`                        |
| !config | Displays current configuration. This does not allow changing the config. Just displaying.                                                                                                                                                                                                                                                                                                                                                                                                                                    | `!config`                            |
| !alert  | Changes alert settings. Options are [most/online/offline/least]. Most will make sure to send a new discord message every time it detects one of the users goes online or offline. Least is the default setting and will only send a discord alert when it starts or a config setting is made. It does this by editing its previous message. Online only sends alert if a user gets online. Offline only send a message when a users goes offline. Using the alert command without an argument returns current alert setting. | `!alert offline`                     |

# TO-DO

-   Use battlemetrics API instead of scraping site (didn't realize they had an API until I finished).
-   Make bot command prefix changeable.
-   Add more information about the users like when they were last online.
-   Fix issues regarding alerts
-   Send updates on Rust news
