# latency-dashboard

## Purpose

A simple latency monitoring dashboard for the testbed collected through  [OWL](
https://github.com/fabric-testbed/owl) running on a slice


## Usage

```
# First time only
python3 -m venv .venv
source .venv/bin/activate

# If necesssary
pip install -r requirements.txt

python app.py
```

Then, connect to `http://127.0.0.1:8050/`


## Required Files

- `./data/sites.csv`: FABRIC sites latitudes and longitudes
- `./data/slice.csv`: Information on the FABRIC slice used for this data collection
- `influxdb.conf`: For accessing InfluxDB.


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
==> sites.csv <==
site,lat,lon

(example)
HAWI,21.29897615,-157.81639907976145


==> slice.csv <==
site,node_name,ip_address

(example)
STAR,node0,10.0.0.2
```

## Interface
![example](./figs/example.png)
