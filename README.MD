# Automated Websecurity Assessment 
## Using OWASP ZAP and Automation Framework

## Files
- DVWA.yaml - Automation script written in YAML for the ZAP Automation Framework, containing all informations related to the application, passive checks, actives scans and report.
- DVWA-Report.json - OWASP ZAP vulnerability report in json.

## Requirements
- OWASP ZAP
- DVWA running at http://192.168.63.128/dvwa


**How to execute:**
With the yaml file it's possible to run automated scans from a regular workstation or inside a docker.
```
zap.sh -cmd -autorun DVWA.yaml
```

**docker**
```
docker pull owasp/zap2docker-stable
docker run -v $(pwd):/zap/wrk/:rw -t owasp/zap2docker-stable bash -c "zap.sh -cmd -addonupdate; zap.sh -cmd -autorun /zap/wrk/DVWA.yaml"
```
