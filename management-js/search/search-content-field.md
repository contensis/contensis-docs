1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Management API](https://www.contensis.com/help-and-docs/apis/management-js)
4.  Search

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 25 September 2024

When we index entry content into Elastic, a special field is generated called the [*searchContent*](https://www.contensis.com/help-and-docs/whats-new/breaking-changes/search) field.  
The field is a long string of content from all text fields in an entry, including composer content. It also includes the content from the *entryTitle* and *entryDescription* fields of linked entries.

This field isn't returned by the Management API as it is essentially one big string to make searching content more efficient and easier for developers.

JSON

```
{
    title: "Meet a brighter and bolder Contensis",
    summary: "Contensis product owner, Richard Saunders will be looking at the latest Contensis updates.",
    introduction: "Join Richard Saunders our Contensis product owner and learn about all that’s new in Contensis 14.",
    searchContent: "Meet a brighter and bolder Contensis Contensis product owner, Richard Saunders will be looking at the latest Contensis updates. Join Richard Saunders our Contensis product owner and learn about all that’s new in Contensis 14. formWebinarSignUp https://www.gotomeeting.com/en-gb 45 <p>You&rsquo;ll discover how we&rsquo;re making Contensis more accessible.</p> <p>How to control what you see in the entry listing with managed columns.</p> <p>How to understand how your entries are connected.</p> <p>You&rsquo;ll learn how to find and locate content within entry searching.</p> <p>Plus get an Introduction of the Workflow API.</p> <p>Richard shares all that&rsquo;s new in Contensis. An updated accessible interface, a richer understanding of how your content is used, along with new ways of searching and managing the content you work with every day.</p> An illustration of a man on a laptop Illustration=Product release Richard Saunders Richard is the product owner for Contensis – our CMS. He sets the direction and roadmap for the product. His background includes both user experience and front-end design. https://calendar.google.com/calendar/u/0/r/eventedit/copy/MmY3N2RpNGdtNDc5bmI2anBrNWg0NnY5NGcgci5icm9tbGV5QHplbmdlbnRpLmNvbQ/Zi5iZWF2YW5AemVuZ2VudGkuY29t?sf=true invite new E-commerce Emergency services Government Higher education A high-level educational institution in which students study for degrees and academic research is done Local government Manufacturing Accessibility basics part 1 – an introduction to WCAG 2.1 Why is it so important to make a website accessible? Jon Maskrey takes a look at who benefits from accessible websites, UK accessibility laws, and the implications of WCAG 2.1. Developing with ARIA to help make your web application accessible Accessible Rich Internet Applications or ARIA, is a specification created to make interactive content accessible. Learn how to make your website accessible using ARIA roles. Meet a brighter and bolder Contensis Join Richard Saunders our Contensis product owner and learn about all that’s new in Contensis 14. An illustration of a man on a laptop Contensis release",
}
```

You can see in the example how the *title*, *summary* and *introduction* fields, along with the rest of the text fields, get merged into one long string in the *searchContent* field.

You can query against the *searchContent* field using the following search operators:

-   contains
-   startsWith
-   endsWith
-   between

Here is an example of querying this field using our Management API. The main use case for the `searchContent` field is when you are querying multiple content types that could have different text fields that make up the main body copy of an entry, such as in a site-wide search.

## JavaScript example

JavaScript

```
(function(Zengenti) {

    var client = Zengenti.Contensis.Client.create(clientConfig);
    var Query = Zengenti.Contensis.Query;
    var Op = Zengenti.Contensis.Op;

    var query = new Query(
        Op.contains('searchContent', 'Batman'),
        Op.greaterThan("runtime", 200) 
    );

    client.entries.search(query).then(function(films) {
        // films are available
        // films.pageIndex
        // films.pageSize
        // films.totalCount
        // films.items

    }, function(error) {
        console.error(error);
    });

})(Zengenti);
```

If you wish to query the contents of assets such as PDFs and Word documents, then the field id is `_searchContent`.