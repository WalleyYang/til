Common Shell Commands
```bash
# Start
$ sudo service mongod start

# Stop
$ sudo service mongod stop

# Start MongoDB Shell
$ mongo

# List all databases
$ show dbs

# Switch to database
> use <database name>

# List collections
> show collections

# View collection contents
> db.<collection name>.find()

# Dump MongoDB
$ mongodump -d <database_name> -o <directory_backup>

# Restore MongoDB
$ mongorestore -d <database_name> <directory_backup>

# Drop database
> db.dropDatabase()
```
