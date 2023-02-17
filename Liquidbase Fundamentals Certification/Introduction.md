## Introduction to Liquidbase
-------
#### What is Liquidbase?
- Open source database migration tool
- Tracks, versions and deploys db schema changes
- Changes are understood based how they are specified using commands and **Change Types** 
  - These changes can be in 1 of the 4 languages below:
    - using SQL code
      - SQL 
    - using *change types*
      - XML 
      - YAML
      - JSON
- Tracks what is deployed to the db by using **changelogs** and tracking tables
- Compatible with a large range of dbs
- Full control on deployment of db changes 

##### Liquidbase Supports
- Ability to merge changes from multiple developers
- Code branches
- Multiple databases
- Cluster-safe database upgrades
- Generation of starting changelogs from existing databases
- Generation of database change documentation
- Automated updates or generation of SQL

#### How Liquidbase Works
2 main concepts:
1. Schema changes consisting of:
  - Changelogs
  - Changesets
  - Change Types
2. Tracking tables - 2 types of tables that record db changes 
  - DATABASECHANGELOG
    - tracks each changeset in changelog by **ID, AUTHOR & FILE** which combined created a primary key
  - DATABASECHANGELOGLOCK
    - ensures only a single instance of Lqbase runs at a time
    - locks others out to avoid databse conflicts
    - ensures others do not overwrite changes accidentally

#### Definitions
- Schema Changes - the fundamental unit of change in Liquidbase
- Change Types - changes to database schemas
- Changeset - 1 or more schema changes, also known as Change Types
  -   Best to limit a changeset to only 1 change type
- Changelog 
  - text file containing schema changes
  - 1 or more changesets
  - store and version in preferred source control tool
  - can include other changelogs too, allowing multiple teams to work on their own changelogs independently
  - used by liquidbase to audit the db and execute any changes not yet applied

#### Liquidbase Terminology 
- Project - a collaborative enterprise that is carefully planned and designed to achieve a particular aim
- Database - an organised collection of data
- Command Line Interface (CLI) - a text-based interface that allows you to view and modify your files
  - CLI allows for liquiqbase commands to be entered in a text-based format
- Changelog - acts as a ledger of changes and contains a list of changesets to be executed in a database
- Changeset - a unit of change that occurs to a database and indicated by 
  - *changeset tag* in XML, JSON, YAML
  - *changeset author:id* in SQL
  The changeset tag is identified by 
    - id tag
    - author tag
    - changelog file classpath name
    & it contains that unit of change

#### Liquidbase Commands
- **update** - applies to all unrun changes
- **rollback** - reverts changes you have made to your database
- **snapshot** - use to compare changes in your db or keep a record of the current db state
- **diff** - allows comparison of 2 dbs of same or different types
- **diff-changelog** - used to create a deployable changelog to synchronize multiple databases
- **history** - a helper command that lists out all deploymentIDs and their associated changesets

