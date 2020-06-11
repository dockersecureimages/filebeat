# Filebeat

Filebeat, image is based on the Alpine base image with 0 vulnerabilities.

## Current Docker image (~99.2MB)

Security scanning using Clair
```
clair-scanner secureimages/filebeat:7.7.1-alpine-3.12.0
2020/06/11 13:29:49 [INFO] ▶ Start clair-scanner
2020/06/11 13:29:50 [INFO] ▶ Server listening on port 9279
2020/06/11 13:29:50 [INFO] ▶ Analyzing 76de98d374759ed05698adec9aa042db7bc0f62c25fb612c0f9be1419a581421
2020/06/11 13:29:50 [INFO] ▶ Analyzing 0307a2ff6a8314ba71e5b2179c4443c84ad2b53009ee443fd2634385e9490b52
2020/06/11 13:29:50 [INFO] ▶ Analyzing d9e072251923e0070616937210f1b3229c4ef84164f83b48241395de4ed3b8e9
2020/06/11 13:29:50 [INFO] ▶ Analyzing 45e242c1e50ee007ecc08739c72e44ea22fff912f20119efa5ea1f23e0817966
2020/06/11 13:29:50 [INFO] ▶ Image [secureimages/filebeat:7.7.1-alpine-3.12.0] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.9.1 --no-progress secureimages/filebeat:7.7.1-alpine-3.12.0
2020-06-11T10:29:56.143Z        INFO    Need to update DB
2020-06-11T10:29:56.143Z        INFO    Downloading DB...
2020-06-11T10:30:01.204Z        INFO    Detecting Alpine vulnerabilities...

secureimages/filebeat:7.7.1-alpine-3.12.0 (alpine 3.12.0)
=========================================================
Total: 0 (UNKNOWN: 0, LOW: 0, MEDIUM: 0, HIGH: 0, CRITICAL: 0)
```

## Official Docker image (~456MB)

[https://www.docker.elastic.co/](https://www.docker.elastic.co/)
```
docker pull docker.elastic.co/beats/filebeat:7.7.1
```

Security scanning using Clair
```
clair-scanner docker.elastic.co/beats/filebeat:7.7.1
2020/06/11 13:30:06 [INFO] ▶ Start clair-scanner
2020/06/11 13:30:12 [INFO] ▶ Server listening on port 9279
2020/06/11 13:30:12 [INFO] ▶ Analyzing c53e4ebe5d0a558645655ec8b3e667ed7cae98e3252a08914c1ab5a08cef4da0
2020/06/11 13:30:12 [INFO] ▶ Analyzing 4a0bece506173717df0b3d9227f4a19d291c86ff4676d75b35fd22fef9daa5ef
2020/06/11 13:30:12 [INFO] ▶ Analyzing b2fa22acd06f073df06771e6ac177c36fb4feb2c7661157bb453a271cfa9561c
2020/06/11 13:30:12 [INFO] ▶ Analyzing 17f19ec01a2a02aecdabe21a6b8f4cf911efc85a969a29e6c73ce3653ade9448
2020/06/11 13:30:12 [INFO] ▶ Analyzing 9dd7c96d6ae17a6a94d6dda4a3edbc3f870569492a153af095c057588ef01f95
2020/06/11 13:30:12 [INFO] ▶ Analyzing 70a9ae5129654d4a241a6db1b755eb2edd75867503f8aba2efd69e264ce74942
2020/06/11 13:30:12 [INFO] ▶ Analyzing b6b9721801be9f70ec736895d1e6f9735734c3b767862d71f42b7670503b1a3f
2020/06/11 13:30:12 [INFO] ▶ Analyzing f53d2fe84324086a025933331a40de71e918fe7d07215bdc1a9d9a01ee0e5f29
2020/06/11 13:30:12 [WARN] ▶ Image [docker.elastic.co/beats/filebeat:7.7.1] contains 1 total vulnerabilities
2020/06/11 13:30:12 [ERRO] ▶ Image [docker.elastic.co/beats/filebeat:7.7.1] contains 1 unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.9.1 --no-progress docker.elastic.co/beats/filebeat:7.7.1
2020-06-11T10:30:14.704Z        INFO    Need to update DB
2020-06-11T10:30:14.704Z        INFO    Downloading DB...
2020-06-11T10:30:25.633Z        INFO    Detecting RHEL/CentOS vulnerabilities...

docker.elastic.co/beats/filebeat:7.7.1 (centos 7.8.2003)
========================================================
Total: 610 (UNKNOWN: 0, LOW: 362, MEDIUM: 241, HIGH: 7, CRITICAL: 0)
```
