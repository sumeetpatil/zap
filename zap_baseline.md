# Run zap baseline scan

- It runs the ZAP spider against the specified target for (by default) 1 minute and then waits for the passive scanning to complete before reporting the results.
- This means that the script doesn’t perform any actual ‘attacks’ and will run for a relatively short period of time (a few minutes at most).
- We can run baseline scan for a website with just this command `docker run -v $(pwd):/zap/wrk/:rw -t owasp/zap2docker-live zap-baseline.py \
    -t http://10.236.195.229:49161 -g gen.conf -r testreport.html`.
- This can also be integrated with Jenkins, Travis or any automation tool which has docker installed. 
- More information - https://www.zaproxy.org/docs/docker/baseline-scan/
