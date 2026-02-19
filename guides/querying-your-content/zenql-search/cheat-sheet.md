1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [User guides](https://www.contensis.com/help-and-docs/guides)
3.  [Querying your content](https://www.contensis.com/help-and-docs/guides/querying-your-content)
4.  ZENQL search

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 29 April 2025

## Entries

### Edited by me today

JavaScript

```
sys.version.modified between(startOfDay(), endOfDay()) and sys.version.modifiedBy = currentUser()
```

### Edited by me this week

JavaScript

```
sys.version.modified between(startOfWeek(), endOfWeek()) and sys.version.modifiedBy = currentUser()
```

### Edited by me this month

JavaScript

```
sys.version.modified between(startOfMonth(), endOfMonth()) and sys.version.modifiedBy = currentUser()
```

### Edited by me this year

json

```
sys.version.modified between(startOfYear(),endOfYear()) and sys.version.modifiedBy = currentUser()
```

### Awaiting approval

JavaScript

```
sys.workflow.state = awaitingApproval
```

### Created this month

json

```
sys.version.created between(startOfMonth(), endOfMonth())
```

### Published this month

JavaScript

```
sys.version.published between(startOfMonth(), endOfMonth())
```

### Archived this month

The *Include archive* checkbox must be checked to use this query.

JavaScript

```
sys.version.archived between(startOfMonth(), endOfMonth())
```

### In draft

JavaScript

```
sys.workflow.state = draft
```

### Entries not published

JavaScript

```
sys.isPublished = false
```

### Published entries

JavaScript

```
sys.isPublished = true
```

### Published this week

json

```
sys.version.published between(startOfWeek(), endOfWeek())
```

### Published last week

json

```
sys.version.published between(startOfWeek(-1), endOfWeek(-1))
```

### Due to be unpublished

*This search is only avaliable in the Management API and UI.*

JavaScript

```
sys.schedules.unpublish exists and sys.schedules.publish.dateTime > now() 
```

### Due to be unpublished in the next month

*This search is only available in the Management API and UI.*

json

```
sys.schedules.unpublish exists and sys.schedules.publish.dateTime between( startOfMonth(1), endOfMonth(1))
```

### Entries due to be published

*This search is only available in the Management API and UI.*

json

```
sys.schedules.publish exists and sys.schedules.publish.dateTime > now()
```

### Translations out of date

*This search is only available in the Management API.*

json

```
sys.translationState = translationOutOfDate and  sys.versionStatus = latest
```

### Translations out of date for specific language e.g. Welsh

*This search is only avaliable in the Management API.*

json

```
sys.translationState = translationOutOfDate and  sys.versionStatus = latest and sys.language = cy
```