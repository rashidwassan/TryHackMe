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
