Back to the "characters database":charactersdb_struct list of tables.

h2. The `character&#95;ticket` table

Holds ticket information from tickets written through the client help request -function.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"ticket_id":Character_ticket#ticket_id|int(11)|NO|PRI|None|auto&#95;increment|
|"guid":Character_ticket#guid|int(11) unsigned|NO||0||
|"ticket_text":Character_ticket#ticket_text|text|YES||None||
|"ticket_category":Character_ticket#ticket_category|int(1)|NO||0||
|"ticket_lastchange":Character_ticket#ticket_lastchange|timestamp|NO||CURRENT&#95;TIMESTAMP||


h3. Description of the fields

h4. ticket&#95;id

A unique ticket ID.

h4. guid

The GUID of the character sending the ticket. See "character.guid":character#guid

h4. ticket&#95;text

The ticket description text; the text written by the player in describing the problem.

h4. ticket&#95;category

The ticket category:

<table>
<caption>Ticket Categories</caption>
<thead>
<tr class="header">
<th align="left">ID
</th>
<th align="left">Category
</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">0
</td>
<td align="left">Item
</td>
</tr>
<tr class="even">
<td align="left">1
</td>
<td align="left">Behavior/Harassment
</td>
</tr>
<tr class="odd">
<td align="left">2
</td>
<td align="left">Guild
</td>
</tr>
<tr class="even">
<td align="left">3
</td>
<td align="left">Character
</td>
</tr>
<tr class="odd">
<td align="left">4
</td>
<td align="left">Non-quest/Creep
</td>
</tr>
<tr class="even">
<td align="left">5
</td>
<td align="left">Stuck
</td>
</tr>
<tr class="odd">
<td align="left">6
</td>
<td align="left">Environmental
</td>
</tr>
<tr class="even">
<td align="left">7
</td>
<td align="left">Quest/Quest NPC
</td>
</tr>
<tr class="odd">
<td align="left">8
</td>
<td align="left">Account/Billing
</td>
</tr>
</tbody>
</table>

h4. ticket&#95;lastchange

Stores the time when this ticket was last changed.
