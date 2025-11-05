# Search
## How to query, filter, and explore Anthera

The search bar has many features and filters you can use to find exactly what you're looking for. This document covers the main ones.

- Filters start with "@", e.g. `@creator=tanza3d` to search for a post by the user tanza3d, or `@type=text` to search only for text posts.

  You can also use operators: `=, !=, <, >, <=, >=, !<, !>, !<=, !>=`. Not all filters support every operator yet.
- Tags start with "#", e.g. `#dragon` to see every post with the tag "dragon". Start the tag with `!` to exclude, e.g. `!#dragon`.
- You can also search by just typing into the field (e.g. just searching "protogen" would find all posts with Protogen mentioned in the title, or character names, or species, or various other fields)

---

# Filters

## @creator
Search by user handle (case-insensitive):
`@creator=tanza3d`, `@creator=1`

## @author / @artist
Filter by authors in a post (not the creator). E.g.
`@author=@tanza3d`, `@author=`

## @status
Filter posts by status:

- `0` = unpublished
- `1` = unlisted
- `2` = published
- `3` = blocked

Example: `@status=2`

## @rating
Filter posts by rating:

| Rating     | Valid types       |
|------------|-------------------|
| Safe       | safe, s, 0        |
| Suggestive | suggestive, su, 1 |
| Mature     | mature, m, 2      |
| Explicit   | explicit, e, 3    |

Example: `@rating!=e` (queries rating is not explicit)

## @library / @folder
Filter by folder ID.

## @likedby / @favouritedby
Filter items liked or favorited by a specific user ID.

## @character
Search for posts with specific characters. Supports:

- `@character=charname` to find any character with specific name
- `@character=@owner/charname` for specific owner
- `@character=384` to find specific ID

## @orderby
Order posts by specific values:

- `date-published`, `date_published` → Items.PublishDate
- `date-posted`, `date_posted` → Items.PostDate
- `date-created`, `date_created` → Items.Date
- `views` → Items.Views
- `name` → Items.Name
- `creator` → Items.Creator
- `stars`, `likes`, `favcount` → VoteCount
- `random` → RAND()

## @orderdir
Sort direction: `ascending` or `descending`  
Aliases: `orderdir`, `sortdir`

## @category
Filter by numeric art category ID (use dropdown on explore page for reference)

## @stars
Filter by star count, e.g. `@stars>4`

## @views
Filter by view count, e.g. `@views>200`

## @species
Find posts with characters based on species, e.g. `@species=dragon`

## @date/creationdate
Filter posts based on their post date.
- @date = The date the post was published
- @creationdate = The Date that the user specified the piece was "created"

Usage examples:
- Find uploads in the past 5 days: <br>`@date=5d`
- Find uploads from more than 2 weeks ago: <br>`@date<2w`
- Find uploads between two specific dates: <br>`@date>2025-04-02 @date<2025-05-06`
- Find art "created" in 2020: <br>`@datecreated=2020` <span class="icon-info" tooltip="Creation date is provided by the uploader of the post and is intended to be the date the piece of art is created. We do not verify or confirm this data and it may be incorrect."></span>


<br>

---
# WIP/Unused
Queries in this section are not properly supported, and may not always work correctly or at all.

## @followingauthor
Filter for items where any author of a post is followed by you (logged in)

## @followingowner
Filter for items where the creator/owner is followed by you (logged in)