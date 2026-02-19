Contensis is a new kind of CMS. It combines the best features of a headless CMS and a traditional system to make it easy for your teams to create, manage and publish multilingual content to any platform. Its features and tools focus on the requirements of modern content teams:

-   Modelling content
-   Authoring content
-   Governing content

## Modelling content

In Contensis you structure the kinds of content you want to create using [content types](/help-and-docs/user-guides/content-modelling/content-types). You can think of this as building a user interface for authors in content teams to create a specific kind of content. Authors then use these content types to create individual items of content called [entries](/help-and-docs/user-guides/authoring/entries/entries-overview).

A content type is created in the default language of a project. If you have a multilingual license key, other languages supported by the project can be enabled for each content type you create.

You create content types by adding [fields](/help-and-docs/user-guides/content-modelling/field-editors/supported-fields-and-editors). Authors use these fields to add the individual pieces of content that make up an entry. The content type builder includes a variety of field types – from integers to images. Some fields provide more than one editor to allow you to specify different data formats. For example, a list field can be displayed as a set of radio buttons or a drop down list.

Assigning specific field editors ensures that authors enter content accurately and in the format you need for your projects. It also takes the guesswork out of creating content. To further ensure that authors create high quality content, different field editors allow you to specify a variety of [validation](/help-and-docs/user-guides/content-modelling/validation/validation-overview) methods.

Say we’re running an online houseplant store. We might have a content type called *Plant* to store all of the information about the plants on sale. This could include the common name of the plant, its latin name, genus, a description, care information, photo, price, and so on. We would then use the *Plant* content type to create an entry for each variety of plant, such as *Moth Orchid* or *Parlour Palm*.

When you want to create a group of fields that are frequently used together you can create a [component](/help-and-docs/user-guides/content-modelling/components/components-overview). Components are groups of fields you can add to your content types. For example, an address component could be a set of text fields for capturing a house number, street name, county, postcode, and country. Components are created using the component builder and are available to add to any content type builder once published.

While we’re modelling the content for our houseplant store we decide to expand our product range and start selling pots for our plants. Many of the fields in our *Plant* content type – such as latin name, genus, and care information – don’t apply to pots and other accessories. So, we need to create a new content type for *Pots.*

However, the product name, description, price and photo are all fields that we want to display for our plants, pots, and any other products we add in the future. We also want them to be in the same format and subject to the same validation so they are consistent across our product range.

So, we create a new component called *Product information* to replace the relevant fields in our *Plant* content type and also add it to our new *Pot* content type. 

You can create sophisticated content models by creating relationships between entries using the [Entry field](/help-and-docs/user-guides/content-modelling/field-editors/entry-field). This important field allows you to link existing entries in other content types to the current entry that is being authored. When adding this field in the content type builder you can limit the field to only allow entries from a specific content type, or allow authors to link an entry from any content type in your project. You can also allow authors to create new entries inline if the entry they need doesn’t exist.

We’ve decided to promote matching pots alongside our plants. To do this we’ll add an Entry field – let’s call it “Matching pots” – to our *Plant* content type and set it to accept multiple entries from the *Pot* content type. Now when an author creates an entry for a plant they can select one or more entries for complementary pots to display alongside the plant. This creates a relationship between the entries and allows us to cross-sell the plants and pots anywhere on our site.

When you want authors to be able to insert the same field multiple times you can either use [repeatable fields](/help-and-docs/user-guides/content-modelling/repeatable-fields/repeatable-field-overview) to allow an author to add the same field more than once, or use a [composer](/help-and-docs/user-guides/content-modelling/field-editors/composer-field) to let authors build up content using a limited number of fields you have specified.

A composer field editor enables you to create multiple blocks of content within a single field.

When you add a composer field to a content type, you are setting up a container for supported fields. You add the fields you want the composer to support in the same way you would normally add fields to a content type. Authors then choose from these fields and add them in the order they need to build rich content. A composer field provides a richer editing experience for an author when used for areas like blogs, articles, and landing pages.

Let’s add a blog to our houseplant store to to give tips on choosing and caring for houseplants and to help promote our great range of plants and pots. We’ll create a *Blog post* content type and add some standard fields, such as a text field for a page title, an image field for a header image, and a component with fields for metadata. Then we’ll add a composer to the content type for authors to create the body of the blog posts. Inside this composer we’ll allow text, image, and quote fields along with an entry field so authors can tag related products from our *Plants* and *Pots* content types. When authors create an entry from this new content type, they’ll be able to create a blog post using any combination of the fields in our new composer.

If you are creating content to be used on a website, [Site View](/help-and-docs/user-guides/content-modelling/site-view/site-view-overview) provides a straightforward way to create and manage your content in a hierarchical structure. You can use the Site View screen to build your information architecture before creating your content, or create and structure the content as you go along. Developers can then access Site View using the Contensis Delivery API and use your site structure to build menus and other navigation.

In Site View you structure your site by creating a tree made up of what we call nodes. Each node represents a location in your website to which you can attach content. Creating a node generates a new URL relative to its place in your site structure. You can then attach entries to these nodes and developers can render them as web pages at the URL.

The entry you assign to a location exists independently of the node, and vice versa. If you simply detach an entry from a node, both will continue to exist. This also makes it possible to attach an entry to more than one node.

You can also set a default location for entries created using the same content type. When authors publish a new entry, the node will be created dynamically with the entry assigned to that new location in your site structure. This is great for managing collections of similar content like products, events, or blogs.

We can use the default location feature to make sure any new entries we create are attached to the correct nodes in Site View. First we'll create a parent node called *Products*. Inside this node we'll create two more parent nodes – *Plants* and *Pots*. We can then set the default location in the *Plants* and *Pots* content types to their respective parent nodes. Now whenever somebody creates a new entry, it will automatically be attached to a new node in the correct place in our site structure.  

## Authoring content

Each item of content created from a content type is referred to as an entry. An entry contains the structured chunks of content defined by the content type. You can create an unlimited number of entries from a single content type.

The lifecycle of every entry in Contensis is controlled by a publishing

## Content governance

Contensis uses a system of [roles and permissions](/help-and-docs/user-guides/governance/roles-and-permissions/roles-and-permissions-overview) to give you control over who can make changes to content. All users and **API keys** in Contensis are assigned to a *Role*. Roles are assigned *Permissions* which grant the users with the role the ability to perform certain tasks within a project.

Users in the *Roles administrators* group can create a new role from the *Roles* listing screen in the Contensis sidebar. From there you can give a role permissions to access and perform actions on:

-   Entries
-   Assets
-   Entry language variations

Permissions are closely tied to workflow events and include:

-   **View** — the user can view content. The view permission is inherently set when any other permission is granted.
-   **Create / save** — the user can create new content, and save changes to existing content.
-   **Submit / revoke** — the user can submit and revoke content from review.
-   **Approve / decline** — the user can approve or decline content for publication.
-   **Publish** – the user can publish the content for immediate publication.
-   **Unpublish** – the user can unpublish the content.
-   **Delete** — the user can delete content permanently.

Roles do not provide granular access to individual files, assets, or entries. If a user is a member of a role with access to a particular content type, they will be able to access all entries created using that content type. This is intentional. Granular permissions quickly become difficult to manage, especially in large organisations.

For example, we might have a *Blog author* role, which enables those users to create, update, and submit for approval any entries using the *Blog post* content type. But users with the *Blog post* approver role may only be able to approve and decline entries for the *Blog post* content type without being allowed to update them.