Back to "world database":mangosdb_struct list of tables.

h2. The `questgiver_greeting` table

Contains special text displayed by some creatures/objects which have NpcFlag 2 (questgiver), but not NpcFlag 1 (gossip).
Unlike normal gossip texts, these texts cannot be found in tables such as "npc_text":Npc_text or broadcast_text.
This data is found within the SMSG_QUESTGIVER_QUEST_LIST packet in sniffs.

h3. Structure

|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"Entry":questgiver_greeting#Entry|int(11) unsigned|NO|PRI|0||
|"Type":questgiver_greeting#Type|int(11) unsigned|NO|PRI|0||
|"Text":questgiver_greeting#Text|longtext|YES||||
|"EmoteId":questgiver_greeting#EmoteId|int(11) unsigned|NO||0||
|"EmoteDelay":questgiver_greeting#EmoteDelay|int(11) unsigned|NO||0||

h4. Entry

Entry of questgiver - either "creature_template.entry":https://github.com/cmangos/issues/wiki/creature_template#entry or "gameobject_template.entry":https://github.com/cmangos/issues/wiki/gameobject_template#entry.

h4. Type

Accepted values: 0 or 1.
If value = 0, then Entry must be a creature.
If value = 1, then Entry must be a gameobject.

h4. Text

Text of the greeting.

h4. EmoteId

Emote ID to be played as text greeting is displayed.

h4. EmoteDelay

Delay before EmoteId is played.