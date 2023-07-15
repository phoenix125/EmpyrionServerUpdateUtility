EmpyrionServerUpdateUtility - A Utility to Keep Your Empyrion Dedicated Server updated (and schedule server restarts, download and install new server files, and more!)
- Latest version: EmpyrionServerUpdateUtility_v1.0.7 (2021-07-14) (Beta and Stable are the same version)
- By Phoenix125 | http://www.Phoenix125.com | http://discord.gg/EU7pzPs | kim@kim125.com
- Based on Dateranoth's ConanExilesServerUtility-3.3.0 and 7dServerUtility | https://gamercide.org/

----------
 FEATURES
----------
- Works with Empyrion Admin Helper (EAH). Optionally closes EAH for updates then restarts it.
- Easy to use and set up. Tray Icon menus only for simplicity yet full functionality.
- Discord: Send server status, reboots, chats, players join or leave, selectively to 4 webhooks.
- Backups. Partial and full server.
- Keeps server updated and running.
- Easily downloads, installs, and set up a new Dedicated Server.
- Send telnet & chat messages with a click.
- Announce server updates and/or restarts in game, on Discord and Twitch.
- Works with all version: Public, Experimental, and custom.
- KeepAlive Watchdog: Restarts "stuck" servers and EAH. 3 methods of detection: Running process PID, query port, and telnet.
- Scheduled restarts.
- Remote Restart: Reboot the server using any web browser.
- Run multiple instances to manage multiple servers.
- Detailed logs.
More detailed features:
- Optionally execute external files for six unique conditions, including at updates, scheduled restarts, remote restart, when first restart notice is announced
  *These options are great executing a batch file to disable certain mods during a server update, to run custom announcement scripts, make config changes (enable PVP at scheduled times), etc.
- Automatically imports server settings from serverconfig.xml (or comparable file) and creates a temporary file... leaving the original file untouched.

-----------------
 GETTING STARTED (Two sets of instructions: one for existing servers and the other to use the EmpyrionServerUpdateUtility tool to download and install a new dedicated server)
-----------------

EXISTING SERVER:
1) Run EmpyrionServerUpdateUtility.exe
2) Adjust desired settings in the Config window. If config window doesn't show, click the tray icon and select "Util CONFIG" toward the top.
- Required fields: Server Folder, Config File, and Local IP.
3) Click "Restart Util"
4) Your server should be up-to-date and running!

FRESH SERVER: Use EmpyrionServerUpdateUtility to download install a fresh dedicated server
1) Run EmpyrionServerUpdateUtility.exe
2) Adjust desired settings in the Config window. If config window doesn't show, click the tray icon and select "Util CONFIG" toward the top.
- Required fields: Server Folder and Local IP. (The Config File will be created when the server is downloaded).
3) Click "Restart Util"
4) Your server files will be downloaded from Steam. Once done, your server will start.
5) From the tray icon, click "Server Config" (toward the bottom). Make desired changes.
6) Restart server and util.
7) Congrats! Your new server is running.

------------
 KNOWN BUGS
------------
- None reported at this time

--------------
 INSTRUCTIONS
-------------- 
Notes:	- It is suggested that you RENAME or COPY the default dedicated.yaml file as it will be overwritten with any updates.
	- Telnet password can only contain letters and numbers.  

To shut down your server:
- Right-click on the EmpyrioServerUpdateUtility icon and select EXIT.
To restart your server:
- Run EmpyrionServerUpdateUtility.exe

-----------------
 TIPS & COMMENTS
-----------------
Comments:
- It is suggested that you RENAME or COPY the default dedicated.yaml file as it may be overwritten with server updates.
- Telnet password can only contain letters and numbers.
- There are a lot of parameters that can be set in the EmpyrionServerUpdateUtility.ini. All parameters can be left at the default value, except...
    I recommend changing the default dedicated.yaml filename so that it does not get overwritten with each server update or file validation.
- If running multiple instances of this utility, each copy must be in a separate folder.
- If running multiple instances of this utility, rename EmpyrionServerUpdateUtility.exe to a unique name for each server. The phoenix icon in the lower right will display the filename.
  For example: I run 6 servers, so I renamed the EmpyrionServerUpdateUtility.exe files to Empy-STABLE.EXE, Empy-EXP.EXE, CONAN-2X.EXE, CONAN-PIPPI.EXE, CONAN-LITMAN.EXE, & ATLAS.EXE.
- If using the "Request Restart From Browser" option, you have to use your local PC's IP address as the server's IP. ex: "Server Local IP=192.168.1.10" (127.0.0.1 and external IP do not work).
Tips:
- Use the "Run external script during server updates" feature to run a batch file that disables certain mods during a server update to prevent incompatibilities.

---------------------------
 UPCOMING PLANNED FEATURES
---------------------------

----------------
 DOWNLOAD LINKS
----------------
Latest Version:       http://www.phoenix125.com/share/empyrion/EmpyrionServerUpdateUtility.zip
Previous Versions:    http://www.phoenix125.com/share/empyrion/empyrionhistory/
Source Code (AutoIT): http://www.phoenix125.com/share/empyrion/EmpyrionServerUpdateUtility.au3
GitHub:	              https://github.com/phoenix125/EmpyrionServerUpdateUtility

Website: http://www.Phoenix125.com
Discord: http://discord.gg/EU7pzPs
Forum:   https://phoenix125.createaforum.com/index.php

More ServerUpdateUtilities available: Conan Exiles, 7 Days to Die, and Atlas.

---------
 CREDITS
---------
- Based on Dateranoth's ConanExilesServerUtility-3.3.0 and 7dServerUtility (THANK YOU!)
https://gamercide.org/forum/topic/9296-7-days-to-die-server-utility/
https://gamercide.org/forum/topic/10558-conan-exiles-server-utility/


-----------------------
 DETAILED INSTRUCTIONS
-----------------------
====> Request Restart From Browser <====
- If enabled on the server, use to remotely restart the server.
- When restarting, an announcement will be made in-game, on Discord, and in Twitch if enabled, with the set duration of delay (warning).
- Set Password in INI file to save, or type each time.
- Restart using IP or Domain Name
- Restart commands are now expecting HTTP headers, and can be sent to the server from a web browser using the format http://IP:PORT?restart=user_pass. The utility will respond if the password is accepted or not. There is also a limit for max password attempts. After 15 tries in 10 minutes the requesting IP will be locked out for 10 minutes.
- 404 Responses will be sent if the RestartKey does not match or the header is incorrect. You can enable Debugging for a full output to the log what is being received by the server if you have any trouble.
- These Are the Allowed Characters in the RestartCode (Password) 1234567890abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ!@$%^&*()+=-{}[]\|:;./?

Usage Example:
INI SETTINGS
[Game Server IP]
ListenIP=192.168.0.1
[Use Remote Restart ?yes/no]
UseRemoteRestart=yes
[Remote Restart Request Key http://IP:Port?RestartKey=RestartCode (Ex: 192.168.1.30:57520?restart=password)]
ListenPort=57520
RestartKey=restart
RestartCode=password

- You can have multiple passwords. For example: RestartCode=password1,pass2,pwd3
In a standard web browser, type in the URL http://192.168.1.30:57520?restart=password. The Server would compare the pass and find that it is correct. It would respond with 200 OK And HTML Code stating the server is restarting.

-----------------
 VERSION HISTORY
-----------------
(2023-07-14) v1.0.7 Stability improvements, bug fixes, and Discord server crash announcements
- Fixed: New improved code for checking for server updates.
- Fixed: Improved code for detecting existing servers to prevent duplicate servers from starting and to allow multiple servers to be hosted on the same machine.
- Fixed: Query & telnet Watchdog was detecting server crashes but often failing to restart the server.  It is now fixed.
- Fixed: Updated the server shutdown command to "saveandexit 0" for cleaner server shutdown.
- Changed: SteamCMD Updater: Moved force install before login
- Added: SteamCMD Updater: If any branch requires a password, including experimental, and no password given, the update check is skipped to prevent a restart loop.
- Changed: Minor improvements to the log file.
- Added: Sometimes EAH uses the Dedicated_EAH.yaml instead of the default file.  ESUU detects this and creates a log entry and prompts user to change if connection errors occur.
- Changed: Default value for closing EAH is Always.  ESUU will now, by default, close EAH whenever servers are shut down because EAH no longer automatically reconnects when server comes online.
- Changed: Default value for watchdog Query port monitoring changed to yes
- Added: Discord: Watchdog can announce when a server crash is first detected and when it performs the restart.
         Note! Announcements must be configured manually in the EmpyrionServerUpdateUtility.ini using any text editor.  There are two sections: DISCORD INTEGRATION & DISCORD MESSAGES sections.
         Comment: In case there is a temporary loss of telnet/query connection or server freeze, multiple failures can be set before it actually restarts the server.  Default is 3 failed attempts.

(2021-01-30) v1.0.6 Bug fixes.
- Fixed: Line 19996 Error during server restarts. (Thanks to @Aleax for reporting)
- Fixed: In-Game restart announcements were only showing first word. (Thanks to @SylenThunder for reporting)
- Fixed: Improved reliability of Announcement Intervals in Config.
- *Added: Optionally hide passwords from logs. (Thanks to @Aleax for requesting). 
- *Added: Customizable EAH filename and location. (Thanks to @SylenThunder for requesting)
*Manually set near the end of the EmpyrionServerUpdateUtility.ini file.

(2020-12-12) v1.0.5 Bug Fix: Now closes EAH
- Fixed: EAH failed to close. Util now closes EAH during updates and restarts, if desired.

(2020-09-17) v1.0.4 Bug Fixes
- Fixed: If steamcmd command line was manually changed, util kept resetting it. (Thanks to @AOD_Bazslash for reporting)
- Fixed: In Config window, the Config File "Select File" button was restricting to .xml files. Changed to .yaml.
- Fixed: If player name ended with a space, the util would keep posting "new player" to Discord.

(2020-09-09) v1.0.3 Bug Fix
- Fixed: Line 20564 due to error acruiring server name from Query if Query disabled. (Thanks to @SylenThunder for reporting)
- Changed: Query Port Watchdog is disabled by default now.

(2020-09-02) v1.0.2 Bug Fixes
- Fixed: Program would eventually crash during server restarts due to plink starting loop.
- Fixed: Line 22587 error
- Fixed: Log now correctly logs imported SaveDirectory

(2020-09-01) v1.0.1 Line 20383 Backup Bug Fix
- Fixed: Backups caused line 20383 error

(2020-08-31) v1.0.0 Initial Release
- Works with Empyrion Admin Helper (EAH). Optionally closes EAH for updates then restarts it.
- Easy to use and set up. Tray Icon menus only for simplicity yet full functionality.
- Discord: Send server status, reboots, chats, players join or leave, selectively to 4 webhooks.
- Backups. Partial and full server.
- Keeps server updated and running.
- Easily downloads, installs, and set up a new Dedicated Server.
- Send telnet & chat messages with a click.
- Announce server updates and/or restarts in game, on Discord and Twitch.
- Works with all version: Public, Experimental, and custom.
- KeepAlive Watchdog: Restarts "stuck" servers and EAH. 3 methods of detection: Running process PID, query port, and telnet.
- Scheduled restarts.
- Remote Restart: Reboot the server using any web browser.
- Run multiple instances to manage multiple servers.
- Detailed logs.
