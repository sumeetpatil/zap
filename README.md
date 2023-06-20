# owasp zaproxy
### Leaning zaproxy 
zaproxy has 2 types of crawlers - Standard/Traditional Spider and AJAX Spider.
1. Standard/Traditional Spider
   The Spider is a tool that is used to automatically discover new resources (URLs) on a particular Site. It begins with a list of URLs to visit, called the seeds, which depends on how the Spider is started. The Spider then visits these URLs, it identifies all the hyperlinks in the page and adds them to the list of URLs to visit and the process continues recursively as long as new resources are found.

2. AJAX Spider
   The AJAX Spider add-on integrates in ZAP a crawler of AJAX rich sites called Crawljax. You can use it to identify the pages of the targeted site. You can combine it with the (normal) spider for better results.

All of the docker images provide a set of packaged scan scripts:
### ZAP Baseline Scan
- It runs the ZAP spider against the specified target for (by default) 1 minute and then waits for the passive scanning to complete before reporting the results.
- This means that the script doesn’t perform any actual ‘attacks’ and will run for a relatively short period of time (a few minutes at most).
- We can run baseline scan for a website with just this command 
   `docker run -v $(pwd):/zap/wrk/:rw -t owasp/zap2docker-live zap-baseline.py -t http://IP_ADDRESS:PORT -g gen.conf -r testreport.html`.
- More information - https://www.zaproxy.org/docs/docker/baseline-scan/

### ZAP Full Scan
- It runs the ZAP spider against the specified target (by default with no time limit) followed by an optional ajax spider scan and then a full active scan before reporting the results.
- This means that the script does perform actual ‘attacks’ and can potentially run for a long period of time.
- We can run this with command
  `docker run -v $(pwd):/zap/wrk/:rw -t owasp/zap2docker-stable zap-full-scan.py -t https://www.example.com -g gen.conf -r testreport.html`
- More Information - https://www.zaproxy.org/docs/docker/full-scan/
  
### ZAP API Scan
It is tuned for performing scans against APIs defined by OpenAPI, SOAP, or GraphQL via either a local file or a URL.

It imports the definition that you specify and then runs an Active Scan against the URLs found. The Active Scan is tuned to APIs, so it doesn’t bother looking for things like XSSs.

It also includes 2 scripts that:

- Raise alerts for any HTTP Server Error response codes
- Raise alerts for any URLs that return content types that are not usually associated with APIs

```
Usage: zap-api-scan.py -t <target> -f <format> [options]
    -t target         target API definition, OpenAPI or SOAP, local file or URL, e.g. https://www.example.com/openapi.json
                      or target endpoint URL, GraphQL, e.g. https://www.example.com/graphql
    -f format         openapi, soap, or graphql
```

The packaged scans are the simplest way to automate ZAP in docker.

List of passive and active http scan rules are found here - https://www.zaproxy.org/docs/alerts/



### Driving OWASP ZAP with Selenium
[Driving OWASP ZAP with Selenium](https://owasp.org/www-chapter-london/assets/slides/OWASPLondon-OWASP-ZAP-Selenium-20180830-PDF.pdf)
