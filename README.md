# EncryptedDnsPcaps
Pcap collection of encrypted DNS or DoH or DNS over HTTPS

Make DNS-over-HTTPS queries via command line using cURL -
curl -kv -H 'accept: application/dns-json' 'https://<DoH-server-name>/dns-query?name=<domain-to-resolve>&type=<query-type>'

example -
curl -kv -H 'accept: application/dns-json' 'https://cloudflare-dns.com/dns-query?name=bbc.co.uk&type=A'

you can bypass DNS-based protections like OpenDNS/Cisco Umbrella , by directly using the IP address of the DoH Server like -
curl -kv -H 'accept: application/dns-json' 'https://1.1.1.1/dns-query?name=bbc.co.uk&type=A'

You should get a response in the form of a JSON like -
{"Status": 0,"TC": false,"RD": true, "RA": true, "AD": false,"CD": false,"Question":[{"name": "bbc.co.uk.", "type": 1}],"Answer":[{"name": "bbc.co.uk.", "type": 1, "TTL": 156, "data": "151.101.0.81"},{"name": "bbc.co.uk.", "type": 1, "TTL": 156, "data": "151.101.64.81"},{"name": "bbc.co.uk.", "type": 1, "TTL": 156, "data": "151.101.128.81"},{"name": "bbc.co.uk.", "type": 1, "TTL": 156, "data": "151.101.192.81"}]}
