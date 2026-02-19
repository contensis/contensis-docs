1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  [Security](/help-and-docs/apis/management-http/security)

[Log in to add to favourites](/account/login)

Page last updated 26 September 2023

## Properties

Name

Type

Format

Description

**id**

string

GUID

The user identifier as a 128 bit GUID

**username**

string

\-

The user's username

**email**

string

\-

The user's email

**firstName**

string

\-

The user's first name

**lastName**

string

\-

The user's last name

**timezone**

string

timezone offset name

The user's timezone preference

**language**

string

[language code](/help-and-docs/apis/management-http/key-concepts/localization)

The user's language preference

**custom.\***

object

\-

Additional custom data stored against the user

**credentials**

object

\-

Container for authentication details

**credentials.password**

string

\-

The password value when creating a user. The value is never returned in a response

**credentials.passwordChangeFrequency**

integer

\-

Sets the number of days before a password expires and has to be changed, unless set to 0, in which case the password never expires. This property can only be set by System Administrators. For Active Directory integrated users, the value is always null and cannot be changed.

**status**

object

\-

Container for status information

**status.active**

boolean

\-

A flag to indicate whether the user is active

**status.locked**

boolean

\-

A flag to indicate whether the user's access has been locked

**status.passwordResetRequired**

boolean

\-

A flag to indicate whether the user's password requires resetting

**created**

datetime

\-

The date and time the user was first created

**modified**

datetime

\-

The date and time the user was modified

**lastLogin**

datetime

\-

The date and time the user last logged-in

**lastFailedLogin**

datetime

\-

The date and time of the last unsuccessful login attempt for the user

**expiry**

datetime

datetime

The expiry date for the user

**passwordChanged**

datetime

\-

The date and time the user's password was last changed

**optOutOfNotifications**

boolean

\-

Shows if the user has chosen to opt out of all notifications

**failedLoginAttempts**

integer

integer

The total number of times this user has failed to log in. This includes entering a correct username and password on a locked account.

**failedLoginAttemptsSinceLastSuccess**

integer

integer

The total number of failed login attempts since the user's last successful login. This will be reset to 0 upon successful login.

**successfulLoginAttempts**

integer

integer

The total number of successful login attempts by this user.

## Example

An example user resource

JSON

```
{
    "id": "e09e77b9-9dd9-4d46-b7dd-deb9702a5835",
    "username": "s.yearsley",
    "email": "s.yearsley@zengenti.com",
    "firstName": "Tyler",
    "lastName": "Durden",
    "timezone": "America/New_York",
    "language": "en-GB",
    "custom": {
        "title": "Mr",
        "department": "finance"
    },
    "credentials": {
        "provider": {
            "type": "contensis",
            "name": "contensis"
        }
    },
    "status": {
        "suspended": true,
        "locked": false,
        "passwordResetRequired": false
    },
    "created": "2020-06-24T16:39:18.000Z",
    "modified": "2020-06-24T16:39:18.000Z",
    "lastLogin": "2020-06-24T16:39:18.000Z",
    "lastFailedLogin": "2019-06-24T16:39:18.000Z",
    "expiry": "2050-12-31T23:59:59.999Z",
    "passwordChanged": "2020-06-24T16:39:18.000Z",
    "optOutOfNotifications": true,
    "failedLoginAttempts": 4,
    "failedLoginAttemptsSinceLastSuccess": 0,
    "successfulLoginAttempts": 3
}
```