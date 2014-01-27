====
<locations>
====

Games can keep their saves anywhere, so here we try to provide as many ways as possible of finding them. These locations are not the exact locations of the saves, but are instead roots used as the first step to find the saves. Why do we do it like this? Here's why:

These are some possible save locations for Deus Ex:	See how they're all different, but all end with the same Save folder? 
We can be certain that the Save folder is always used, no matter the location,
and just specify the part of the path that we can't predict:
C:\DeusEx\Save\	C:\DeusEx\
C:\Program Files\GOG.com\Deus Ex\Save\	C:\Program Files\GOG.com\Deus Ex\
C:\Program Files\Steam\steamapps\common\deus ex\Save\	C:\Program Files\Steam\steamapps\common\deus ex\

The main point here is to not store the same information (the Save folder) more than once. This has space saving advantages, but it also allows us to re-use the same location to specify Settings, Replays, Screenshots, or anything else that might happen to be there. We must be mindful to include enough of the root path that we can't mistake one game's paths for another. We have a few ways of finding these locations:

.. toctree::
   :maxdepth: 2
   :glob:

   locations\attributes
   locations\parent
   locations\path
   locations\registry
   locations\shortcut
