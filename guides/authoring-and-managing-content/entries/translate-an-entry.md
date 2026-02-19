Translating an entry follows a common language workflow. Entries can only be translated into another language once there is a published version of the default language. This workflow ensures that as the default language entry is updated, authors of different languages will see that a change has been made. The change will be highlighted by the entry's workflow state, such as when an entry has *Never been translated*.

**Note**: We consider the default language as the common business language used in a project, from which all other languages are translated.

All language variations are associated with a default language entry. The default language entry acts as a container for all language variations (the default language is always the same as the default language of a project). The number of languages available for a given entry will depend on those supported by the [content type](/help-and-docs/user-guides/content-modelling/content-types/enable-or-disable-languages-for-a-content-type).

After an entry has been created and published in the default language, each language variation will become available for translation.

## Translate an entry from the language panel

1.  Press the **Entries** button in the sidebar to open the *Entries* listing screen. You can reduce the number of entries displayed using the *Type filter*. The entry listing will update to show all entries for the content type you've selected.
2.  Locate the entry requiring translation in the listing. If the entry is available in other language variations you will see *Show other languages* in the language column of the listing. Press **Show other languages**. The language panel will be displayed.
3.  The language panel shows all language variations for the entry. Entries awaiting translation will have an action to translate, whilst those already translated will be available to edit. Pressing **Translate** or **Edit** will open the entry in a split view entry editor for translation.
4.  You can now populate the fields for the new language. The *copy field* option can be used to quickly copy content from one language to the language variation where content remains the same.
5.  Press **Save** between any changes – the minor [version](/help-and-docs/user-guides/authoring/entries/entry-versioning) will increment upon each save. When you have finished, press the **Submit** or **Publish** button. Once published the language variation will be available through the Delivery API, together with the default language content.

**Note**: In the split view entry editor, the left-hand panel displays the default language content unless the language has been changed in the dropdown. The other panel represents the language you are currently editing.