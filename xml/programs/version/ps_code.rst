====
<ps_code />
====

<game name="BrutalLegend">
    <title>BrÃ¼tal Legend</title>
    <version os="PS3" region="USA">
        <ps_code prefix="BLUS" suffix="30330"/>
        <contributor>GameSave.Info</contributor>
    </version>
</game>
PlayStation Games are considered just another version of the base game, and are marked with an OS matching the PlayStation platform (PS1, PS2, PS3, PSP). Instead of "locations", "files" (and the optional "identifier"), you only specify the game's PlayStation code, which can usually be found on the game disc and case. Each disc (even within the same game) usually has a unique code, 4 letters then 5 numbers. This code is used in the name of a game's saves. Like file tags, you can sepcify a type on a PlayStation Code

For console games you should include the region code, as almost all console saves are guaranteed to be incompatible with those from other countries.

Some more modern PS3 games keep multiple save files for different types of data, sometimes seperating out Profile or setting data. Usually these saves wil have extra letters appended to the name. You can specify these with the append tag, as shown in this example from Tomb Raider: Anniversary:

<ps_code prefix="BLUS" suffix="30718" append="-TALIST"/>
<ps_code prefix="BLUS" suffix="30718" append="-TAPROFILE" type="Profile"/>
Usually you would want to accompany an append with an appropriate type. Having a code with an append will NOT indicate that it should be excluded from other types, so make sure each code entry will indicate a unique entry.