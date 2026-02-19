1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Delivery API](/help-and-docs/apis/delivery-js)
4.  Entries
5.  Search

[Log in to add to favourites](/account/login)

Page last updated 13 November 2024

Composers are typically used by editors to create body in content types such as blogs. It's not unusual to see 30+ fields used for some body content and some of these may be components, which in turn have multiple fields.

Ideally we need to keep this number to be less than 1,000 so that it doesn't affect search performance. To do this, composer fields are mapped as a flattened type which means you can still use certain operators but without the need to map each field.

In general, you should not use composer fields for data that you filter on to produce searches or listings. It is preferable to use components and/or repeating fields where you want to store repeated or structured data that you will then filter on. You can of course [search all the content of a composer (and other text fields)](/help-and-docs/apis/delivery-dotnet/search/search-content-field) using the `searchContent` field.

With Contensis versions 14 and older, you can still search all the items in the composer field using the following search [operators](/help-and-docs/apis/delivery-js/entries/search/query-operators):

-   contains
-   startsWith
-   endsWith
-   between