## We value your privacy

We use cookies to improve your experience. [Privacy policy](https://www.contensis.com/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [User guides](https://www.contensis.com/help-and-docs/guides)
3.  [Personalisation](https://www.contensis.com/help-and-docs/guides/personalisation)
4.  [Signals](https://www.contensis.com/help-and-docs/guides/personalisation/signals)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 07 October 2025

Contensis supports a wide range of built-in signal attributes. These attributes can be used individually or in combination to define sophisticated signal conditions, which drive audience targeting in personalisation.

## 🔍 Browser

Browser attributes

Name

Attribute name

Description

Example

User agent

`browser.userAgent`

The User-Agent string from the user's browser.

`"Mozilla/5.0 (Windows NT 10.0; Win64; x64)"`

Language

`browser.language`

The primary language setting of the user's browser.

`"en-GB"`

Platform

`browser.platform`

The platform the browser is running on (e.g., OS or device type).

`"Win32"`

Vendor

`browser.vendor`

The vendor of the browser (e.g., Chrome, Firefox, Safari).

`"Google Inc."`

Screen width

`browser.screenWidth`

The width of the user's screen in pixels.

`1920`

Screen height

`browser.screenHeight`

The width of the user's screen in pixels.

`1080`

Color Depth

`browser.colorDepth`

The color depth of the user's display (in bits).

`24`

Touch support

`browser.touchSupport`

Indicates if the user's browser supports touch input.

`true`

Timezone

`browser.timezone`

The timezone configured in the user's browser or device.

`"Europe/London"`

Cookies enabled

`browser.cookiesEnabled`

Indicates if cookies are enabled in the user's browser.

`true`

## 🍪 Cookie

Cookie attributes

Name

Attribute name

Description

Example

Value

`cookie.value`

The value of a cookie by its name.

`"darkMode=true"`

String

`cookie.string`

The raw cookie string.

`"__Secure-3PAPISID=uI1pBPWTQ6zjVFv7; _pk_id.84.29a1=4be9ecd6020e3b7c.1733324457.1.1733324457.3324457."`

## 🌍 Location

Location attributes

Name

Attribute name

Description

Example

IP

`location.ip`

The IP address of the user.

`"185.18.138.30" "185.18.138.0\24"`

Country

`location.country`

The country derived from the user's IP address.

`"GB"`

## 📄 Page

Page attributes

Name

Attribute name

Description

Example

URL

`page.url`

The full URL including protocol, domain, path, query string, and fragment.

`"https://www.mysite.com/products/televisions?type=oled"`

Path

`page.path`

The path portion of the URL (after the domain, before the query string).

`"/products/televisions"`

Query string

`page.querystring`

The raw query string (everything after `?`).

`"type=oled&size=55"`

Query string parameter

`page.queryParams.type`

Specific query parameter from the page

`"oled"`

Subdomain

`page.subdomain`

The subdomain portion of the domain name.

`"www"`

Base URL

`page.baseUrl`

The URL without the query string or fragment (protocol + domain + path).

`"https://www.mysite.com/products/televisions"`

## ↪️ Referrer

Referrer attributes

Name

Attribute name

Description

Example

URL

`referrer.url`

The full URL of the referring page.

`"https://www.mysite.com/products/televisions?type=oled"`

Path

`referrer.path`

The path portion of the referring page URL.

`"/products/televisions"`

Query string

`referrer.querystring`

The raw query string of the referring page.

`"type=oled&size=55"`

Query string parameter

`referrer.queryParams.type`

Specific query parameter from the referring page.

`"oled"`

Domain

`referrer.domain`

The domain name of the referring page, including subdomains.

`"www.mysite.com"`

Subdomain

`referrer.subdomain`

The subdomain portion of the referring page’s domain name.

`"www"`

Base URL

`referrer.baseUrl`

The referring page’s URL without the query string or fragment.

`"https://www.mysite.com/products"`

## ⏱️ Session

Session attributes

Name

Attribute name

Description

Example

First visit

`session.isFirstVisit`

Indicates if it’s a new user session.

`true`

Start time

`session.startTime`

The timestamp when the session started.

`"2025-01-21T10:00:00Z"`

Duration

`session.duration`

The length of the session in seconds.

`1200` (20 minutes)

Page views

`session.pageViews`

The number of pages viewed during the session.

`5`

Last activity

`session.lastActivity`

The timestamp of the user’s last interaction.

`"2025-01-21T10:05:00Z"`

Entry page

`session.entryPage`

The first page the user visited in the session.

`"/home"`

Referrer URL

`session.referrer.url`

The full URL of the referring page.

`"https://www.mysite.com/products?category=electronics"`

Referrer path

`session.referrer.path`

The path portion of the referring page URL.

`"/products"`

Referrer query string

`session.referrer.querystring`

The raw query string of the referring page.

`"category=electronics"`

Referrer query parameter

`session.referrer.queryParams.category`

Specific query parameter from the referring page.

`"electronics"`

Referrer domain

`session.referrer.domain`

The domain name of the referring page, including subdomains.

`"www.mysite.com"`

Referrer subdomain

`session.referrer.subdomain`

The subdomain portion of the referring page’s domain name.

`"www"`

Referrer base URL

`session.referrer.baseUrl`

The referring page’s URL without the query string or fragment.

`"https://www.mysite.com/products"`