leveldb-py
==========

A fork of leveldb-py project which provides an interface to LevelDB's C API using python-ctypes

============
Sample Usage
============

```
import leveldb
db = leveldb.DB('/path/to/db', create_if_missing=True)
db.put('key', 'value')
print db.get('key')

for key, value in db:
  print key, value

db.delete('key')
db.close()
```

=========================================
Supported Operations and Notable Features
=========================================
- Supports get/put/delete (with standard read/write options)
- Supports bloomfilters
- Supports leveldb LRU cache
- Allows for automatic or manual database closing
- Provides write batches
- Provides support for iterators
- Provides prefix-based iteration (returns iterators that work as if all keys
  with a shared prefix had the prefix stripped and were dumped into their own
  database)
- provides scoped sub-databases (presents a new database wrapper backed by an
  existing database with all keys prefixed by some prefix)
- provides range iterators (for idioms like give me all keys between start and
  end)
- provides an in-memory db implementation (for faster unit tests)
- supports snapshots
- fits in one file
- requires no compilation
