#Automate Websecurity Assessment 
##Using OWASP ZAP and Automation Framework

##Pre-req
OWASP ZAP

##Predefine application : 
DVWA running at http://192.168.63.128/dvwa
DVWA.yaml - File containing all informations related to the application, passive and actives scan rules and report.


##How to execute:
With the yaml file it's possible to run automated scans from a regular workstation or inside a docker.
zap.sh -cmd -autorun DVWA.yaml

>docker  
docker pull owasp/zap2docker-stable
docker run -v $(pwd):/zap/wrk/:rw -t owasp/zap2docker-stable bash -c "zap.sh -cmd -addonupdate; zap.sh -cmd -autorun /zap/wrk/DVWA.yaml"