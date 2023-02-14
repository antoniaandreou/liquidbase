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

#### Liquidbase Terminology 
- Project - 

