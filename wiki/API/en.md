# Anthera's API
Currently we do not have a public api, but you can make use of our Gallery endpoint to query for posts.

Our eventual goal is to support full third-party apps and frontends for Anthera entirely through an official and free API, but we're first working towards getting all features implemented on-site first.


## Get Gallery `/api/gallery/v2`

POST (preferably)
Data:
- Query
  - Required.
  - Uses same syntax as the search bar. [Learn about Search Queries here](Miscellaneous/Search)
- Offset
  - Amount of items (__not pages!__) to offset the result by.
  - e.g. If your pages show 30 items per page, for page 2 you would want offset 30
- Limit
  - How many items show per page/result. Following the example above, where you want to show 30 items per page, you would set this to 30.

Example request:
```js
(await fetch("https://anthera.art/api/gallery/v2", {
    method: "POST",
    headers: {
        "Content-Type": "application/json",
    },
    body: JSON.stringify({
        query: "@type=art|photo|text @orderby=date-published",
        offset: 0,
        limit: 1 // just for example, you would want to up this!
    }),
})).json() 
```
Example response:
```js
{
  "items": [
    {
      "ID": 97,
      "Creator": 1, // The owner/creator of the post
      "Type": "art",
      "Name": "cute ram",
      "Rating": 0,
      "Description": "two *very* cute protos! :3", // can be markdown
      "AltText": "",
      "ArtCategory": 0,
      "Date": "2024-03-22 19:05:32", // date the item was created
      "PostDate": "2024-03-22 19:05:38", // date the user provided for "art creation"
      "PublishDate": "2024-03-22 19:06:05", // date the user published the post
      "Status": 2, // 0 = draft, 2 = publised.
      "HomepageFeature": 0, // featured on homepage
      "Deleted": 0,
      "Views": 16,
      "PixelArt": 0, // nearest neighbour upscaling when set to 1
      "CreatorTag": "tanza",
      "CreatorName": "Tanza",
      "Width": 1920,
      "Height": 1080,
      "Colours": "[\"d2d2b4\",\"f0f0f0\",\"96785a\",\"b49678\",\"1e1e1e\",\"5a3c3c\",\"3c3c1e\",\"5a0096\",\"785a3c\",960078]", // most common colours in the image. this is a json array as a string but will likely be updated to just be an array in the future. add handling for both
      "AspectRatio": "16:9",
      "Bucket": "storage/anthera", // not important for you :)
      "HasSmall": 1,
      "Extension": "png",
      "ImageBlur": "/9j/4AAQSkZJRgABAQEAYABgAAD/2wBDAAgGBgcGBQgHBwcJCQgKDBQNDAsLDBkSEw8UHRofHh0aHBwgJC4nICIsIxwcKDcpLDAxNDQ0Hyc5PTgyPC4zNDL/2wBDAQkJCQwLDBgNDRgyIRwhMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjL/wAARCAAEAAcDAREAAhEBAxEB/8QAFAABAAAAAAAAAAAAAAAAAAAAA//EAB8QAAIBAgcAAAAAAAAAAAAAAAEDAgAGBRETIlFxgf/EABUBAQEAAAAAAAAAAAAAAAAAAAIF/8QAGhEBAAEFAAAAAAAAAAAAAAAAAQIAAwQRUf/aAAwDAQACEQMRAD8AW3rixFY1JMi0tm1kgwEjPaOez7U3Imxd8CnmX5WwTuq//9k=", // low resolution (4px tall) version of the image. can be used to show a blurred version while it loads
      "HasVotedLoggedIn": 1, // only shows when logged in
      "HasVoted": true, // only shows when logged in
      "VoteCount": 6,
      "Authors": [
        {
          "ID": 1,
          "Type": "0",
          "Name": "Tanza",
          "Tag": "tanza",
          "HumanTag": "tANZA",
          "AuthorName": null, // for "custom authors"
          "AuthorLink": null, // for "custom authors"
          "IsFollowing": 1 // only shows when logged in
        },
        {
          "ID": 3,
          "Type": "Character Owner",
          "Name": "Retiu",
          "Tag": "retiu",
          "HumanTag": "Retiu",
          "AuthorName": null, // for "custom authors"
          "AuthorLink": null, // for "custom authors"
          "IsFollowing": 1 // only shows when logged in
        }
      ],
      "Tags": [
        {
          "ID": 1,
          "Name": "protogen"
        },
        {
          "ID": 12,
          "Name": "cute"
        },
        {
          "ID": 140,
          "Name": "retiu"
        },
        {
          "ID": 145,
          "Name": "tanza"
        }
      ],
      "Characters": [
        {
          "ID": 1,
          "Name": "Tanza",
          "Tag": "Tanza",
          "OwnerTag": "tANZA",
          "OwnerID": 1,
          "PfpTime": 1711905470
        },
        {
          "ID": 34,
          "Name": "Retiu",
          "Tag": "Retiu",
          "OwnerTag": "Retiu",
          "OwnerID": 3,
          "PfpTime": 1740711073
        }
      ],
      "CommentCount": 96, // currently incorrect? don't rely on it lol
      "UIWidth": 1920,
      "UIHeight": 1080
    }
  ],
  "maxCount": 200, // how many items could possibly be returned from this query (in the case that there was no limit) - can be used divided by your limit to get how many pages there are (when ceil)
  "debug": "Debugging gallery query not available on anthera-prod-instance.", // when running on a development instance, this would show the full query ran to get this response. might sometimes be enabled on prod but don't expect it
  "cachingTime": 0,
  "fromCache": false
}
```



.. If you need any more APIs, feel free to dig around in the responses tab, but keep in mind I plan to add an oauth application system in the future, so don't be surprised if your client gets locked out of those. If I know you or have heard of your usage of the API, I'll try reach out prior to making any breaking changes like that.

Keep in mind Anthera is still in heavy development, so expect things to come and disappear over time.