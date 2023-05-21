# DNS

## cf-ddns.sh

this file is run by Github actions for update dynamic ip address to cloudflare

Step:
You need to add secret key in environment settings
CF_KEY= Cloudflare Global API Key with Permission Zone.DNS
CF_EMAIL=Cloudflare email
CF_HOST=fqdn of the record you want to update eg. test.example.com
CF_ZONE=will show you all zones if forgot, but you need this eg. example.com
CF_TYPE=A|AAAA # specify ipv4/ipv6, default: ipv4

This will run in github action every 12:00am to update DDNS and every push event

May Encounter Error with permission right
Fix Just Run

```bash
git update-index --chmod=+x .\ddns\cf-ddns.sh
```

How to run locally:
[git clones](https://github.com/yeoyck/script.git)

For Window (Require install Bash you can run in git bash) similar linux steps

For linux

```bash
cd script
chmod a+x ddns/cf-ddns.sh
cf-ddns.sh cf-ddns.sh -k cloudflare-api-key  -u user@example.com  -h host.example.com  -z example.com  -t A|AAAA 
```
