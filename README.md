# Stenoscope
A golang scanner & parser for the SST index files generated by [stenographer](https://github.com/google/stenographer) to JSON

### Command Line
Compile the command line version using go 1.10+
```
go build
```

#### Usage
##### JSON
```
./SSTableKeys /data/stenographer/1/thread0/index $(date -d '1 minute ago' +%s) $(date +%s)
```

### NodeJS Module
Compile the native binding for nodejs (or download a prebuilt version)
```
make
```

#### Usage
```
const sstable = require('./index.js');

var fromtime = parseInt(new Date().getTime()/1000) - 60;
var totime = parseInt(new Date().getTime()/1000);

console.log(
  sstable.sstj('/var/lib/stenographer/thread0/index', fromtime, totime )
);
```
