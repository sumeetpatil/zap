# zap
### Leaning zap 
Zap has 2 types of crawlers - Standard/Traditional Spider and AJAX Spider.
1. Standard/Traditional Spider
   The Spider is a tool that is used to automatically discover new resources (URLs) on a particular Site. It begins with a list of URLs to visit, called the seeds, which depends on how the Spider is started. The Spider then visits these URLs, it identifies all the hyperlinks in the page and adds them to the list of URLs to visit and the process continues recursively as long as new resources are found.

2. AJAX Spider
   The AJAX Spider add-on integrates in ZAP a crawler of AJAX rich sites called Crawljax. You can use it to identify the pages of the targeted site. You can combine it with the (normal) spider for better results.

Docker Scans - 
1. [ZAP - Baseline Scan](zap_baseline.md)

List of passive and active http scan rules are found here - https://www.zaproxy.org/docs/alerts/
