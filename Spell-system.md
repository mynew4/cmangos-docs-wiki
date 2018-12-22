Spell in cMaNGOS is the essential object which is used for most purposes.

Each Spell has up to three effects, which have generic behaviour, determined by values in spell.dbc and then custom behaviour, that is scripted either using C++ or dbscripts_on_spell (this is restricted to DUMMY, SCRIPT_EFFECT spell effects).

Spell script can be anything ranging from triggering additional spells under certain conditions, to restricting targets of given spell.

Spell.dbc - is the source of spell definitions. Tells us what effects/values/targets etc a given spell has.  
Description of [Spell.dbc](Spell.dbc)

Triggered spells - There are 3 main kinds of triggered spells:
1. Event/AI triggered
2. Triggered by another spell (arcane missiles)
3. Triggered by aura (Talents/Blizzard)
Triggered spell setting influences many aspects of given spell. It skips cast time, cooldown checking, can target unselectable targets and more. Also these three kinds heavily influence PROCs, meaning in case of wrong usage, spells tend to not proc properly among other things (namely skipping safety checks).

NOTE: Work in progress - Author - Killerwife
