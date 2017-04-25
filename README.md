DNS Query Tool
==============

Connect to a DNS server and query for DNS hostname or IP address.

## Running

Run using either as bash script or python script.

### Python Script

Execute the script using `python dnsq.py`.
To get help, use the `-h` flag (e.g. `python dnsq.py -h`).

### Bash Script

To run bash script, first `chmod +x dnsq` to change permissions.
Then, execute the tool using `./dnsq`. To get help,
use the `-h` flag (e.g. `./dnsq -h`).

## Example

This is an example to run for the purposes of the lab:
    ./dnsq -v --nameserver=8.8.8.8 wikipedia.org
