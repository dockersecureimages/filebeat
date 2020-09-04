# Filebeat

Filebeat, image is based on the Alpine base image with 0 vulnerabilities.

## Current Docker image (~120MB)

Security scanning using Clair
```
clair-scanner secureimages/filebeat:7.9.1-alpine-3.12.0
2020/09/04 16:15:34 [INFO] ▶ Start clair-scanner
2020/09/04 16:15:35 [INFO] ▶ Server listening on port 9279
2020/09/04 16:15:35 [INFO] ▶ Analyzing 31609b718dd2bed92b93b1ab00c0ff67419a3121d0144bef0dc6ca49718820a7
2020/09/04 16:15:35 [INFO] ▶ Analyzing 10d44b50521a3c9b79dea9294d1224822119224e0e41b6de722d14cf9a671340
2020/09/04 16:15:35 [INFO] ▶ Analyzing 2c2b2cd550a27d9dccfc754c7fb88d02c88712d9863411be2df8a240bab0c920
2020/09/04 16:15:35 [INFO] ▶ Analyzing c05ad64debefd136449b1def52ac7d59b177bc6288ce3609c60e8a01c8342c17
2020/09/04 16:15:35 [INFO] ▶ Image [secureimages/filebeat:7.9.1-alpine-3.12.0] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.11.0 --no-progress secureimages/filebeat:7.9.1-alpine-3.12.0
2020-09-04T16:15:40.671Z        INFO    Need to update DB
2020-09-04T16:15:40.671Z        INFO    Downloading DB...
2020-09-04T16:15:46.584Z        INFO    Detecting Alpine vulnerabilities...

secureimages/filebeat:7.9.1-alpine-3.12.0 (alpine 3.12.0)
=========================================================
Total: 0 (UNKNOWN: 0, LOW: 0, MEDIUM: 0, HIGH: 0, CRITICAL: 0)
```

## Official Docker image (~449MB)

[https://www.docker.elastic.co/](https://www.docker.elastic.co/)
```
docker pull docker.elastic.co/beats/filebeat:7.9.1
```

Security scanning using Clair
```
clair-scanner docker.elastic.co/beats/filebeat:7.9.1
2020/09/04 16:15:54 [INFO] ▶ Start clair-scanner
2020/09/04 16:16:01 [INFO] ▶ Server listening on port 9279
2020/09/04 16:16:01 [INFO] ▶ Analyzing 33b5e87a65b65985a0445827bd27436b3467bb578d1b1cc2aa0b6000685fb4bf
2020/09/04 16:16:01 [INFO] ▶ Analyzing da00777e9498d95e00a3121d7e07cf78d30f63f8d6cca57e0fe1470e4f07720e
2020/09/04 16:16:01 [INFO] ▶ Analyzing 4e97248d4b9aaa91f73afc29a3254a34fe963a9e48b0e9ba947184858577bc92
2020/09/04 16:16:01 [INFO] ▶ Analyzing d3ec9de5bfe8ba922daa9b502b5cbd4ff9e9bfd14d8fc9e878760926018cd778
2020/09/04 16:16:01 [INFO] ▶ Analyzing 22a605a7e114f82628fde310be9eee8a80a32c016e85331ada238826de8753fe
2020/09/04 16:16:01 [INFO] ▶ Analyzing 93761a5089dcc5e7680a605096606b59d8f49068459b5b71d4120e59d995e84d
2020/09/04 16:16:01 [INFO] ▶ Analyzing 6672cdb4844e0a13a0bd10fd5687a76aac37b43ce34d957be9cb62668e9f207f
2020/09/04 16:16:01 [INFO] ▶ Analyzing ca838dbf0398f7415f1dec994d9a961c6760fdad231caa9bbd6563e4ce67a523
2020/09/04 16:16:01 [INFO] ▶ Image [docker.elastic.co/beats/filebeat:7.9.1] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.11.0 --no-progress docker.elastic.co/beats/filebeat:7.9.1
2020-09-04T16:16:01.784Z        INFO    Need to update DB
2020-09-04T16:16:01.784Z        INFO    Downloading DB...
2020-09-04T16:16:13.125Z        INFO    Detecting RHEL/CentOS vulnerabilities...

docker.elastic.co/beats/filebeat:7.9.1 (centos 7.8.2003)
========================================================
Total: 636 (UNKNOWN: 0, LOW: 365, MEDIUM: 266, HIGH: 5, CRITICAL: 0)
```
