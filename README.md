# latency-dashboard

## Purpose

A simple latency monitoring dashboard for the testbed collected through  [OWL](
https://github.com/fabric-testbed/owl) running on a slice


## Usage

### First time only

```
# First time only
python3.11 -m venv .venv
source .venv/bin/activate

pip install -r requirements.txt

```

### Edit app.py

```
influxdb_ver = 'v2' (or 'v3')
conf_files = 'path/to/dir/for/required/files' # see below
``` 

### Start the Flask server

```
source .venv/bin/activate
python app.py <path/to/config/files/dir>
```

Then, connect to `http://127.0.0.1:8050/`


## Required Files

Directory name can be something other than "confs"

- `./confs/sites.csv`: FABRIC sites latitudes and longitudes
- `./confs/slice.csv`: Information on the FABRIC slice used for this data collection
- `./confs/influxdb.conf`: For accessing InfluxDB.


### influxDB config file format (`influxdb.conf`)

```
[InfluxDB]
org = <organization name>
host = <cloud or local InfluxDB URL (e.g. https://us-east-1-1.aws.cloud2.influxdata.com)>
database = <database (i.e., bucket) name>
token = <token string>
language = sql 		# v.3 (cloud) only
```

### CSV File Format

```
(example)
==> sites.csv <==
site,lat,lon
HAWI,21.29897615,-157.81639907976145

(example)
==> slice.csv <==
site,node_name,ip_address
STAR,node0,10.0.0.2
```

## Interface
![example](./figs/example.png)
