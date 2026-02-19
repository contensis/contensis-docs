1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [User guides](https://www.contensis.com/help-and-docs/guides)
3.  [Authoring and managing content](https://www.contensis.com/help-and-docs/guides/authoring-and-managing-content)
4.  Entries

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 10 December 2024

## On this page

-   [Location options](#location-options)

You can use the *Set a location* option within the entry editor to determine where the content should be available in your site.

You'll only be able to set a location for an entry if you are a member of the *Site View Administrators* group.

1.  Press the **Entries** button in the sidebar to open the *Entries listing* screen.
2.  Press the title in the listing of the entry you want to edit. Alternatively, create one from the *New entry* button in the toolbar. The *Entry Editor* screen will open.
3.  Press the **Set a location** link at the bottom of the editor and the *Set an entry location* window will be displayed.
4.  You can navigate to the location you want the entry to be available from by using the tree explorer in the left-hand pane. The selection you make determines what options are displayed.
5.  Once you've made your selection, press **Apply** to save the entry at the selected location. Once the entry has been published the entry will be available at the specified URL.

## Location options

The following options are displayed in the *Set an entry location* window and are described with examples:

### Create a new location

This option saves the entry, e.g. *Danny the Champion of the World,* to a location within the selected node. If you selected`/books/`,the book would be created inside`/books/`.

Markdown

```
-- books
    --charlie-and-the-chocolate-factory
    --james-and-the-giant-peach
    --danny-the-champion-of-the-world       <-- New book added to /books/
```

### Assign to an existing location

This option assigns the entry to a node that has already been created in your site structure.

The location is either a parent node/folder or child node that doesn't currently have an entry attached.

#### Parent node/folder

Parent nodes are usually reserved for listing content, or the homepage of a section. They usually summarise the section content. In this example the entry will be assigned to the node `books`, so the entry will be available at www.mywebsite.com/books/.

Markdown

```
-- books                                     <-- entry is saved to this location
    --charlie-and-the-chocolate-factory
    --james-and-the-giant-peach
    --danny-the-champion-of-the-world
```

When an entry is saved at a parent/folder location it is not possible to change the slug or display name as this will affect all content held under it.

#### Child node

If someone has set up the information architecture for your site before you've created your content, you may find that you want to set an entry at an existing location that does not have an entry attached to it.

`-- top-10-books-of-2019`

In this scenario you may have created an entry called Our top 10 reads of 2019 with a collection of the best books of 2019 that need to be displayed at a specific URL.

## On this page

-   [Location options](#location-options)