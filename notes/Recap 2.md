Batch 
    Load and process, output process at one time
Stream
    immediate
    incremental processing
    data keep adding, updating..

repartition
    to increase partition
    shuffle
coalsece
    to reduce
    shuffle may happen, try to reduce shuffle

cache
    why to cache?
    reuse rdd/dataframe
           loading time/cost/save cost of processing

    df.cache() - MEMORY AND DISK, shall call df.persist internally with
            df.persist(StorageLEvel.MEMORY_AND_DISK)

    StorageLevel.XYZZZ_2, where _2 represent replication.

    In general, no replication for cached data. _2 means, the copy of the cache is kept in one another executor as backup.


    df.persist(StorageLevel.DISK_ONLY) - Cache, persist accept a parameter, to define storage level
    df.persist(StorageLevel.MEMORY_ONLY)

---


