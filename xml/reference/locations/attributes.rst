====
location attributes
====


Append And Detract Attributes

<game name="AloneInTheDark">
    <title>Alone in the Dark</title>
    <version os="DOS">
      <locations>
        <path ev="installlocation" path="GOG.com\Alone in the Dark\INDARK"/>
        <registry root="local_machine" key="SOFTWARE\GOG.com\GOGALONE1" value="PATH" append="INDARK"/>
        <shortcut ev="startmenu" path="Programs\GOG.com\Alone in the Dark\Alone in the Dark.lnk" detract="DOSBOX" append="INDARK" />
      </locations>
      <files>
        <include filename="SAVE?.ITD"/>
      </files>
      <contributor>GameSave.Info</contributor>
    </version>
</game>
All of the location elements can use the append and detract attributes. In the above example, the shortcut provided actually points to:

C:\Program Files\GOG.com\Alone in the Dark\DOSBOX
But the saves are actually in:

C:\Program Files\GOG.com\Alone in the Dark\INDARK
These attributes tell us to detract (or take away) DOSBOX, then append (or add to the end) INDARK from the location the shortcut points to. This is frequently needed for expansions, registry keys and shortcuts, which will usually point close to the desired location, but not to exactly the right spot.

You can use both of the attributes, only one or the other, or none at all, there are no requirements format-wise.


only_for Attribute

<path ev="allusersprofile" path="Documents\Monolith Productions\Condemned" only_for="WindowsXP"/>
<path ev="public" path="Documents\Monolith Productions\Condemned" only_for="WindowsVista"/>
Some locations are only applicable to certain operating systems. For these you can use the only_for attribute to specify an OS that the path is for. All the OSs that can be used for the os attribute for the version element can be used here. See the above version element section for a list of them.


Deprecated Locations

<game name="OddworldStrangersWrath" follows="OddworldMunchsOddysee">
    <title>Oddworld: Stranger's Wrath</title>
    <version os="Windows">
      <locations>
        <path ev="steamcommon" path="stranger's wrath" deprecated="true"/>
        <path ev="userdocuments" path="Oddworld\Stranger's Wrath"/>
      </locations>
      <files>
        <include path="Save"/>
      </files>
      <files type="Settings">
        <include filename="config.txt"/>
      </files>
      <contributor>Arc Angel</contributor>
      <contributor>slake_jones</contributor>
    </version>
</game>
Sometimes a game changes where it keeps its saves. In this example, Oddworld: Stranger's Wrath USED TO keep its saves in its install folder. A patch changed this. By adding the deprecated attribute, we're saying that this WAS a save location, but it isn't used anymore. We keep these locations because there may still be saves there, and mark it as deprecated so we know we should never place saves there.