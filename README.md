# Filebeat

Filebeat, image is based on the Alpine base image with 0 vulnerabilities.

## Current Docker image (~101MB)

Security scanning using Clair
```
clair-scanner secureimages/filebeat:7.8.0-alpine-3.12.0
2020/06/19 21:17:01 [INFO] ▶ Start clair-scanner
2020/06/19 21:17:03 [INFO] ▶ Server listening on port 9279
2020/06/19 21:17:03 [INFO] ▶ Analyzing 76de98d374759ed05698adec9aa042db7bc0f62c25fb612c0f9be1419a581421
2020/06/19 21:17:03 [INFO] ▶ Analyzing 70c25cdd575b70b87a2b8a821b34263d72634108e7e9b429bbd4f172eddb1c7f
2020/06/19 21:17:03 [INFO] ▶ Analyzing 5fdadcdbbd82013fe5b454a6eeda061dc2ac698aefb720e2a326a746995d3e4b
2020/06/19 21:17:03 [INFO] ▶ Analyzing d87ec77d615295da8f10b0005168d1b8b0c29bdbc1fd6736443ff41075ac15e0
2020/06/19 21:17:03 [INFO] ▶ Image [secureimages/filebeat:7.8.0-alpine-3.12.0] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.9.1 --no-progress secureimages/filebeat:7.8.0-alpine-3.12.0
2020-06-19T18:17:09.401Z        INFO    Need to update DB
2020-06-19T18:17:09.401Z        INFO    Downloading DB...
2020-06-19T18:17:15.231Z        INFO    Detecting Alpine vulnerabilities...

secureimages/filebeat:7.8.0-alpine-3.12.0 (alpine 3.12.0)
=========================================================
Total: 0 (UNKNOWN: 0, LOW: 0, MEDIUM: 0, HIGH: 0, CRITICAL: 0)
```

## Official Docker image (~460MB)

[https://www.docker.elastic.co/](https://www.docker.elastic.co/)
```
docker pull docker.elastic.co/beats/filebeat:7.8.0
```

Security scanning using Clair
```
clair-scanner docker.elastic.co/beats/filebeat:7.8.0
2020/06/19 21:17:19 [INFO] ▶ Start clair-scanner
2020/06/19 21:17:26 [INFO] ▶ Server listening on port 9279
2020/06/19 21:17:26 [INFO] ▶ Analyzing c53e4ebe5d0a558645655ec8b3e667ed7cae98e3252a08914c1ab5a08cef4da0
2020/06/19 21:17:26 [INFO] ▶ Analyzing 4a952647c5cbcdd6b3e96e240ad7ff3065a9e79b0b52898611b4024e021eaf0c
2020/06/19 21:17:26 [INFO] ▶ Analyzing cc17ac19d76bd3f2983b7e553b3aa76d02767c4cecf9fc7fbfe6c9680d9b763f
2020/06/19 21:17:26 [INFO] ▶ Analyzing e1f861d11fb81971016dc44388e80262ffaaf8751d116025c8e83d78e3c44120
2020/06/19 21:17:26 [INFO] ▶ Analyzing 5f4101d286edb6985020294780d1f3b496460583c7db13e05092326a0ef01c74
2020/06/19 21:17:26 [INFO] ▶ Analyzing 52ce2b65322a2b74cda627bb2dbdaf38701aa81ec5e081e42f73c950d5e42996
2020/06/19 21:17:26 [INFO] ▶ Analyzing 0451ddb3b272514d4be294d2a6f6cfa8df7ddabc47ead8f25fb77664023b9009
2020/06/19 21:17:26 [INFO] ▶ Analyzing ee3b76ef63af36ac41fbf0fcfde2e71025c8ce780328d6403e591344219f0e31
2020/06/19 21:17:26 [INFO] ▶ Image [docker.elastic.co/beats/filebeat:7.8.0] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.9.1 --no-progress docker.elastic.co/beats/filebeat:7.8.0
2020-06-19T18:17:28.712Z        INFO    Need to update DB
2020-06-19T18:17:28.712Z        INFO    Downloading DB...
2020-06-19T18:17:42.482Z        INFO    Detecting RHEL/CentOS vulnerabilities...

docker.elastic.co/beats/filebeat:7.8.0 (centos 7.8.2003)
========================================================
Total: 614 (UNKNOWN: 0, LOW: 360, MEDIUM: 249, HIGH: 5, CRITICAL: 0)
```
