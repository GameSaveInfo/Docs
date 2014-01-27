====
<version>
====

<version os="Windows">

The version tag is used to specify the versions of the game the contained saves are compatible with. In this example, it's compatible with Windows. This does NOT mean this save will only work on Windows, only that it's only for the Windows version of the game. This save would also be compatible with Linux if you have Deus Ex installed under WINE. The reason it is organized like this is because GameSave.Info also doubles as the data source for the game save backup program MASGAU.

There are 5 attributes that allow us to describe a unique game save version:

os
   The operating system the save is compatible with. Possible values:
   #. Android
   #. DOS
   #. Linux
   #. OSX
   #. PS1
   #. PS2
   #. PS3
   #. PSP
   #. Windows
   #. WindowsVista
   #. WindowsXP
   
platform
   The technology platform the save is compatible with. Possible values:
   #. Flash
   #. RenPy
   #. ScummVM
   #. SteamCloud
   #. UbisoftSaveStorage
   
region
   The region of the world the save is for. Possible values include any 3-letter ISO 3166-1 country code, or any of these two-letter continent codes:
   #. AF - Africa
   #. AS - Asia
   #. EU - Europe
   #. NA - North America
   #. SA - South America
   #. OC - Oceania
   (Antarctica has its own country code, so I won't support its continent code)
   
media
   The delivery medium of the game version that the save is compatible with. Possible values:
   #. CD
   #. Download
   #. Floppy
   #. GoG
   #. Steam
   
release
   The release of the game the save is compatible with. This is freeform, can be anything at all. Some examples:
   #. CollectorsEdition
   #. TitaniumEdition
   #. Gold
   #. HD
   #. Remastered
   #. GOTY


If a save is compatible with more than one thing in any of these categories, just don't specify the attribute. Try to keep the version specification as general as possible, while simultaneously making sure that a save would not accidentally get labelled as belonging to the wrong version of the game.

<version os="Windows" media="CD" release="TitaniumEdition" region="USA">
This example states that the contained saves are only compatible with the Windows version of the Titanium Edition of the game that was released on CD in the USA. This example is fake, I have yet to encounter saves that had such specific requirements.

<version media="Steam">
An important distinction should be made between a version for Steam and a version specifically for Steam Cloud data. The above is for the former, and the below for the latter.

<version platform="SteamCloud">
You could also specify media="Steam" on this, and it would be accurate but since SteamCloud automatically imples Steam, it's not necessary.

My policy right now on DOS games is to label it as DOS if the save produced is only compatible with the DOS version of the game. If there exists a Windows version of a DOS game, and the saves are compatible with both, then both of the games' information would be combined into one Windows profile, such as with Master Of Orion 2 or Descent II.

If you omit these attributes, then it is saying that the saves described are compatible with all versions of the game. This is pretty rare, but these games do exist. One example is fs2_open:

  <game name="fs2_open">
    <title>fs2_open</title>
    <version>
      <locations>
        <path ev="installlocation" path="fs2_open"/>
        <parent name="FreeSpace2" os="Windows"/>
      </locations>
      <files>
        <include path="data\players"/>
      </files>
      <identifier filename="fs2_open*"/>
      <comment>Doesn't have a default install folder, so might require an Alt. Install Path.</comment>
      <contributor>GameSave.Info</contributor>
    </version>
  </game>
If a game's saves were to work across just Linux and Windows, I would also not add a platform attribute, even if there was a Mac version with incompatible saves. By adding an additional Mac-specific version we would be declaring such an incompatibility.

You can specify more than one version of a game within the same game tag:

 <game name="MechWarrior2">
    <title>MechWarrior 2: 31st Century Combat</title>
    <version os="Windows">
      <locations>
        <path ev="installlocation" path="Activision\BattlePack\MW2"/>
        <shortcut ev="startmenu" path="Programs\BattlePack\MechWarrior 2\MechWarrior 2 Uninstall.lnk"/>
      </locations>
      <files type="Mechs">
        <include path="mek"/>
      </files>
      <files>
        <include filename="userstar.bwd"/>
      </files>
      <files type="Settings">
        <include filename="MW2PRM.CFG"/>
        <include filename="MW2REG.CFG"/>
      </files>
      <contributor>GameSave.Info</contributor>
    </version>
    <version os="Windows" release="TitaniumEdition">
      <title>MechWarrior 2: 31st Century Combat: Titanium Edition</title>
      <locations>
        <path ev="installlocation" path="Activision\Titanium\Mechwarrior2"/>
        <path ev="altsavepaths" path="MechVM\games\mw2-31stcc-tt"/>
        <registry root="local_machine" key="SOFTWARE\Activision\Activenet\Applications\1020.2.1" value="Cwd"/>
        <shortcut ev="startmenu" path="Programs\Titanium\Mechwarrior2\Play MechWarrior2.lnk" detract="splash"/>
      </locations>
      <files type="Mechs">
        <include path="mek"/>
      </files>
      <files>
        <include filename="userstar.bwd"/>
      </files>
      <files type="Settings">
        <include filename="MW2PRM.CFG"/>
        <include filename="MW2REG.CFG"/>
      </files>
      <contributor>GameSave.Info</contributor>
    </version>
  </game>
As you can see we only specify a version title when that version has a title different than the main one specified under the game tag.

<version os="Windows" virtualstore="ignore" detect="required">
There are two additional attributes demonstrated here:

virtualstore - Specified if the game ignores VirtualStore in Windows Vista and later. Can be set to "ignore" or "use". Default is use.
detect - Specifies wether the game's save location cannot be predicted without an existing save location. Can be either "required" or "optional". Default is "optional".
<version deprecated="true">
If a version is marked as deprecated, it means that the information provided is no longer considered correct. It's kept only for posterity and backwards-compatability.
