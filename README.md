# DeltaMatch Dataset
1. 'BCSD_dataset' is a dataset for binary code similarity detection. It consists of 220,000 binary functions in different versions of different software.

2. 'cve_dataset' is the vulnerability information dataset. It contains vulnerability information for six projects on NVD.

## Download

https://delta-match.s3.amazonaws.com/dataset/

Users have to pay for the download.

## Usage
1. In order to use it, you need to pre-download and install MongoDB.

2. Import data using mongoimport:
```
>> mongoimport -d [database name] -c [collection name] xxx.dat
```

## Data Format

Each function information is stored as JSON in MongoDB.

### BCSD_dataset

Field information:
funcname: software name - function name
matrix: 200x200 dimension co-occurrence matrix
node_num: number of basic blocks
edge_num: number of edge to control flow graph(CFG)
call_func_num: number of functions called
code_size: code segment size
frame_size: frame size
sub_esp_size: local variable space size
string_num: number of strings
mnem_num: number of assembly instructions

### cve_dataset
Project：curl, libtiff, openjpeg, openssl, radare2, tcpdump
Field information：
cveid: CVE ID
file: file where the vulnerability exists
funcname-list: vulnerable function name
v-affect-version: version number of vulnerable software
p-version: version number of patched software 
vul-tpye: vulnerability type
vul-level: vulnerability level
description: vulnerability description
