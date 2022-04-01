# Spring4Shell

## VULNERABILITY DESCRIPTION
Spring4Shell is a critical vulnerability that has been reported in the most widely used lightweight open source framework Spring.
A remote attacker can obtain an AccessLogValve object through the framework’s parameter binding feature and use malicious field values to trigger the pipeline mechanism and write to a file in an arbitrary path. The full-chain attack ends with  triggering remote command execution with new crafted jsp files. 


## Working Spring4Shell Proof Of Concept
Creating jsp web shell:
![Step1](/01_.jpeg)
Checking file existence:
![Step2](/02_.jpeg)
Triggering RCE:
![Step3](/03_.jpeg)

## REF

* https://www.cyberkendra.com/2022/03/springshell-rce-0-day-vulnerability.html
* https://www.springcloud.io/post/2022-03/spring-0day-vulnerability

## CVE

- No cve assigned yet

## Mitigations

### JDK Version under 9

You can easily check this by running
```sh
java -version
```

### Passive detection of vulnerable instances

Do a global search after "spring-beans-*.jar" and "spring*.jar"

```sh
find . -name spring-beans*.jar
find . -name spring*.jar
```

## Poc
poc2 i noticed to be more valid in some situation where the first poc didn't work.


## Added value
the curl one-liner easy spring4shll "scanner" (curl http://host:port/path?class.module.classLoader.URLs%5B0%5D=0) that should return 400 when a vulnerable instance is found has been noticed to be not enough cause some vulnerable endpoints return 200 as http status code and not 400 as suggested on the web.
