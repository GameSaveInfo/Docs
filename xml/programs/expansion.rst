====
<expansion>
====

****
Example
****

.. code-block:: xml

  <expansion name="MechWarrior4BlackKnight" for="MechWarrior4Vengeance">
    ...
  </expansion>

****
Description
****
 
Use this if the entry is for an expansion pack, add-on or DLC for another game. In this example, Mechwarrior 4: Black Knight is an expansion for MechWarrior 4: Vengeance. The "for" attribute is required for an expansion, and MUST reference another game in the XML file. "Stand-alone expansions" do NOT get to be marked as an expansion. The term is an oxymoron, and makes no sense.


****
Attributes
****

.. include:: <common_attributes.rst>

for
   Designates the name of the game that the expansion is for. This allows GameSave.Info to establish links between expansions and the base game.

****
Child Elements
****

.. include:: <common_children.rst>

****
Parent Element
****

:doc:`programs`
   Root element that contains all program-type elements.