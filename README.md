# Streamlabs-Chatbot
[Dowload Chatbot](https://www.streamlabs.com/chatbot)  
[Chatbot Discord](https://discordapp.com/invite/J4QMG5m)  
[Changelog](https://streamlabs.com/changelog?filter=Streamlabs%20Chatbot)  
[Suggest new Features](https://ideas.streamlabs.com)  
[Streamlabs Website](https://www.streamlabs.com)  
  
Documentation:  
[Twitch](https://cdn.streamlabs.com/chatbot/Documentation_Twitch.pdf) | [YouTube](https://cdn.streamlabs.com/chatbot/Documentation_Youtube.pdf) | [Mixer](https://cdn.streamlabs.com/chatbot/Documentation_Mixer.pdf)  

## List of issues with known fixes
- [Messages show in console/chatbot but not stream chat](https://github.com/StreamlabsSupport/Streamlabs-Chatbot#messages-show-in-consolechatbot-but-not-stream-chat)
- [Bot can send messages but isn't responding to commands](https://github.com/StreamlabsSupport/Streamlabs-Chatbot/blob/master/README.md#bot-can-send-messages-but-isnt-responding-to-commands)
- [Songrequest by artist/name](https://github.com/StreamlabsSupport/Streamlabs-Chatbot#songrequest-by-artistname)
- [Songrequests on Spotify is playing random songs after the first one](https://github.com/StreamlabsSupport/Streamlabs-Chatbot#songrequests-on-spotify-is-playing-random-songs-after-the-first-one)
- [Songrequests not responding in chat/ Songrequest stuck on track](https://github.com/StreamlabsSupport/Streamlabs-Chatbot#songrequests-not-responding-in-chat-songrequest-stuck-on-track)
- [SFX aren't playing](https://github.com/StreamlabsSupport/Streamlabs-Chatbot#sfx-arent-playing)
- [Bot crashes / doesn't launch](https://github.com/StreamlabsSupport/Streamlabs-Chatbot#bot-crashes--doesnt-launch)
- [Missing tabs](https://github.com/StreamlabsSupport/Streamlabs-Chatbot#missing-tabs)
- [Scripts not loading](https://github.com/StreamlabsSupport/Streamlabs-Chatbot#scripts-not-loading)
- [Minigames aren't working](https://github.com/StreamlabsSupport/Streamlabs-Chatbot#minigames-arent-working)
- [Bot size is huge/tiny on one or multiple monitors](https://github.com/StreamlabsSupport/Streamlabs-Chatbot#bot-size-is-hugetiny-on-one-or-multiple-monitors)
- [Notifications aren't working](https://github.com/StreamlabsSupport/Streamlabs-Chatbot#notifications-arent-working)
- [Can't update game/tile through dashboard or command](https://github.com/StreamlabsSupport/Streamlabs-Chatbot/blob/master/README.md#cant-update-gametile-through-dashboard-or-command)
- [Can't generate token ](https://github.com/StreamlabsSupport/Streamlabs-Chatbot#cant-generate-token)

## Messages show in console/chatbot but not stream chat   
You most likely connected the bot to the wrong channel.  
1. Go to connections :bust_in_silhouette: 
2. Go into bot connection (mixer or twitch bot)  
3. Make sure Streamer Channel is the same as your actual stream name  

## Bot can send messages but isn't responding to commands

Most likely one of the following settings was overlooked.
- `Usage` make sure it's set to the chat that's being used. Stream Whisper means you have to whisper the command
- `Cost` if the cost is set to anything higher than 0 currency must be enabled and user need enough points
- `Cooldown` Broadcaster ignore cooldowns but nobody else does, restarting the bot will clear all cooldowns
- `Permission` & `Info` 

YouTube only - last resort/possible reason.
> Timestamps in the bot doesn't match the timestamps sent from youtube to the bot, so the bot doesn't recognize new messages to respond to. To ensure this isn't the issue simply enable "Set timee automatically" and make sure the correct Time zone is selected, how to find these settings is explained [here](https://www.computerhope.com/issues/ch000554.htm). 


## Songrequest by artist/name
- To enable this feature go into the `Songrequest` tab in the bot then press the :gear: in the top right corner and change `mode` from `$id` to either of the two other options

## Songrequests on Spotify is playing random songs after the first one
- You can disable this in Spotify under `edit` -> `preferences` -> `Advanced settings` -> `Autoplay` -> `Autoplay similar songs when your music ends` 

## Songrequests not responding in chat/ Songrequest stuck on track
Songrequests not responding could be a few possible reasons, please check the following reasons first.
1. Songrequests are disabled in the songrequest tab (top left corner)
2. Songrequests have a cost that's higher than the users current currencyamount
3. Songrequests are set to work in discord/whispers only. `settings` :gear: -> `usage` -> `songrequests`

If none of the options above explained your issue you can try resetting songqueue and songrequest settings by following these steps:

1. press the `?` in the bot's top right corner
2. press `open install directory` 
3. close the bot 
4. go into `services` folder 
5. go into `twitch` folder (replace with youtube or mixer if you stream there)
6. go into `settings` folder 
7. delete `SongQueue.bin` and `songrequestsettings.bin` 
8. start up the bot
9. Enable songrequests


## SFX aren't playing  
> If preview works you can skip these
- Wrong `audio output` is selected in `settings` :gear: -> `general`  
- `audio enging` is set to waveout in `settings` :gear: -> `general`  
- File/filepath doesn't exist
- Soundfile format isn't supported (.mp3 only)
- The Chatbot is muted in windows audio mixer

> Preview working but not commands
- `Only play Sound Files when stream is live` is checked in `Commands tab` -> `settings` :gear:
- Global sound file user cooldown is in minutes `commands tab` -> `settings` :gear: Restart the Chatbot to clear cooldowns
- Numbers of votes set is too high, the bot doesn't announce each vote

## Bot crashes / doesn't launch
Most likely you don't have microsoft `visual c++ redistributables 2013` installed, note that both `x64` and `x86` needs to be installed. If you have both installed you can still visit [this link](https://www.microsoft.com/en-us/download/details.aspx?id=40784) to download and repair them both. If you need a step to step tutorial for this you can find that [here](https://support.streamlabs.com/hc/en-us/articles/115004407613-Repair-C-Redistributables-2013-x86-and-x64).  

> Running as admin  

- It's always a good option to run the bot as admin to make sure it got all permissions needed. In order to do that you right click your Chatbot Shortcut -> `run as administrator`

> If all else failed it might be MSI afterburner  

- First check if the bot does launch with MSI turned off (If it does not it is a different problem and this solution is not for you) With the bot closed and afterburner open, go into afterburner `settings` -> `User Interface` and make sure `Single tray icon mode` is `OFF`. Then go to your tray, right click `RivaTunerStatisticsServer`, and click `show`.  Click `Add`, then find the Streamlabs `Chatbot.exe`.  Making sure the Streamlabs Chatbot profile is selected, turn Application Detection Level to None.  Open the chatbot and it should work fine now.

## Missing tabs
There are three tabs that can be hidden in the chatbot.
- `Discord tab` is hidden for YouTube and Mixer since they do not support discord integration
- `Scripts tab` is hidden until you connect streamer and bot account under `connections` to the streamer's channel
- `Subscribers tab` is hidden for YouTube and Mixer

## Scripts not loading
There are no default scripts with the bot currently so in order for them to install they must have been imported manually. 
> Importing scripts
1. Download a .zip file containging the script (preferably from chatbot discord)
2. Go into the scripts tab and press `import` in the top right corner
3. Select the .zip file you downloaded in `step 1`
4. Hit `open` and after a short time it should pop up a message confirming that it was a successful import. 

When troubleshooting scripts your best help is the error view. You can find it in the top right corner of the scripts tab. 
> Troubleshooting scripts
- No module named `os` / `json`
  - Make sure [python 2.7.13](https://www.python.org/downloads/release/python-2713/)  x86 is installed. Don't use newer versions of python or x64
  - Make sure the lib folder path found in `scripts tab` -> `settings` :gear: leads to the lib folder located inside the python folder that was created when installing python. 
- Unexpected token `from` / `:`
  - Make sure you installed [python 2.7.13](https://www.python.org/downloads/release/python-2713/) x86 and NOT python 3.X


## Minigames aren't working
Minigames require you to enable currency before they can be used, this still applies even if the cost is 0.
<details>
  <summary>Heist (Click to expand)</summary>

- Command needs to be followed by a value (!heist 10)
- Heist will show a message saying that it's open and people can join
- People joining won't get a message unless enabled in heist message settings
- Start delay needs to be at least 1 to give users the time to join in
- If not enough people (lower than min entries) enters it get cancelled

</details>
  
<details>
  <summary>Duel (Click to expand)</summary>

- Command needs to be followed by a target (!challenge must13)
- Users competing in a duel need to have enough currency (same or above the cost)
- A message will be triggered and the target must answer with the original user (!challenge castorr91)
- Expiry time needs to be at least 1 or the target got 0 minutes to accept the challenge
</details>
  
<details>
  <summary>Free For All (Click to expand)</summary>

- Only the first one starting the game will get a response
- Users competing in the Free for All need to have enough currency (same or above the cost)
- Start delay needs to be at least 1 to give users the time to join in
- If not enough people (lower than min entries) enters it get cancelled
</details>
  
<details>
  <summary>Boss (Click to expand)</summary>

- Only the first one starting the game will get a response
- Users competing in a duel need to have enough currency (same or above the cost)
- Start delay needs to be at least 1 to give users the time to join in
- When the timer runs out the needs to be a boss that got the interval as the amount of praticipants. If no boss is found for the group size it gets cancelled.  
</details>

If minigames still aren't working make sure that `settings` :gear: -> `usage` -> `minigames` are set to match where you try to use them. Minigames can only be either discord or stream chat and not both.

## Bot size is huge/tiny on one or multiple monitors
right click the chatbot shortcut -> go to the `compability tab` -> change `scaling option` to system "Override high DPI scaling behavior. Scaling performed by:" -> select `system`.
If your shortcut is in the task bar you have to `right click` the icon -> `right click` where it says "Streamlabs Chatbot" and then you go to the compability tab. [Example](https://i.gyazo.com/e445bedb5389fee195c6137448866a43.gif)  


## Notifications aren't working
Click the :bust_in_silhouette: in the bottom left corner of the bot and go to `streamlabs` 
1. Disconnect from streamlabs
2. Generate token (make sure it's using the streamer account)
3. Connect to streamlabs  

> Note that you also need to have any widget open. Alert box/event list/ chat box/streamlabels/ Streamlabs OBS

## Can't update game/tile through dashboard or command

Your twitch token for the streamer account expired. Please generate a new one
`connections` :bust_in_silhouette: -> `twitch streamer` -> `disconnect` -> `generate token` -> `connect`

## Can't generate token  

This is due to a connection issue between the bot and the site it needs to generate the token. 
- Make sure there's an expcetion for the bot in your firewall
- Make sure there's an exception for the bot in your antivirus/windows defender
- Disabling ipv6 have resolved the issue for some users [Guide Here](https://support.streamlabs.com/hc/en-us/articles/115004232954-How-to-solve-IPv6-issues)
- Use a VPN to get around recaptcha to generate tokens.  

If nothing else work you can manually generate some tokens through these links  
[Twitch Bot Token](https://api.twitch.tv/kraken/oauth2/authorize?response_type=token&client_id=dve7ifeawf0xeegigqamnvqy9qqm2y&redirect_uri=https%3A%2F%2Fstreamlabs.com%2Fchatbot-auth%3Fservice%3Dtwitch&scope=chat_login+user_read&force_verify=true) | 
[Twitch Streamer Token](https://api.twitch.tv/kraken/oauth2/authorize?response_type=token&client_id=dve7ifeawf0xeegigqamnvqy9qqm2y&redirect_uri=https%3A%2F%2Fstreamlabs.com%2Fchatbot-auth%3Fservice%3Dtwitch&scope=chat_login+user_read+channel_check_subscription+channel_commercial+channel_editor+channel_subscriptions&force_verify=true) | 
[Spotify Token](https://accounts.spotify.com/en/authorize?client_id=681722a742874f1295455870c2da4d36&response_type=code&redirect_uri=https:%2F%2Fstreamlabs.com%2Fchatbot-auth%3Fservice%3Dspotify&scope=user-read-private%20playlist-read-private&show_dialog=true) | 
[Streamlabs Token](https://www.streamlabs.com/login?r=https%3A%2F%2Fwww.streamlabs.com%2Fapi%2Fv1.0%2Fauthorize%3Fclient_id%3DWwQemCiJEhLTnk9mBvPCGWIUvbYWNzpuEG6wxkHJ%26redirect_uri%3Dhttps%253A%252F%252Fstreamlabs.com%252Fchatbot-auth%253Fservice%253Dstreamlabs%26response_type%3Dcode%26scope%3Dlegacy.token%2520donations.read%2520alerts.write%2520credits.write%2520jar.write%2520socket.token%2520points.write%2520points.read%2520wheel.write) | 
[Gamewisp Token](https://api.gamewisp.com/pub/v1/oauth/authorize?client_id=fa5358299f20fc03b66e7df1833235169341caf&redirect_uri=https://streamlabs.com/chatbot-auth?service=gamewisp&response_type=code&scope=read_only&state=SLCB) | 
