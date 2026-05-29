# Lab 02: DNS TTL Lookup

## Objective

Use a DNS lookup command to observe DNS resolution and Time to Live behavior.

## Scenario

A DNS lookup is performed for a website to identify its A record and TTL value.

## Command Used

```bash
dig www.professormesser.com A
```

## Command Output

```text
;; ANSWER SECTION:
www.professormesser.com. 300 IN A 172.66.174.118
www.professormesser.com. 300 IN A 104.20.22.204

;; Query time: 71 msec
;; SERVER: 2001:558:feed::1#53(2001:558:feed::1)
```
