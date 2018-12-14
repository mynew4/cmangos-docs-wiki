Back to "world database":mangosdb_struct list of tables.

h2. The `mail&#95;level&#95;reward` table

This table holds information on sent mails when a character levels up. Can be specified by raceMask.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"level":Mail_level_reward#level|tinyint(3) unsigned|NO|PRI|0||
|"raceMask":Mail_level_reward#racemask|mediumint(8) unsigned|NO|PRI|0||
|"mailTemplateId":Mail_level_reward#mailtemplateid|mediumint(8) unsigned|NO||0||
|"senderEntry":Mail_level_reward#senderentry|mediumint(8) unsigned|NO||0||
||


h3. Description of the fields

h4. level

Send mail when a character reaches this level.

h4. raceMask

Only these races are considered.

h4. mailTemplateId

Reference to "MailTemplate.dbc.":MailTemplate.dbc. Containing mail text and subject.

h4. senderEntry

Sender of mail. Reference to "creature&#95;template.entry":creature_template#entry.
