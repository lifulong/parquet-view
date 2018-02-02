Parquet View
======

Parquet-view improve from Parquet-tools(https://github.com/apache/parquet-mr)

## Build

If you want to use parquet-view in local mode, you should use the local profile so the 
hadoop client dependency is included.

```sh
cd parquet-view && mvn clean package -Plocal 
```

To use it in hadoop mode, the default profile will exclude the hadoop client dependency

```sh
cd parquet-view && mvn clean package 
```

The resulting jar is target/parquet-view-<Version>.jar, you can copy it to the place where you
want to use it

## Depends

Parquet-view depends on parquet-hadoop-1.9.1, you may need to compile it manually from [parquet-mr](https://github.com/apache/parquet-mr)

#Run from hadoop

See Commands Usage for command to use

```sh
hadoop jar ./parquet-view-<VERSION>.jar <command> my_parquet_file.lzo.parquet
```

#Run locally

See Commands Usage for command to use

```
java -jar ./parquet-view-<VERSION>.jar <command> my_parquet_file.lzo.parquet
```

## Commands Usage

To see usage instructions for all commands: 

```
java -jar ./parquet-view-<VERSION>.jar --help
```

**Note:** To run it on hadoop, you should use `hadoop jar` instead of `java -jar`

## Meta Legend

### Row Group Totals

Acronym | Definition
--------|-----------
RC | Row Count
TS | Total Byte Size

### Row Group Column Details

Acronym | Definition
--------|-----------
DO | Dictionary Page Offset
FPO | First Data Page Offset
SZ:{x}/{y}/{z} | Size in bytes. x = Compressed total, y = uncompressed total, z = y:x ratio
VC | Value Count
RLE | Run-Length Encoding
