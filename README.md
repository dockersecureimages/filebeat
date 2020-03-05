# Filebeat

Filebeat, image is based on the Alpine base image with 0 vulnerabilities.

## Current Docker image

Security scanning using Clair
```
clair-scanner secureimages/filebeat:7.6.1-alpine-3.11.3
2020/03/05 15:24:06 [INFO] ▶ Start clair-scanner
2020/03/05 15:24:07 [INFO] ▶ Server listening on port 9279
2020/03/05 15:24:07 [INFO] ▶ Analyzing c60e0e5e0b8cce2c353f5af4186afb2cde56680bc78ff165fd2368a003530178
2020/03/05 15:24:07 [INFO] ▶ Analyzing 1a725b48a2b37a639dbeea428ee02b895d3bf0b88a15e151a667e05f2a413aea
2020/03/05 15:24:07 [INFO] ▶ Analyzing e85460c1e23d518ba4a12e5c987136b7c514773313ef470f698b1445b11648fc
2020/03/05 15:24:07 [INFO] ▶ Analyzing c3e313cd21a05b47e326734a17cc016edde06a04119cd05073c9ded68cc0adca
2020/03/05 15:24:07 [INFO] ▶ Image [secureimages/filebeat:7.6.1-alpine-3.11.3] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.4.4 --no-progress secureimages/filebeat:7.6.1-alpine-3.11.3
2020-03-05T13:24:13.951Z        INFO    Need to update DB
2020-03-05T13:24:13.951Z        INFO    Downloading DB...
2020-03-05T13:24:17.857Z        INFO    Reopening DB...
2020-03-05T13:24:19.218Z        INFO    Detecting Alpine vulnerabilities...

secureimages/filebeat:7.6.1-alpine-3.11.3 (alpine 3.11.3)
=========================================================
Total: 0 (UNKNOWN: 0, LOW: 0, MEDIUM: 0, HIGH: 0, CRITICAL: 0)
```

## Official Docker image

[https://www.docker.elastic.co/](https://www.docker.elastic.co/)
```
docker pull docker.elastic.co/beats/filebeat:7.6.1
```

Security scanning using Clair
```
clair-scanner docker.elastic.co/beats/filebeat:7.6.1
2020/03/05 15:24:24 [INFO] ▶ Start clair-scanner
2020/03/05 15:24:30 [INFO] ▶ Server listening on port 9279
2020/03/05 15:24:30 [INFO] ▶ Analyzing efabb8e7a64ff0670af40775b5aa02a8e19f73baa9f9e24aef8ce37a563f632d
2020/03/05 15:24:30 [INFO] ▶ Analyzing 0db6045735b02268054781a13d0b6b88f43f99f3a7da684696366195bd1e7284
2020/03/05 15:24:30 [INFO] ▶ Analyzing 4b3a8b9001b3e27157b28f6de9ebc73ec011278c493fb2ce9d41204646f4c7df
2020/03/05 15:24:30 [INFO] ▶ Analyzing f81d6a7971e1f5e99c989d9b35fe77d2aa4c0bbdca67ae5993283cc104b5c62a
2020/03/05 15:24:30 [INFO] ▶ Analyzing aafa8e855419644a1429299c91f7fda262df77e7bc2e4af31f9f25d27c33689b
2020/03/05 15:24:30 [INFO] ▶ Analyzing da1ec8cf896f03b035f081b445b6bea4a705071ac18efb4c66aca96f5b4fa9ea
2020/03/05 15:24:30 [INFO] ▶ Analyzing e6110c3a36fb9f8c1527744857ba47aa2fefe6f97b2986b0bdd84f6d02c0d252
2020/03/05 15:24:30 [WARN] ▶ Image [docker.elastic.co/beats/filebeat:7.6.1] contains 7 total vulnerabilities
2020/03/05 15:24:30 [ERRO] ▶ Image [docker.elastic.co/beats/filebeat:7.6.1] contains 7 unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.4.4 --no-progress docker.elastic.co/beats/filebeat:7.6.1
2020-03-05T13:24:34.732Z        INFO    Need to update DB
2020-03-05T13:24:34.732Z        INFO    Downloading DB...
2020-03-05T13:24:38.740Z        INFO    Reopening DB...
2020-03-05T13:24:44.539Z        INFO    Detecting RHEL/CentOS vulnerabilities...

docker.elastic.co/beats/filebeat:7.6.1 (centos 7.7.1908)
========================================================
Total: 634 (UNKNOWN: 0, LOW: 61, MEDIUM: 468, HIGH: 102, CRITICAL: 3)
```
