====
Creating the XML file
====



For the most part, you don't need to create an XML file from scratch. Just check out the data files from the repo and edit the ones already there. But, if you're curious as to the purpose of the root tags in the file, here's an explanation:

.. highlight:: xml
All GameSave.Info files must start with a standard XML declaration::

   <?xml version="1.0" encoding="UTF-8"?>
   
The encoding attribute is important. Due to needing to support many non-ASCII characters, GameSave.Info XML files must all be encoded in UTF-8.
   
.. highlight:: xml
The root tag is called "programs". This is because a GameSave.Info XML file may contain data for mor than jsut games, it can also contain definitions for game-related utilities::
      
   <programs majorVersion="2" minorVersion="0" revision="2" updated="2013-06-15T13:45:04" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="GameSaveInfo202.xsd">

There are a number of attributes:

majorVersion
   This defines the major version fo the XML file format. GameSave.Info and MASGAU both make use of this to determine whether they are compatible with a particular format of an XML file, and whether it is possible for it to automatically update the file to a newer format. Major version changes are defined as changes that drastically alter the entire format of the file.
   
minorVersion
   This is used in the same manor as majorVersion. Minor version changes are defined as changes that do not affect the file as a whole, but still can impact compatability with older versions of GameSave.Info or MASGAU.
   
revision
   This is used in the same manor as minorVersion. Revisions are defined as changes that fo not affect the file or compatability, but still require a change to the schema file that defines the format.
   
updated
   This is used by MASGAU's auto-update system to keep track of when a file was last updated.
   
xmlns:xsi
   This lets the XML parser know that the file uses an XML Schema.

xsi:noNamespaceSchemaLocation
   This tells the XML parser what the filename of the XML Schema is.
   
Aside from all that, the format requires that at least one game-type element (see next page) be defined per file, and that the file end with a closing programs tag:

   ``</programs>``
