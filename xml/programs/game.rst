.. highlight:: xml

<game>
====

****
Example
****

.. code-block:: xml

   <game name="DeusEx">
     ...
   </game>

****
Description
****

Each game is defined within a program element. There are four types of program elements:

#. <game>
#. <expansion>
#. <mod>
#. <system>

The main purpose of this tag is to provide a unique internal name for the game. This unique name must follow these rules:

#. No spaces, and no symbols. 
#. Use `CamelCase <http://en.wikipedia.org/wiki/CamelCase>`_ for legibility. 
#. Always use numbers instead of `roman numerals <http://en.wikipedia.org/wiki/Roman_numerals>`_ (or other representations of numbers), for sorting purposes. 
#. All versions of a game go under the same game tag. For example, the Deus Ex game tag contains a version for both Windows and PlayStation 2.

There are actually several variations on this tag, and you should try to use the one appropriate for your entry:

<expansion name="MechWarrior4BlackKnight" for="MechWarrior4Vengeance">
Use this if the entry is for an expansion pack, add-on or DLC for another game. In this example, Mechwarrior 4: Black Knight is an expansion for MechWarrior 4: Vengeance. The "for" attribute is required for an expansion, and MUST reference another game in the XML file. "Stand-alone expansions" do NOT get to be marked as an expansion. The term is an oxymoron, and makes no sense.

<mod name="NamelessMod" for="DeusEx">
Use this if the entry is for an MOD for another game. In this example, The Nameless Mod is a MOD for Deus Ex. The "for" attribute is required for a MOD, and MUST reference another game in the XML file.

<system name="GamesForWindows">
Use this when describing system data.

There is a completely optional "follows" attribute that can be added to any of these variations:

<game name="DeusExInvisibleWar" follows="DeusEx">
It basically just indicates that the entry is somehow a follow-up (or sequel) to the indicated other entry. It's not parsed or used anywhere yet, but one day maybe.


If a game is marked as deprecated, it means that the i. 

Obviously your closing tag should match your opening tag. Other than this, the contained tags are all the same.

****
Attributes
****

deprecated (boolean) (optional)
   Marks a game as deprecated, meaning that the information provided is no longer considered correct. This allows the data to be kept for posterity and backwards-compatability.
.. code-block:: xml

   <game name="DeprecatedGame" deprecated="true">

****
Child elements
****

:doc:`title` (required)
   Defines the title for the game. This title will be used for all versions of the game, except for those that have an explicitily defined title.

****
Parent element
****

:doc:`programs`
   Root element that contains all program-type elements.