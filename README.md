# Filebeat

Filebeat, image is based on the Alpine base image with 0 vulnerabilities.

## Current Docker image (~102MB)

Security scanning using Clair
```
clair-scanner secureimages/filebeat:7.8.1-alpine-3.12.0
2020/07/31 16:58:34 [INFO] ▶ Start clair-scanner
2020/07/31 16:58:35 [INFO] ▶ Server listening on port 9279
2020/07/31 16:58:35 [INFO] ▶ Analyzing 76de98d374759ed05698adec9aa042db7bc0f62c25fb612c0f9be1419a581421
2020/07/31 16:58:35 [INFO] ▶ Analyzing b1bc184d85cb0bf29353028daee41c32fb0be119f91dec00d640e02b08a9107a
2020/07/31 16:58:35 [INFO] ▶ Analyzing 07dcdb38307f12cd4d616b765c8ce1aa8f525fef522177c7c7881b1a5f022b74
2020/07/31 16:58:35 [INFO] ▶ Analyzing 33d4cdab4414a6ec01e4ae783a1774833c9a651e03e08011f3d4fada6deadac6
2020/07/31 16:58:35 [INFO] ▶ Image [secureimages/filebeat:7.8.1-alpine-3.12.0] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.10.1 --no-progress secureimages/filebeat:7.8.1-alpine-3.12.0
2020-07-31T13:58:41.109Z        INFO    Need to update DB
2020-07-31T13:58:41.109Z        INFO    Downloading DB...
2020-07-31T13:58:46.654Z        INFO    Detecting Alpine vulnerabilities...

secureimages/filebeat:7.8.1-alpine-3.12.0 (alpine 3.12.0)
=========================================================
Total: 0 (UNKNOWN: 0, LOW: 0, MEDIUM: 0, HIGH: 0, CRITICAL: 0)
```

## Official Docker image (~463MB)

[https://www.docker.elastic.co/](https://www.docker.elastic.co/)
```
docker pull docker.elastic.co/beats/filebeat:7.8.1
```

Security scanning using Clair
```
clair-scanner docker.elastic.co/beats/filebeat:7.8.1
2020/07/31 16:58:52 [INFO] ▶ Start clair-scanner
2020/07/31 16:58:58 [INFO] ▶ Server listening on port 9279
2020/07/31 16:58:58 [INFO] ▶ Analyzing c53e4ebe5d0a558645655ec8b3e667ed7cae98e3252a08914c1ab5a08cef4da0
2020/07/31 16:58:58 [INFO] ▶ Analyzing 353a591338e2c4ec216ff7e88ffac41a21c3c3b2d85c00e35384ea8f153c835f
2020/07/31 16:58:58 [INFO] ▶ Analyzing bf4c2e02adce9aef3e345e1353d7c5973ecb7335a77504daa8cf16aeb0d40b5f
2020/07/31 16:58:59 [INFO] ▶ Analyzing 96baf0b2c666a0fa3f6d447074cb09381e9f2026b0ef6c9618dd4d3248604285
2020/07/31 16:58:59 [INFO] ▶ Analyzing cbc243f4d7bfce56f303dd118f9b7940553d5e9b42e39b646bb3c3012075ecdb
2020/07/31 16:58:59 [INFO] ▶ Analyzing c53d7ca2d7b3b4915d7fd5f56adbc8d8e7882ecc2de6322a4af99d0dd38c9704
2020/07/31 16:58:59 [INFO] ▶ Analyzing 3ee74b22c515ce27b7a11046fa193a707147ad14526c13817a0cd6e3b4b893fe
2020/07/31 16:58:59 [INFO] ▶ Analyzing b10ef791065f90632b1b4c1d9f1e0ccfc63a691a5c1c910322ccee5bcfd408f7
2020/07/31 16:58:59 [INFO] ▶ Image [docker.elastic.co/beats/filebeat:7.8.1] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.10.1 --no-progress docker.elastic.co/beats/filebeat:7.8.1
2020-07-31T13:59:00.921Z        INFO    Need to update DB
2020-07-31T13:59:00.921Z        INFO    Downloading DB...
2020-07-31T13:59:13.630Z        INFO    Detecting RHEL/CentOS vulnerabilities...

docker.elastic.co/beats/filebeat:7.8.1 (centos 7.8.2003)
========================================================
Total: 618 (UNKNOWN: 0, LOW: 361, MEDIUM: 252, HIGH: 5, CRITICAL: 0)
```
