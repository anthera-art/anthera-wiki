# Search
## How to query, filter, and explore Anthera

The search bar has many various features and filters you can use to find exactly what you're looking for. This document will cover the important ones.

Filters start with "@", e.g. if you wanted to search for a post by the user tanza3d, you would do `@creator=tanza3d`, or if you only wanted to search for text posts, you can do `@type=text`

Tags start with #, e.g. if you want to see every post with the tag "dragon", you search `#dragon`. Start the tag with a ! to exclude, e.g. `!#dragon`

On occasion, you can also specify other operators, any from the following list:
`=, !=, <, >, >=, !<=, !<, !>, !>=, !<=`, though this is not supported by every query just yet.




## @creator
@creator searches by user handle (case insensitive)

## @creatorid
@creatorid searches by 

## @status
Filters posts by current status.

0 = unpublished<br>
1 = unlisted<br>
2 = published<br>
3 = blocked

## @rating
Filters posts by rating.

| Rating     | Valid Types       |
|------------|-------------------|
| Safe       | safe, s, 0        |
| Suggestive | suggestive, su, 1 |
| Mature     | mature, m, 2      |
| Explicit   | explicit, e, 3    |


## @author / @artist
Filters by authors in post (not creator!)

## @library / @folder
Filters by what folder the items are in, use folder ID.

## @likedby / @favouritedby
Search users' liked posts. Use user ID

## @character
Search for posts with specific characters. e.g. `@character=@cyon/cyonsergal`

You can also search just by character name (e.g. `@character=tanza3d`), but if multiple characters have the same handle, this will return all results.

## @orderby
Order posts by specific values, valid orderings are:
`date-published`, `date-posted`, `views`, `name`, `creator`, `stars`


## @orderdir
Direction of ordering, use 'descending' or 'ascending'. Defaults to 'descending'.

## @type
Search posts by type. Search for multiple by using `|` (e.g. `@type=text|art`) - the UI has options for this 