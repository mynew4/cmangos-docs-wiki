Back to "world database":mangosdb_struct list of tables.

h2. The `locales&#95;quest` table

This table is used to provide to localized clients with localized string for quest templates.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"entry":Locales_quest#entry|int(11) unsigned|NO|PRI|0||
|"Title_loc1":Locales_quest#title_locx|text|YES||None||
|"Title_loc2":Locales_quest#title_locx|text|YES||None||
|"Title_loc3":Locales_quest#title_locx|text|YES||None||
|"Title_loc4":Locales_quest#title_locx|text|YES||None||
|"Title_loc5":Locales_quest#title_locx|text|YES||None||
|"Title_loc6":Locales_quest#title_locx|text|YES||None||
|"Title_loc7":Locales_quest#title_locx|text|YES||None||
|"Details_loc1":Locales_quest#details_locx|text|YES||None||
|"Details_loc2":Locales_quest#details_locx|text|YES||None||
|"Details_loc3":Locales_quest#details_locx|text|YES||None||
|"Details_loc4":Locales_quest#details_locx|text|YES||None||
|"Details_loc5":Locales_quest#details_locx|text|YES||None||
|"Details_loc6":Locales_quest#details_locx|text|YES||None||
|"Details_loc7":Locales_quest#details_locx|text|YES||None||
|"Objectives_loc1":Locales_quest#objectives_locx|text|YES||None||
|"Objectives_loc2":Locales_quest#objectives_locx|text|YES||None||
|"Objectives_loc3":Locales_quest#objectives_locx|text|YES||None||
|"Objectives_loc4":Locales_quest#objectives_locx|text|YES||None||
|"Objectives_loc5":Locales_quest#objectives_locx|text|YES||None||
|"Objectives_loc6":Locales_quest#objectives_locx|text|YES||None||
|"Objectives_loc7":Locales_quest#objectives_locx|text|YES||None||
|"OfferRewardText_loc1":Locales_quest#offerrewardtext_locx|text|YES||None||
|"OfferRewardText_loc2":Locales_quest#offerrewardtext_locx|text|YES||None||
|"OfferRewardText_loc3":Locales_quest#offerrewardtext_locx|text|YES||None||
|"OfferRewardText_loc4":Locales_quest#offerrewardtext_locx|text|YES||None||
|"OfferRewardText_loc5":Locales_quest#offerrewardtext_locx|text|YES||None||
|"OfferRewardText_loc6":Locales_quest#offerrewardtext_locx|text|YES||None||
|"OfferRewardText_loc7":Locales_quest#offerrewardtext_locx|text|YES||None||
|"RequestItemsText_loc1":Locales_quest#requestitemstext_locx|text|YES||None||
|"RequestItemsText_loc2":Locales_quest#requestitemstext_locx|text|YES||None||
|"RequestItemsText_loc3":Locales_quest#requestitemstext_locx|text|YES||None||
|"RequestItemsText_loc4":Locales_quest#requestitemstext_locx|text|YES||None||
|"RequestItemsText_loc5":Locales_quest#requestitemstext_locx|text|YES||None||
|"RequestItemsText_loc6":Locales_quest#requestitemstext_locx|text|YES||None||
|"RequestItemsText_loc7":Locales_quest#requestitemstext_locx|text|YES||None||
|"EndText_loc1":Locales_quest#endtext_locx|text|YES||None||
|"EndText_loc2":Locales_quest#endtext_locx|text|YES||None||
|"EndText_loc3":Locales_quest#endtext_locx|text|YES||None||
|"EndText_loc4":Locales_quest#endtext_locx|text|YES||None||
|"EndText_loc5":Locales_quest#endtext_locx|text|YES||None||
|"EndText_loc6":Locales_quest#endtext_locx|text|YES||None||
|"EndText_loc7":Locales_quest#endtext_locx|text|YES||None||
|"ObjectiveText1_loc1":Locales_quest#objectivetext1_locx|text|YES||None||
|"ObjectiveText1_loc2":Locales_quest#objectivetext1_locx|text|YES||None||
|"ObjectiveText1_loc3":Locales_quest#objectivetext1_locx|text|YES||None||
|"ObjectiveText1_loc4":Locales_quest#objectivetext1_locx|text|YES||None||
|"ObjectiveText1_loc5":Locales_quest#objectivetext1_locx|text|YES||None||
|"ObjectiveText1_loc6":Locales_quest#objectivetext1_locx|text|YES||None||
|"ObjectiveText1_loc7":Locales_quest#objectivetext1_locx|text|YES||None||
|"ObjectiveText2_loc1":Locales_quest#objectivetext2_locx|text|YES||None||
|"ObjectiveText2_loc2":Locales_quest#objectivetext2_locx|text|YES||None||
|"ObjectiveText2_loc3":Locales_quest#objectivetext2_locx|text|YES||None||
|"ObjectiveText2_loc4":Locales_quest#objectivetext2_locx|text|YES||None||
|"ObjectiveText2_loc5":Locales_quest#objectivetext2_locx|text|YES||None||
|"ObjectiveText2_loc6":Locales_quest#objectivetext2_locx|text|YES||None||
|"ObjectiveText2_loc7":Locales_quest#objectivetext2_locx|text|YES||None||
|"ObjectiveText3_loc1":Locales_quest#objectivetext3_locx|text|YES||None||
|"ObjectiveText3_loc2":Locales_quest#objectivetext3_locx|text|YES||None||
|"ObjectiveText3_loc3":Locales_quest#objectivetext3_locx|text|YES||None||
|"ObjectiveText3_loc4":Locales_quest#objectivetext3_locx|text|YES||None||
|"ObjectiveText3_loc5":Locales_quest#objectivetext3_locx|text|YES||None||
|"ObjectiveText3_loc6":Locales_quest#objectivetext3_locx|text|YES||None||
|"ObjectiveText3_loc7":Locales_quest#objectivetext3_locx|text|YES||None||
|"ObjectiveText4_loc1":Locales_quest#objectivetext4_locx|text|YES||None||
|"ObjectiveText4_loc2":Locales_quest#objectivetext4_locx|text|YES||None||
|"ObjectiveText4_loc3":Locales_quest#objectivetext4_locx|text|YES||None||
|"ObjectiveText4_loc4":Locales_quest#objectivetext4_locx|text|YES||None||
|"ObjectiveText4_loc5":Locales_quest#objectivetext4_locx|text|YES||None||
|"ObjectiveText4_loc6":Locales_quest#objectivetext4_locx|text|YES||None||
|"ObjectiveText4_loc7":Locales_quest#objectivetext4_locx|text|YES||None||


h3. Description of the fields

h4. entry

This entry must be the same as "quest&#95;template.entry":quest_template#entry and then the row will be used to provide localization support for this quest&#95;template record.

h4. Title&#95;locX

Translated content for "quest&#95;template.title":quest_template#title field for language X. See "localization languages":localization_lang list to know which value to use for X.

h4. Details&#95;locX

Translated content for "quest&#95;template.details":quest_template#details field for language X. See "localization languages":localization_lang list to know which value to use for X.

h4. Objectives&#95;locX

Translated content for "quest&#95;template.objectives":quest_template#objectives field for language X. See "localization languages":localization_lang list to know which value to use for X.

h4. OfferRewardText&#95;locX

Translated content for "quest&#95;template.OfferRewardText":quest_template#OfferRewardText field for language X. See "localization languages":localization_lang list to know which value to use for X.

h4. RequestItemsText&#95;locX

Translated content for "quest&#95;template.RequestItemsText":quest_template#RequestItemsText field for language X. See "localization languages":localization_lang list to know which value to use for X.

h4. EndText&#95;locX

Translated content for "quest&#95;template.EndText":quest_template#EndText field for language X. See "localization languages":localization_lang list to know which value to use for X.

h4. ObjectiveTextA&#95;locX

Translated content for "quest&#95;template.ObjectiveText":quest_template#ObjectiveText field for language X. See "localization languages":localization_lang list to know which value to use for X.
