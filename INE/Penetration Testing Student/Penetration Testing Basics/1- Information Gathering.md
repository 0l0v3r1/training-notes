# Open-Source Intelligence

## 1.2.2 Public Sites Information Gathering

* **CrunchBase**: Is an IT startup database where you can find detailed info about founders, investors, employees, buyouts and aquisitions.
* **sam.gov** and **gsaelibrary.gsa.gov**: can be used to find information about contracts between private companies and the US Government

## 1.2.3 Whois

* Use it on Linux and MacOS using `whois` commmand

***
***
# Subdomain Enumeration

## 1.3 Subdomain Enumeration

* We can use google that may index pages that were not meant for indexing
	* `site: target.com`
* [dnsdumpster](https://dnsdumpster.com/) can be used too, it utulizes data from google-indexed subdomains, but also checks sites like Bing or Virustotal for similar info
* [Sublist3r](https://github.com/aboul3la/Sublist3r) is a tool that extends the capabilities of DNS enumeration (a little bit old) check [this](https://github.com/blechschmidt/massdns)
* [AMASS](https://github.com/OWASP/Amass) is a more sophisticated tool that can be used