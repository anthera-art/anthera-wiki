# Search
## How to query, filter, and explore Anthera

The search bar has many various features and filters you can use to find exactly what you're looking for. This document will cover the important ones.

Filters start with "@", e.g. if you wanted to search for a post by the user tanza3d, you would do `@creator=tanza3d`, or if you only wanted to search for text posts, you can do `@type=text`

Tags start with #, e.g. if you want to see every post with the tag "dragon", you search `#dragon`. Start the tag with a ! to exclude, e.g. `!#dragon`

On occasion, you can also specify other operators, any from the following list:
`=, !=, <, >, >=, !<=, !<, !>, !>=, !<=`, though this is not supported by every query just yet.



## @creator
@creator searches by user handle (case insensitive)

`@creator=tanza3d`

## @creatorid
@creatorid searches by numeric user ID

`@creator=1750074177708288`

## @status
Filters posts by current status.

0 = unpublished  
1 = unlisted  
2 = published  
3 = blocked

`@status=2`

## @rating
Filters posts by rating.

| Rating     | Valid Types       |
|------------|-------------------|
| Safe       | safe, s, 0        |
| Suggestive | suggestive, su, 1 |
| Mature     | mature, m, 2      |
| Explicit   | explicit, e, 3    |

`@rating!=e` (rating is not explicit)

## @author / @artist and @authorid / @artistid
Filters by authors in post (not creator!)  
Use handle (e.g. `@author=foo`) or user ID (`@authorid=123`)

## @library / @folder
Filters by what folder the items are in, use folder ID

## @likedby / @favouritedby
Filters items liked/favorited by a specific user ID

## @character
Search for posts with specific characters.  
Supports two forms:
- `@character=charname`
- `@character=@owner/charname` for specificity

## @type
Filters by content type.  
Supports `|` for multiple (e.g. `@type=text|art`)

## @orderby
Order posts by specific values. Valid values:
- `date-published`, `date_published` = Items.PublishDate
- `date-posted`, `date_posted` = Items.PostDate
- `date-created`, `date_created` = Items.Date
- `views` = Items.Views
- `name` = Items.Name
- `creator` = Items.Creator
- `stars`, `likes`, `favcount` = VoteCount
- `random` = RAND()

## @orderdir
Sort direction. Use `ascending` or `descending`  
Aliases: `orderdir`, `sortdir`

## @followingauthor
Filters for items where any author of a post is followed by you
(only available when logged in)

## @followingowner
Filters for items where the **owner/creator** is followed by you  
(only available when logged in)

## @category
Filter by numeric art category ID - best to use the dropdown on the explore page for this!