# owasp zaproxy
### Leaning zaproxy 
zaproxy has 2 types of crawlers - Standard/Traditional Spider and AJAX Spider.
1. Standard/Traditional Spider
   The Spider is a tool that is used to automatically discover new resources (URLs) on a particular Site. It begins with a list of URLs to visit, called the seeds, which depends on how the Spider is started. The Spider then visits these URLs, it identifies all the hyperlinks in the page and adds them to the list of URLs to visit and the process continues recursively as long as new resources are found.

2. AJAX Spider
   The AJAX Spider add-on integrates in ZAP a crawler of AJAX rich sites called Crawljax. You can use it to identify the pages of the targeted site. You can combine it with the (normal) spider for better results.

All of the docker images provide a set of packaged scan scripts:
1. [ZAP - Baseline Scan](zap_baseline.md) - which runs the ZAP spider against the target for (by default) 1 minute followed by an optional ajax spider scan before reporting the results of the passive scanning.
2. [ZAP - Full Scan](zap_full_scan.md) - which runs the ZAP spider against the target (by default with no time limit) followed by an optional ajax spider scan and then a full active scan before reporting the results.
3. [ZAP - API Scan](zap_api_scan.md) - which performs an active scan against APIs defined by OpenAPI, or GraphQL (post 2.9.0) via either a local file or a URL.

The packaged scans are the simplest way to automate ZAP in docker.

List of passive and active http scan rules are found here - https://www.zaproxy.org/docs/alerts/
