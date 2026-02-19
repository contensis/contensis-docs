The entries listing screen provides comprehensive tools for viewing, searching, and filtering entries within your Contensis project. This guide explains how to effectively navigate and manage your content entries.

## Entries listing screen

Select **Entries** in the sidebar to open the *Entries* listing screen.

## Search and filter entries

If you have a large number of entries in your project, you may find it easier to use the filter panel to narrow down the number of entries displayed. The filter acts as a [faceted search](https://en.wikipedia.org/wiki/Faceted_search), building a search query based on the filters selected.

The entries you see in the entries listing and the options that are present in the filter panel are reflective of user permissions, based on the [roles](/help-and-docs/user-guides/governance/roles-and-permissions/roles-and-permissions-overview) to which a user is assigned.

### Search by keyword

Searching by keyword from the entry listing works in two ways. The search box has a checkbox labeled *Search title only* which is checked by default*.* When you enter a search term the title of the entry will be searched to locate the content you are looking for.

The keyword search can also be set to search all fields in your entry, allowing you to locate content that is more relevant to your search. This is helpful when you want to locate changes to an acronym or a name of something that could be located deep inside your content. Simply uncheck the *Search title only* checkbox to carry out a deeper search.

To begin searching, type your keyword into the search box and your results will update in the entries listing. The search query also takes into account any filters that are applied, such as *Content type* or *Language*.

### Filter by content type(s)

You can narrow down the number of entries displayed by changing the content type dropdown from *All content types* to one or more specific content types in the list, such as to show books and people.

### Filter by language

You can filter the entries by changing the language in the dropdown. If you have selected a content type then the list of languages will be reflective of those supported by the content type.

### Filter by content owner(s)

This filter allows you to see all content belonging to specific content owners. Content owners are defined in the properties panel of an entry. The content owner is usually the author that created the content.

### Filter by published status

The published filter reduces the entries listing to either entries that are published or those that are not yet published. Those that have been published are available to the [Delivery API.](/help-and-docs/apis/delivery-http)

### Filter by workflow status

Entries transition through different workflow states defined by their workflow. For example, in the approval workflow there are *Draft*, *Awaiting approval*, *Declined* and *Done* states.

When no content types are selected from the content type filter, the list of workflow states is reflective of the workflows that are in use.

If you filter to a specific content type, the states shown are based on the workflow of the selected type.

### Filter by schedules

An entry can have different schedules applied that result in the entry being published or unpublished. You can view entries that have a *Publish schedule*, an *Unpublish schedule* or a *Missed publishing schedule* by using the filters.

### Translation status

If you have any entries that are available in multiple languages then the translation status filters are shown. The filters allow you to filter entries to those which are *Available to translate* – meaning the default language has been published – and those which are *Not available to translate,* meaning the default language is not currently published.

## Reset filters

You can easily reset any filters that you have set by pressing the **Reset filters** link at the top of the filter panel. Reloading the entries listing from the sidebar have the same effect.