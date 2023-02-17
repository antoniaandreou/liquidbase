## How Liquidbase Works
----------
#### Changelogs
- Source of all change in liquidbase
- A text file containing all the schema changes
- Can be written in
    - SQL
    - XML
    - YAML
    - JSON
- Can be versioned control by any tool

Two most common ways lqbase used:
- SQL Model written in SQL
- Platform-agnostic model written in eith XML, JSON or YAML

##### SQL Model
- Uses SQL statements in changesets to make changes
- Lqbase then sues these SQL changesets to create the *change types*
- Formatted SQL changelog use comments to provide lqbase metadata. Needs to begin with the following comment 
    - -- liquidbase formatted sql
- Changesets need to begin with the following comment
    - -- changeset author:id
    Could add multiple changesets in a changelog but each need to begin with a new line as dictated above
- These are then followed by SQL statements separated by semi-colons

##### Platform-Agnostic Model
- Each changeset contains 1 or more lqbase changeset objects to create custom *change types*
- Changelogs contain information for the XML parser at the top & a list of changesets underneath
- XML changelogs can be more useful than SQL ones when you have to make db schema changes, especially when changes are between different types of dbs 
- each change need to be separate with a new change tag

##### Best Practice
Can write multiple changesets in changelog
However best practise is to:
- have only 1 change types in a changeset
- not overload changelog with a bunch of changesets
- best to create multiple changelogs that are nested under a **master changelog** written in XML

