====
shortcut element
====

<shortcut ev="startmenu" path="Programs\Deus Ex\Play Deus Ex.lnk" detract="System"/>
Quite frequently there is a shortcut in the Start menu, or on the desktop, or somewhere else, that points to the install folder of a game. If the game keeps its saves in the install folder, then this is yet another way we can use to find them! The ev attribute here supports the same values as the path element described above, but you'll pretty much always be using startmenu. From there you provide the path to the shortcut, easy peasy!

As shown in the example, this tag can also take advantage of the append and detract attributes, which are explained in a later section.