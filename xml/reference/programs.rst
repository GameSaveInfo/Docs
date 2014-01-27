.. highlight:: xml
<programs>
====

****
Example
****

.. code-block:: xml  

  <programs majorVersion="2" minorVersion="0" revision="2" updated="2013-06-15T13:45:04" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="GameSaveInfo202.xsd">
    ... 
  </programs>

****
Description
****

The root element for the GameSave.Info XML format is the "programs" element. There can only be one "programs" element per XML file. The name "programs" was chosen because an individual file can contain data on not just games, but mods and system tools.

****
Attributes
****

majorVersion (required)
   This defines the major version for the XML file format. GameSave.Info and MASGAU both make use of this to determine whether they are compatible with a particular format of an XML file, and whether it is possible for it to automatically update the file to a newer format. Major version changes are defined as changes that drastically alter the entire format of the file.
   
minorVersion (required)
   This is used in the same manor as majorVersion. Minor version changes are defined as changes that do not affect the file as a whole, but still can impact compatability with older versions of GameSave.Info or MASGAU.
   
revision (required)
   This is used in the same manor as minorVersion. Revisions are defined as changes that fo not affect the file or compatability, but still require a change to the schema file that defines the format.
   
updated (required)
   This is used by MASGAU's auto-update system to keep track of when a file was last updated.
   
xmlns:xsi (required)
   This lets the XML parser know that the file uses an XML Schema.

xsi:noNamespaceSchemaLocation (required)
   This tells the XML parser what the filename of the XML Schema is.
   
****
Child Elements
****

:doc:`game` (required)
   Defines the games for this file. GameSave.Info organizes games into files by the first letter of the game's name, but this is not a requirement of the format, only of GameSave.Info.


   
