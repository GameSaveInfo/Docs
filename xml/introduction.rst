====
Introduction
====

GameSave.Info uses an XML file checked into Github to describe where each game keeps its settings and saves. As you may or may not know, an XML file is little more than a specially typed text file, and can be created in programs as simple as notepad. All you do is fire up your favorite text editor and type the correct lines. Here's an excerpt from the games.xml file::

   <game name="DeusEx">
    <title>Deus Ex</title>
    <version os="PS2" region="USA">
      <title>Deus Ex: The Conspiracy</title>
      <ps_code prefix="SLUS" suffix="20111"/>
      <contributor>GameSave.Info</contributor>
    </version>
    <version os="Windows">
      <locations>
        <path ev="installlocation" path="DeusEx"/>
        <path ev="installlocation" path="GOG.com\Deus Ex"/>
        <path ev="steamcommon" path="deus ex"/>
        <registry root="local_machine" key="SOFTWARE\GOG.com\GOGDEUSX" value="PATH"/>
        <registry root="local_machine" key="SOFTWARE\Unreal Technology\Installed Apps\Deus Ex" value="Folder"/>
        <shortcut ev="startmenu" path="Programs\Deus Ex\Play Deus Ex.lnk" detract="System"/>
        <shortcut ev="startmenu" path="Programs\GOG.com\Deus Ex GOTY\Deus Ex GOTY.lnk" detract="System"/>
      </locations>
      <files>
        <include path="Save"/>
      </files>
      <files type="Settings">
        <include path="System" filename="*.ini"/>
      </files>
      <linkable path="Save"/>
      <identifier path="Save"/>
      <contributor>GameSave.Info</contributor>
    </version>
    <comment>The best game EVER!</comment>
   </game>

This looks more intimidating than it is. Let's go into it line-by-line, but first some terms:

``<game name="DeusEx">``

Element or Tag
That little bit of code is an element. Elements are surrounded by < and >.
Attribute
The word "name" in the above is an attribute. It's like a property of an element.
**NOTE: IN PATHS AND FILENAMES LEAVE OFF ALL LEADING AND TRAILING SLASHES ( \ AND / )**

**ANOTHER NOTE: There is a schema file on GitHub. If you know what that means, use it.**