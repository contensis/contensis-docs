1.  [Help and docs](/help-and-docs)
2.  [User guides](/help-and-docs/guides)
3.  [Authoring and managing content](/help-and-docs/guides/authoring-and-managing-content)
4.  Entries

[Log in to add to favourites](/account/login)

Page last updated 10 December 2024

## On this page

-   [Create an entry for a specific language](#create-an-entry-for-a-specific-language)
-   [Adding additional language variations](#adding-additional-language-variations)

You can create an entry in a language that is not the default language for your project, outside of the normal [translation workflow](/help-and-docs/user-guides/authoring/entries/translate-an-entry). This could be useful where the content is applicable only to a specific locale or you want to display a variation of a language, such as a dialect.

For a product that is available worldwide, product entries would normally be created for all languages. However, you may have a product that is specific to a country or region, where the default and other languages may not be required. In this situation, you'll need to create an entry for a specific language.

## Create an entry for a specific language

Creating content in specific languages requires a user to be a member of an appropriate role that has support for the required language.

1.  Press the dropdown next to the *New entry* button. A menu will open.
2.  Select the **New entry (other language)** option. A list of content types will be displayed.
3.  Choose the content type you want to create an entry from. You'll be taken to a list of available languages for that content type.
4.  Select the required language.
5.  A new entry will be created and the selected language variation will open for editing.
6.  You can now populate the fields for the new language.
7.  Press **Save** after any changes – the minor [version](/help-and-docs/user-guides/authoring/entries/entry-versioning) will increment upon each save. When you have finished, press **Submit** to send the entry for approval, or **Publish** if the workflow allows. Once approved and published the language variation will now be available through the [Delivery API](/help-and-docs/apis/all-apis), without requiring the default language.

## Adding additional language variations

In the scenario outlined at the beginning of this article, we mentioned a product specific to a country or region. Over time, you may find that the product (or other type of entry) may need to be made available in one or more other languages.

In this case, you'll need to locate the entry in the entry listing screen for the language the entry was created against and follow the steps below to add additional languages to the entry.

![](/image-library/resources-images/entry-language-outside-workflow-cropped-1135x432.x2f1828cc.png?q=80&f=webp)

1.  In the entries listing screen, press the **Show other languages** link to open the language panel.
2.  The panel states will differ slightly to those shown when translating an entry from the default language. For example, you'll see a *Create* button instead of *Translate*, and states including *No default langauge* in place of *Not yet translated*.
3.  From the language panel, press **Create** on a language which has not yet been created. The language variation will open.
4.  You can repeat this process for each subsequent language.

Although language variations are part of the same entry, each variation is independent of other languages. This is true until the default language is created and published, at which point the translation workflow activates, and language variations are no longer independent of one another.

Note: The languages in which an entry can be created are determined by those which have been assigned to a project and enabled for a [content type](/help-and-docs/user-guides/content-modelling/content-types/enable-or-disable-languages-for-a-content-type "Enable or disable languages for a content type").

## On this page

-   [Create an entry for a specific language](#create-an-entry-for-a-specific-language)
-   [Adding additional language variations](#adding-additional-language-variations)