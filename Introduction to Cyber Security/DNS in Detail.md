# DNS in Detail

- DNS (Domain Name System)
- Allows us to browse web easily without remembering complicated numbers (IP Addresses)
- So instead of remembering `104.26.10.229`, you can remember `tryhackme.com` instead.

## Domain Hierarchy

### TLD (Top Level Domain)
- Most righthand part of a domain name i.e facebook`.com`
- Two Types
  - **gTLD:** Generic Top Level Domain. This is used to give the idea of the purpose of the domain's name i.e `.edu` for education.
  - **ccTLD:** Country Code Top Level Domain. Examples: .pk, .in, and .uk.

### Second Level Domain
- Taking `facebook.com` as an example, the `.com` part is the **TLD**, and `facebook` is the Second Level Domain.
- When registering a domain name, the second-level domain is limited to 63 characters + the TLD and can only use a-z 0-9 and hyphens (cannot start or end with hyphens or have consecutive hyphens).


### Subdomain
- Sits on the left-hand side of the Second-Level Domain using a period to separate it.
- In the name `admin.tryhackme.com` the **admin** part is the subdomain.
- Length must be kept to 253 characters or less.
- There is no limit to the number of subdomains you can create for your domain name.

### DNS Record Types
- DNS isn't just for websites though, and multiple types of DNS record exist.
- `A Record:` These records resolve to IPv4 addresses, for example 104.26.10.229
- `AAAA Record:` These records resolve to IPv6 addresses, for example 2606:4700:20::681a:be5
- `CNAME Reocord:` These records resolve to another domain name, for example, TryHackMe's online shop has the subdomain name store.tryhackme.com which returns a CNAME record shops.shopify.com. Another DNS request would then be made to shops.shopify.com to work out the IP address.
- `MX Record:` These records resolve to the address of the servers that handle the email for the domain you are querying, for example an MX record response for tryhackme.com would look something like alt1.aspmx.l.google.com.
- `TXT Record:` TXT records are free text fields where any text-based data can be stored. TXT records have multiple uses, but some common ones can be to list servers that have the authority to send an email on behalf of the domain (this can help in the battle against spam and spoofed email).


### What happens when you make a DNS request?
- 1: When you request a domain name, your computer first checks its local cache to see if you've previously looked up the address recently; if not, a request to your Recursive DNS Server will be made.
- 2: A Recursive DNS Server is usually provided by your ISP, but you can also choose your own. If the request cannot be found locally, a journey begins to find the correct answer, starting with the internet's root DNS servers.
- 3: The root servers act as the DNS backbone of the internet; their job is to redirect you to the correct Top Level Domain Server, depending on your request.
- 4: The TLD server holds records for where to find the authoritative server (nameserver) to answer the DNS request.
- 5: An authoritative DNS server is the server that is responsible for storing the DNS records for a particular domain name and where any updates to your Depending on the record type, the DNS record is then sent back to the Recursive DNS Server, where a local copy will be cached for future requests and then relayed back to the original client that made the request.
