#!/usr/bin/env python
#

import sys, time, argparse
import dns.resolver

# Define default constants
default_port = 53
default_timeout = 10.0 # in seconds
default_nameserver = '8.8.8.8'

# Parse the command line options (and generate help)
parser = argparse.ArgumentParser(
    description='Connect to a DNS server and query for DNS hostname or IP address.')
parser.add_argument('-v', help='Increase output verbosity', action='store_true')
parser.add_argument('--port', help='Set the port for DNS', 
                    type=int, default=default_port, metavar='PORT')
parser.add_argument('--timeout', help='Set the timeout for the query', 
                    type=float, default=default_timeout, metavar='TIMEOUT')
parser.add_argument('--nameserver', help='The DNS nameserver to query', 
                    type=str, default=default_nameserver, metavar='NAMESERVER')
parser.add_argument('hostname', type=str, help='The DNS hostname or IP address to query')
args = parser.parse_args()


# Create the DNS resolver
dns_resolver = dns.resolver.Resolver()

if args.v: print('\x1b[0;33;40m' + 'Setup DNS resolver.' + '\x1b[0m')

# Set nameserver on resolver
dns_resolver.nameservers = [args.nameserver]

# Set timeout on resolver
dns_resolver.timeout = args.timeout

# Set port on resolver
dns_resolver.port = args.port

if args.v: print('\x1b[0;33;40m' + 'Query the DNS server.' + '\x1b[0m')

# Run DNS query
dns_answer = dns_resolver.query(args.hostname)

if args.v: print('\x1b[0;33;40m' + 'Query run successfully.' + '\x1b[0m')

# Print results of DNS query
if args.v: print('')
print('\x1b[1;32;40m' + 'Query Response:' + '\x1b[0m')
print(dns_answer.response)
