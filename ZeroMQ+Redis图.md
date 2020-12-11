---
date: 2020-08-27T15:17
tags: [DistributedComputing]
---

# ZeroMQ+Redis图

-------Application-------      ------------
|                       |      | External |
|           ZMQ socket-(|<----(|  Source  |
|            v          |      ------------
|            V          |
|     (Process Data)    |      ----------
|            V          |      |  Redis |
|      Redis connector--|)---->| Server |
|                       |      ----------
-------------------------

