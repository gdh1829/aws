---
Title: Elastic Cache
---

## Differences between Memcahced and Redis

| features                                         | Memcached | Reids  |
| ------------------------------------------------ | --------- | ------ |
| Sub-millisecond latency                          | O         | O      |
| Developer ease of use                            | O         | O      |
| *Data partitioning                               | O         | O      |
| Support for a broad set of programming languages | O         | O      |
| *Advanced data structures                        | -         | O      |
| *Multithreaded architecture                      | O         | -      |
| Snapshots                                        | -         | O      |
| Replication                                      | -         | O      |
| *Transactions                                    | -         | O      |
| *Pub/Sub                                         | -         | O      |
| *Lua scripting                                   | -         | O      |
| *Geospatial support                              | -         | O      |
| relative avaiability between those two           | lower     | higher |

- Data partitiooning
  - Both Reids and Memcached allow you to distribute your data among multiple nodes. This allows you to scale out to better handle more data when demand grows.

- Advanced data structures
  - In addition to strings, Redis supports lists, sets, sorted sets, hashes, bit arrays, and hyperloglogs.
  - Applications can use these more advanced data structures to support a variety of use cases.
  - For example, you can use Reids Sorted Sets to easily implement a leaderboard that keeps a list of players sorted by their rank.

- Multithreaded architecture
  - Since Memcached is multithreaded, it can make use of multiple processing cores. This means that you can handle more operations by scaling up compute capacity.

- Transactions
  - Redis supports transactions which let you execute a group of commands as an isolated and atomic operation

- Pub/Sub
  - Redis supports Pub/Sub messaging with pattern matching which you can use for high performance chat rooms, real-time comment streams, social media feeds, and server intercommunication.

- Lua scripting
  - Redis allows you to execute transactional Lua scripts. Scripts can help you boost performance and simplify your application.

- Geospatial support
  - Redis has purpose-built commands for working with real-time geospatial data at scale.
  - You can perform operations like finding the distance between two elements (for example people ro places) and finding all elements within a given distance of a point.


## Redis

- Both Reids and Memcached have sub-millisecond latency but for Redis with support of replication, snapshots, etc, it has higher availability than Memcachd.

## Memcached