# Spring4Shell
Working Spring4Shell Proof Of Concept

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
Change proxy address :)
