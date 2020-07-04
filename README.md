## cf-check
Check an IP is Owned by Cloudflare.

## Install
```
▶ go get -u github.com/dwisiswant0/cf-check
```

## Usage
```
▶ echo "uber.com" | cf-check
```

### Flags

```
  -c int
        Set the concurrency level (default 20)
  -d    Prints domain instead of IP address
```

## Workaround

The goal is that you don't need to do a port scan if it's proven that the IP is owned by Cloudflare.

```
▶ subfinder -silent -d uber.com | filter-resolved | cf-check | sort -u | naabu -silent -verify | httprobe
```