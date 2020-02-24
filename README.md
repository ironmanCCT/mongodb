# mongodb
tips for mongodb users bson, json, mongolite, jsonlite, etc.

#steps for converting bson->mongodb
1. Put .bson file in a folder you have access to.
2. Install Mongodb with Compass Software
3. Open Mongodb Compass Software
4. Create new connection (default values)
5. Create new database and collection
6. open cmd commandline
7. Go to C:\Program Files\MongoDB\Server\4.2\bin\ 
8. It's very simple to import a .bson file:

`mongorestore -d db_name -c collection_name /path/file.bson` 

for example input/output:
```C:\Program Files\MongoDB\Server\4.2\bin>mongorestore -d bank4 -c bank4 station_1.bson
2020-02-23T15:37:09.885+0700    checking for collection data in station_1.bson
2020-02-23T15:37:09.888+0700    restoring to existing collection bank4.bank4 without dropping
2020-02-23T15:37:09.888+0700    restoring bank4.bank4 from station_1.bson
2020-02-23T15:37:12.886+0700    [#######.................]  bank4.bank4  34.2MB/108MB  (31.7%)
2020-02-23T15:37:15.887+0700    [################........]  bank4.bank4  76.4MB/108MB  (70.7%)
2020-02-23T15:37:18.197+0700    [########################]  bank4.bank4  108MB/108MB  (100.0%)
2020-02-23T15:37:18.197+0700    no indexes to restore
2020-02-23T15:37:18.198+0700    finished restoring bank4.bank4 (249908 documents, 0 failures)
2020-02-23T15:37:18.198+0700    249908 document(s) restored successfully. 0 document(s) failed to restore.
```
9. Verify that there are no errors on import and that Compass shows the correct records in the collection
10. Open collection in Compass
11. in the top bar menu, select collection>Export Collection
12. select options for export all, csv, and set a destination folder/file name.
13. csv will be exported from mongodb->csv 

#notes: I tried to convert .bson->.json with bsondump.exe (another mongodb program) but when I try to import the .json file into mongodb collection, i get an error.

