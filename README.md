# SMTPTester

SMTPTester is a python3 tool to test SMTP server for 3 common vulnerabilities:
* Spoofing - The ability to send a mail on behalf of an internal user
* Relay - Using this SMTP server to send email to other address outside of the organization
* user enumeration - using the SMTP VRFY command to check if specific username and\or email address exist within the organization.

## How to use it
First, install the needed dependencies:
```
pip install -r requirments.txt
```
Second, run the tool with the needed flags:
```
python SMTPTester.py --tester [tester email] --targets [SMTP IP or file containing multiple IPs]
```

## Options to consider
* -i\\--internal
  * testing only for mail spoofing
* -e\\--external
  * only testing for mail relay
* -v\\--vrfy
  * only perform user enumeration
the tool will perform both internal and external when no specific test type is specified, and will append the output to a log file on the same folder as the SMTPTester.py file. 

## Docker Build
```
docker build -t <IMAGE NAME> .
docker build -t xshuden/smtptester .
```

## Docker Run
```
docker run --rm -it xshuden/smtptester
```
