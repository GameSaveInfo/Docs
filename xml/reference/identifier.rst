====
<identifier />
====

<identifier path="Save" />
Some games aren't consistent about where their saves are. For example Peggle will store its setting in its install folder under XP, but under ProgramData under Vista and 7. This means that both must be specified in the XML file, leading to confusion if both are detected. The identifier tag is a way of telling for sure that we've got the right location. It can use the exact same attributes as a "save" element (described above).

In Peggle's case we'd specify

<identifier path="userdata" />
because only the right location will have a userdata folder in it. It would probably be best for every game to have one of these, but the only ones that absolutely need it are ones that can have multiple locations, or if you need to distinguish between two versions of a game (such as with The Longest Journey's 2-disc and 4-disc variants).