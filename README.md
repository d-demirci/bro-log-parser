# Bro log parser
Simple logfile parser for [Bro IDS](https://www.bro.org/). This library parses and transforms entries 
in a logfile created by the [ASCII Writer](https://www.bro.org/sphinx/frameworks/logging.html#ascii-writer)
into a dynamically generated namedtuple. Fields are converted into native python data types.

## Requirements
* python3
 
## Install
    python3 setup.py install

## Example
```python
>>> from brologparse import parse_log
>>> for entry in parse_log("conn.log"):
...     # entry._fields: Tuple of strings listing the field names
...     # entry._asdict(): Return a new OrderedDict which maps field names to their corresponding values
...     print(entry)
...
ConnEntry(
    ts=datetime.datetime(2015, 1, 23, 0, 49, 13, 396481),
    uid='CjPbcf1SkE86OWWTra', 
    id_orig_h=IPv4Address('192.168.1.100'),
    id_orig_p=137,
    id_resp_h=IPv4Address('192.168.1.255'),
    id_resp_p=137,
    proto='udp',
    service='dns',
    duration=0.752894,
    orig_bytes=100,
    resp_bytes=0,
    conn_state='S0',
    local_orig=None,
    local_resp=None,
    missed_bytes=0,
    history='D',
    orig_pkts=2,
    orig_ip_bytes=156,
    resp_pkts=0,
    resp_ip_bytes=0,
    tunnel_parents=None
)
```
## License

MIT

## Author Information

Fabian Weisshaar <elnappo@nerdpol.io>
