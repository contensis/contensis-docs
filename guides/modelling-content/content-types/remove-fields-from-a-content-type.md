If you no longer require a field within a content type, it can be removed in the following way:

1.  With the content type opened for editing, locate the field that you want to remove.
2.  Select the more actions button for the field, indicated by the triple dot icon.
3.  Press **Remove field** from the menu to remove it from the content type. A *Delete field* confirmation screen will be displayed.
4.  Press **Delete**, then **Save**, followed by **Publish** to confirm your changes.

## Field removal behaviour

The data associated with the removed field for an entry is preserved until the entry is updated and saved.

Any code created referencing the removed field would return null or the default value for the type through the Delivery API.