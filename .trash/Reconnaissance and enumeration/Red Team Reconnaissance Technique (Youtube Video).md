---
tags:
aliases:
date/time: 2026-03-20 14:59
---
https://youtu.be/BWaGnsRirtU?si=M5M9TQSVKNkIA4TE
by hackersploit 
[[MightAttack]] website is mentioned 
# 1.What is reconnaissance?

The gathering of information that can be used to plan future operations involves reconnaisance. It consists of techniques that involve adversaries actively or passively, gathering ingo that can be used to support targeting. 
Examples: victim organization infrastructure or staff...

it is split into two categories:
-Active recon ( [[port scanning]], [[vuln scans]],  ) 
-passive recon ([[whois]],[[Osint]], [[DNS]], [[search engine dorcks]])

# 2.Passive Recon:

host and nslookup commands:

---->host website.org or nslookup website.org (domain)
it identifies the Ip address of the domain 

traceroute command traces the data traces from point A me to point B the website 

## DNS RECON 

dnsrecon -d domain enumerates all dns records (can be used both passif and actif)

we could deduce server records the website records the protection servers records etc...

## wafw00f (The Web Application Firewall Fingerprinting tool) 

unfortunately we can't identify the Ip address of the firewall 


## dig utility: 
- dig domain  also gets the DNS and Ip addresses of the victim

(we can add dig @ip_addresss domain and we can dig in a specific records )

dig domain ANY -> displays all the dns records 

## whois utility   

whois domain --> it gives general information about the domain registration
## netcraft site Or Dns Dumpster site 

performs a lookup and general information about a domain and some key information: expiration , some vulnerabilities, 

## whatweb utility 
command whatweb domain
it shows information, plugin banners, themes.

alternative: Whappalyzer add-on or BuiltWith add-on 

## theHarvester tool 

it is used to gather open source intelligence (OSINT) 
good useful sources to look for, google,twitter,linkedin,bing,yahoo,sublister

theHarvester -d domain -l (to limit results) -b sources 

## sublist3r command 

default command: sublist3r -d domain we can find from this command sub-domains

## google dorcks:

to search for website:
site:* domain 
to exclude results we add -site:domain
to add a key word in url we simply add inurl:keyword
example inurl:admin or inurl:login 
to limit for a specific file tyoes filetype:extention


# 3. Active recon 

## subdomain enumeration using brute force :
---> fierce tool (VERY ACTIVE TOOL)
fierce --domain domain 
--->knockpy tool 
knockpy domain 
we can use a custom word list in  in knockpy 
-> Helpful wordlists: dns-Jhaddix.txt fierce-hostlist.txt depmagic.com-prefixes.txt bitquarck-subdomains.txt 

## [[port scanning]](illegal):
Using nmap and other scanners, 
it is very extensive scanning, however ones can be send many packets and be suspicious since it is a highly active technic 

we can also use nmap to scan for vulnerabilities and heartbleed.nse to see if we can identify if the site is vulnerable to heartbleed attacks

vulnerability scanning can be used also by nikto tool 

## directory brute forcing 
we can use wfuzz gobuster ...etc 

## CMSmap tool 
is used to identify vulnerabilities in content management systems 

# 4.Automating recon 

## SN1PER framework 
it is quite an extensive framework for both active and passive recon : 
it runs a wide variety of scans and stores the results automatically, it also utilizes some technics that we have spoke of before 

the reports are stored in a folder under the directory (the path is displayed)

for  passive recon -m (mode) stealth is important to be added

## Amass apt 
1:06:00 in the video 








 




