===
<path />
===

Location Using A Path

<path ev="installlocation" path="DeusEx"/>
The path tag lets us specify an actual folder name, but sitll allows us to do so in a format that can adjust automatically for any system. This is attained via environment variables. The environment variable will be replaced with whatever the appropriate path from the system is, and prepended onto the provided path.

The environment variables available for use:
allusersprofile	A Windows folder that contains data common to all the users.
Here are some common examples:
Windows Vista, 7 & 8
C:\ProgramData
Windows XP
C:\Documents and Settings\All Users
altsavepaths	This is catch-all folder, it could be literally anywhere.
I know it's not much to go on :(
appdata	Contains the application data for a particular Windows user.
Here are some common examples:
Windows Vista, 7 & 8
C:\Users\%USERNAME%\AppData\Roaming
Windows XP
C:\Documents and Settings\%USERNAME%\Application Data
commonapplicationdata	Contains application data that is common to all users
Here are some common examples:
Windows Vista, 7 & 8
C:\ProgramData
Windows XP
C:\Documents and Settings\All Users\Application Data
desktop	A per-user folder that contains the files store on a user's desktop.
Here are some common examples:
Windows Vista, 7 & 8
C:\Users\%USERNAME%\Desktop
Windows XP
C:\Documents and Settings\%USERNAME%\Desktop
drive	Refers to the root of a drive. Any drive.
Here are some common examples:
Linux
/mnt/sda1
Windows
C:\
D:\
G:\
T:\
flashshared	Stores cached Adobe Flash data.
Here are some common examples:
Windows Vista, 7 & 8
C:\Users\%USERNAME%\AppData\Roaming\Macromedia\Flash Player\#SharedObjects
Windows XP
C:\Documents and Settings\%USERNAME%\Application Data\Macromedia\Flash Player\#SharedObjects
installlocation	This means that the game keeps its saves in its install folder.
Here are some common examples:
Linux
/usr/bin
/var/shared
Windows
C:\Program Files
C:\Program Files (x86) (Common for games on 64-bit Windows)
C:\Games
localappdata	Contains the local settings for a particular Windows user.
Here are some common examples:
Windows Vista, 7 & 8
C:\Users\%USERNAME%\AppData\Local
Windows XP
C:\Documents and Settings\%USERNAME%\Local Settings\Application Data
public	A special folder only on certain versions of Windows for storing user data common to all the users.
Here are some common examples:
Windows Vista, 7 & 8
C:\Users\Public
savedgames	A folder only on certain versions of Windows specifically for storing saved games.
Here are some common examples:
Windows Vista, 7 & 8
C:\Users\%USERNAME%\Saved Games
startmenu	The folder that contains the files for Windows' start menu.
There is one for each user, and a global one that all users share.
Here are some common examples:
Windows Vista, 7 & 8
User: C:\Users\%USER%\AppData\Roaming\Microsoft\Windows\Start
Menu\
Global: C:\ProgramData\Microsoft\Windows\Start Menu
Windows XP
User: C:\Documents and Settings\%USER%\Start Menu
Global: C:\Documents and Settings\All Users\Start Menu
steamcommon	This is the location where Steam keeps games that don't use its integrated GCF system (which is most games).
Here are some common examples:
Windows
C:\Program Files\Steam\steamapps\common
steamsourcemods	This folder contains the files for mods for Valve's Source game engine.
Here are some common examples:
Windows
C:\Program Files\Steam\steamapps\SourceMods
steamuser	This location stores per-user settings, saves and cache files for Valve's game distributed through Steam.
Here are some common examples:
Windows
C:\Program Files\Steam\steamapps\%STEAMUSERNAME%
steamuserdata	This folder stores Steam Cloud data.
This data is automatically backed up onto Steam's servers.
Here are some common examples:
Windows
C:\Program Files\Steam\userdata\%STEAMID%
ubisoftsavestorage	The save location used by the Ubisoft Game Launcher
Here are some common examples:
Windows Vista, 7 & 8
C:\Users\%USERNAME%\AppData\Local\Ubisoft Game Launcher\savegame_storage\%RANDOMNUMBERS%\
Windows XP
C:\Documents and Settings\%USERNAME%\Local Settings\Application Data\Ubisoft Game Launcher\savegame_storage\%RANDOMNUMBERS%\
userdocuments	The user's document folder.
Here are some common examples:
Windows Vista, 7 & 8
C:\Users\%USERNAME%\Documents
Windows XP
C:\Documents and Settings\%USERNAME%\My Documents
userprofile	This folder contains all the files related to a particular user.
Here are some common examples:
Linux
/home/%USERNAME%/
Windows Vista, 7 & 8
C:\Users\%USERNAME%
Windows XP
C:\Documents and Settings\%USERNAME%
Different versions of a game can install to all kinds of locations, so if a game keeps its saves in the install folder we have to specify as many different install paths as we can discover. For Deus Ex, the CD, Steam and GoG.com versions all install to different locations, so we add a path element for each one:

<path ev="installlocation" path="DeusEx"/>
<path ev="installlocation" path="GOG.com\Deus Ex"/>
<path ev="steamcommon" path="deus ex"/>
If we're lucky, the game keeps its saves somewhere other than the install folder, which usually means that all versions of the gam use the exact same path. A good example, and one that most games follow these days, is using the "My Documents" folder. Deus Ex's sequel, Invisible War, was wise enough to do this:

<path ev="userdocuments" path="Deus Ex - Invisible War"/>
This will check each user's My Documents folder for a path called "Deus Ex - Invisible War", and should work for the disc, Steam, Impulse, Gog.com or any other versions of the game. This is not universal unfortuantely, as some games (like Alan Wake) use different folder names for different versions, despite all using folders like My Documents.