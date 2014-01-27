====
Creating the XML file
====

For the most part, you don't need to create an XML file from scratch. Just check out the data files from the repo and edit the ones already there. All GameSave.Info files must start with a standard XML declaration:

.. code-block:: xml
   <?xml version="1.0" encoding="UTF-8"?>
   
The encoding attribute is important. Due to needing to support many non-ASCII characters, GameSave.Info XML files must all be encoded in UTF-8.
   
