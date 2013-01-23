CandyBox
=====

My lovely scriptlets (in case I need one of them some day).

HBase Export/Import
-------------------

### exp_schema.sh
Export HBase table schemas (dump to stdout).
```bash
$ ./exp_schema.sh [tablelist]
```
The optional argument `tablelist` should be a file containing a list of table name to be exported. If `tablelist` is absent, then schema of all tables are dumped to stdout.
The dumped schema can be later executed in `hbase shell` to create tables.

### exp_data.sh
Export HBase table data to specified directory. (via [org.apache.hadoop.hbase.mapreduce.Export](http://hbase.apache.org/book/ops_mgt.html#export))
```bash
$ ./exp_data.sh <outputdir> [tablelist]
```
If `tablelist` is absent, all tables are exported. The exported data can be imported to current/another cluster later with `imp_data.sh`.

### imp_data.sh
Import HBase table data from specified directory to tables. (via [org.apache.hadoop.hbase.mapreduce.Import](http://hbase.apache.org/book/ops_mgt.html#import) )
```bash
$ ./imp_data.sh <inputdir> [tablelist]
```
if `tablelist` is abset, all sub-directory names in `inputdir` is used as tables.
