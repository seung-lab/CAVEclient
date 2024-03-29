---
title: Changelog
---

## 5.1.0

- Added get_oldest_timestamp call to chunkedgraph

## 5.0.1

- Fixed bug with desired_resolution being set at the client level
  was being ignored in >5.0.0

## 5.0.0

- Added support for the new CAVE Materialization 3.0 API
  Includes support for the new materialization API, which allows for
  server side conversion of the units of position, and ensures that
  all positions are returned with the same units, even after joins.
- Added support for querying databases that were materialized without merging
  tables together. This will allow for faster materializations.
- Removed support for LiveLive query from the Materialization 2.0 API client.
  Note.. <5.0.0 clients interacting with MaterializationEngine >4.7.0 servers will
  use live live query but will doubly convert the units of position if you ask
  for a desired resolution, as the old client will also do a conversion server side.
- Fixed interaction with api version querying of servers from individual
  clients to work with verify=False. (useful for testing)
- Stored infromation from client about mapping between dataframe and table names
  and original column names.
- Added support for suffixes and select columns to be passed by dictionary rather than list
  making the selection an application of suffixes more explicit when there are collisions
  between column names in joined tables.

---

## Older Upgrade Notes

Change all select_column calls to pass dictionaries rather than lists.
Change all suffix calls to pass dictionaries rather than lists.
Advocate for your server administrator to upgrade to MaterializationEngine 4.7.0 or later,
so you can use the new MaterializationEngine 3.0 API and client.
