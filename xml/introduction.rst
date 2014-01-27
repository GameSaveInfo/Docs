====
Introduction
====

.. highlight:: xml

.. role:: xml(code)
   :language: xml

GameSave.Info uses XML files checked into Github to describe where each game keeps its settings and saves. As you may or may not know, an XML file is little more than a specially typed text file, and can be created in programs as simple as notepad. All you do is fire up your favorite text editor and type the correct lines. Here's an excerpt from the d.xml file:

.. code-block:: xml

   <game name="DeusEx" added="1955-11-05T00:00:00" updated="1955-11-05T00:00:00">
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

This looks more intimidating than it is. Each tag is explained on its own page, but before you read those let's define some terms::

   <game name="DeusEx">

Element or Tag
   That little bit of code is an element. Elements are surrounded by < and >. Some elements have an opening and closing, like :xml:`<game></game>` where :xml:`</game>` is the closing element. Anything between the opening and closing element are considered "children" of that element.

Attribute
   The word "name" in the above is an attribute. It's like a property of an element.

NOTE: IN PATHS AND FILENAMES LEAVE OFF ALL LEADING AND TRAILING SLASHES (\\ AND /)

ANOTHER NOTE: There is a `schema file on GitHub <https://github.com/GameSaveInfo/Data/blob/master/GameSaveInfo202.xsd>`_\ . If you know what that means, use it.