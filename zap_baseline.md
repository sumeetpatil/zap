# Run zap baseline scan

- We can run baseline scan for a website with just this command `docker run -v $(pwd):/zap/wrk/:rw -t owasp/zap2docker-live zap-baseline.py \
    -t http://10.236.195.229:49161 -g gen.conf -r testreport.html`.
- More information - https://www.zaproxy.org/docs/docker/baseline-scan/
- This can also be integrated with Jenkins, Travis or any automation tool which has docker installed. 
