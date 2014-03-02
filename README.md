cloud-manager
=============

Manages a pool of files uploaded to "the cloud"


    import cloudmanager

    cm = cloudmanager.CloudManager(
      "/path/to/database.sqlite3",   # Database of the stored files' information
      "/path/to/storage/",           # Cached files will be stored here
      20 * (2**30))                  # 20 GiB capacity

    cm.upload("/path/to/file")       # returns hash of the uploaded file, or error

    cm.warm_up("6f7bed7...121b2")    # Puts the corresponding file in cache
    cm.download("6f7bed7...121b2")   # Same as warm_up

    cm.exists("6f7bed7...121b2")     # returns true if the file exists on the database
    cm.on_cache("6f7bed7...121b2")   # returns true if the file is on cache

    cm.usage_ratio()                 # Returns the storage usage percentage

    cm.close()                       # cleans up everything.

