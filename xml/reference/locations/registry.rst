====
<registry />
====


Location Using A Registry Key

<registry root="local_machine" key="SOFTWARE\Unreal Technology\Installed Apps\Deus Ex" value="Folder"/>
The registry element lets you specify a registry key that contains the path to a game's saves. For thsoe not in the know, Windows keeps what is called a registry, and it's basically a fancy collection of names and value. If you click Start, Run then type in regedit, you'll be able to browse it. Windows keeps all of its settings, and the install locations of a lot of programs here, which means we can take advantage of it to find a game, but it's pretty much only useful for games that keep their saves in the isntall folder. The root of a key indicates which registry root will be used. Windows has several, here are what's available:

classes_root - I don't know
current_user - The registry for the currently logged in user
current_config - The registry for Windows' settings
dyn_data - I don't know
local_machine - The registry for the computer as a whole
performance_data - I don't know
users - The registry for all the users
The key is like a folder path, pointing to the location of the key in the registry root (browse around regedit, it'll make sense). A key can have several values, one default and zero or more named values. If you ommit the value attribute, the default one will be used, otherwise only a value matching the name you provide will be used.

There is one caveat on 64-bit systems. On these systems, Windows places the registry keys for 32-bit programs (which most games are) inside of a special folder, seperate from the 64-bit programs. For instance Deus Ex's registry entry on a 32-bit system would be:

SOFTWARE\Unreal Technology\Installed Apps\Deus Ex
But on a 64-bit system it would be placed in:

SOFTWARE\Wow6432Node\Unreal Technology\Installed Apps\Deus Ex
The policy right now is to write entries WITHOUT the Wow6432Node. Adding the node is trivial, so this way is more compatible.

Registry keys frequently can make use of the append and detract attributes available to all location elements. See the section below for more details.