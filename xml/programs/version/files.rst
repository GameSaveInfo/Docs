====
<files>
====

Now we get to the nitty-gritty of specifying which files are saves, settings, etc. After the locations element's closing tag, we can specify one or more "files" elements, specifying and sorting these files by type.

Types

<files>
<files type="Settings">
Each "files" element has an optional "type" attribute. This tells us what type of files are going to be specified within the files tag. It could also be "Settings", "Profiles", or anything else. The attribute isn't constrained, so you can be as accurate as necessary. When possible, try to conform to existing type names, so there can be some semblence of consistency, but if it absolutely needs to be a new type name, go for it.

Files To Save

<files>
    <include path="Save"/>
</files>
Within each files element, we specify one or more "save" elements that describe the files. There are three attributes used to specify files:

path - This specifies the folder path (starting at the end of the locations found from the above sections' specifications). This can use wildcards (like SAVE*)
filename - This specifies the name of the files. This can also use wildcards, like *.sav
modified_after - This specifies a time and date that the file must be modified after in order to qualify
Different combinations of path and filename have different meanings:

If no path or filename are specified, then that means ALL the files in ALL the folders in the location.
<include />
If only a path is specified, then that means all the files in that folder, but NOT the subfolders.
<include path="Save" />
If only a filename is specified, then that means all the files matching that name in the location, but NOT the subfolders.
<include filename="*.sav" />
If a path and a filename are specified, then that means all the files matching the name in that specific folder, but NOT the subfolders.
<include path="System" filename="*.ini"/>
The modified_after date is formatted as follows:

<include path="Data\Campaigns" modified_after="2001-10-09T00:00:00"/>
Except For...

<include path="userdata">
  <exclude path="userdata\mp3"/>
</include>
To make things easier, you can specify a very broad save definition, and refine it using one or more "except" elements under that save element. This element can use all the same tags as the "save" element, and they all work exactly the same, except the deselect files instead of selecting them.