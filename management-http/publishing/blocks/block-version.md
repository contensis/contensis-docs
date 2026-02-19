JSON

```
{
    "id": "movie-listing",
    "projectId": "movieDb",
    "image": {
        "uri": "moviedb/movie-listing",
        "tag": "81e13d08"
    },
    "source": {
        "branch": "main",
        "provider": "github",
        "repositoryUrl": "https://github.com/moviedb/movie-listing.git",
        "commit": {
            "id": "81e13d08",
            "message": "Displays the main listing for movies on the movie example site",
            "datetime": "2021-03-09T18:05:10Z",
            "authorEmail": "m.scorsese@film.com",
            "committerEmail": "m.scorsese@film.com",
            "commitUrl": "https://github.com/moviedb/movie-listing/-/commit/81e13d08",
            "comparisonUrl": "https://github.com/moviedb/movie-listing/-/commit/cc6b2a33...81e13d08"
        }
    },
    "staticPaths": [
        "static",
        "image-gallery"
    ],
    "endpoints": [
        {
            "id": "movieListing",
            "path": "/movieListing",
            "type": "pagelet"
        },
        {
            "id": "movieRecord",
            "path": "/movieRecord",
            "type": "pagelet"
        },
        {
            "id": "ratingTemplate",
            "path": "/ratingtemplate",
            "type": "layout"
        }
    ],
    "version": {
        "pushedBy": "m.scorsese@film.com",
        "pushed": "2021-03-09T18:05:10Z",
        "releasedBy": "sikeliaProductions",
        "released": "2021-03-10T10:15:12.19Z",
        "markedBrokenBy": null,
        "markedBroken": null,
        "versionNo": "6.0",
        "madeLiveBy": null,
        "madeLive": null
    },
    "status": {
        "broken": false,
        "deployment": "Deployed",
        "running": "Available",
        "workflow": "Draft"
    }
}
```