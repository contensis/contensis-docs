1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [User guides](https://www.contensis.com/help-and-docs/guides)
3.  [Personalisation](https://www.contensis.com/help-and-docs/guides/personalisation)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 06 October 2025

Signals are the foundation of personalisation in Contensis. A signal defines the criteria Contensis uses to decide whether a visitor belongs to a particular audience.

Each signal helps you evaluate visitor characteristics, such as their device type, location, or how they found your site. This lets you build audience definitions that are as simple or as detailed as you need.

For example, you might create a signal that identifies visitors who are in the United Kingdom and viewing a page in the /courses section of your site.

## How signals are structured

A signal is made up of rules, and each rule contains one or more conditions. This layered structure gives you the flexibility to define simple or complex criteria.

### Conditions

A condition is the smallest part of a signal. It checks for something specific about the visitor’s browser, behaviour, or session. Each condition has three parts:

-   **Signal attribute:** What you are evaluating, such as:
    
    -   browser.language (for example, en-GB)
    -   page.path (for example, /courses)
    -   referrer.domain (for example, google.com)
    
-   **Operator:** How to compare the attribute to a value, such as:
    
    -   equals
    -   contains
    -   greater than
    
-   **Value:** What the attribute is compared against, such as:
    
    -   GB for location.country
    -   courses in a URL path
    -   true for flags like session.isFirstVisit
    

Together, these define the specific condition that must be met for the rule to match.

### Rules: grouping conditions

Rules group conditions together to define more complex scenarios. You can choose how the conditions in a rule should be evaluated:

-   **All conditions must be met:** Every condition in the rule must be true for the rule to match.
-   **Any condition may be met:** The rule matches if any one of the conditions is true.

#### Grouping examples

-   **All conditions must be met**:  
    Show content to users who are in the UK **and** are viewing the /courses page. **→ Both** conditions must be true.
-   **Any condition may be met:**  
    Show content to users who are from a specific campaign **or** using a mobile device. **→ Only one** condition needs to be true.

## Example signals

Here are some signals you might define for your sector:

### Local government

-   Visitors located in a specific council area and accessing waste collection pages.
-   Visitors referred from a government portal, such as GOV.UK.
-   Mobile users browsing service directories.

### Higher education

-   Prospective students outside the UK viewing undergraduate course pages.
-   Current students accessing from campus IP ranges.
-   Visitors who have previously viewed accommodation, open day, or scholarship information.

## Summary

Signals give you the building blocks for defining audiences. By combining conditions into rules, and rules into signals, you can create personalised experiences that match your visitors’ needs.