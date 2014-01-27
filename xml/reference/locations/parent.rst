====
parent element
====

Location Using Another Game

<expansion name="MechWarrior4BlackKnight" for="MechWarrior4Vengeance">
    <title>MechWarrior 4: Black Knight</title>
    <version os="Windows">
      <locations>
        <registry root="local_machine" key="SOFTWARE\Microsoft\Microsoft Games\MechWarrior Black Knight" value="EXE Path"/>
        <parent name="MechWarrior4Vengeance" os="Windows"/>
      </locations>
      <files type="Mechs">
        <include path="resource\Variantsx"/>
      </files>
      <files>
        <include path="resource\Pilotsx"/>
      </files>
      <files type="Settings">
        <include filename="optionsx.ini"/>
      </files>
      <identifier filename="optionsx.ini"/>
      <contributor>GameSave.Info</contributor>
    </version>
</expansion>
If the game shares its save location in any way with another game, we can specify that game as a location source. More specifically, we specify a specific version of the game to take locations from. We specify the name of the game, along with all the version attributes of the version we want. These version elements MUST match a game version that is in the XML file.

This also allows you to create entries whose detection is dependent on the detection of another game.

Quite often this will need to make use of the append and detract attributes, as well as the identifier element, all of which are explained later.