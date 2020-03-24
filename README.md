# Filebeat

Filebeat, image is based on the Alpine base image with 0 vulnerabilities.

## Current Docker image

Security scanning using Clair
```
clair-scanner secureimages/filebeat:7.6.1-alpine-3.11.5
2020/03/24 18:50:58 [INFO] ▶ Start clair-scanner
2020/03/24 18:50:59 [INFO] ▶ Server listening on port 9279
2020/03/24 18:50:59 [INFO] ▶ Analyzing dac63304c60354902922613d675ec533c6e10879f72d49b7602575ae5d5f9257
2020/03/24 18:50:59 [INFO] ▶ Analyzing 1c864994e70b080a38c8e749819cea19478e947b7e1be258b9653bbf5d352f21
2020/03/24 18:50:59 [INFO] ▶ Analyzing da7903c5e494b637e747d7a86f53de525f9463d16efe04e41303fad60b7a1f1a
2020/03/24 18:50:59 [INFO] ▶ Analyzing 5dc481ac49c09b2be2a46c8909fb6cf003a6b589dd31e4f0062a79a147aa0077
2020/03/24 18:50:59 [INFO] ▶ Image [secureimages/filebeat:7.6.1-alpine-3.11.5] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.5.3 --no-progress secureimages/filebeat:7.6.1-alpine-3.11.5
2020-03-24T16:51:05.180Z        INFO    Need to update DB
2020-03-24T16:51:05.180Z        INFO    Downloading DB...
2020-03-24T16:51:10.128Z        INFO    Reopening DB...
2020-03-24T16:51:11.864Z        INFO    Detecting Alpine vulnerabilities...

secureimages/filebeat:7.6.1-alpine-3.11.5 (alpine 3.11.5)
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
2020/03/24 18:51:16 [INFO] ▶ Start clair-scanner
2020/03/24 18:51:21 [INFO] ▶ Server listening on port 9279
2020/03/24 18:51:21 [INFO] ▶ Analyzing efabb8e7a64ff0670af40775b5aa02a8e19f73baa9f9e24aef8ce37a563f632d
2020/03/24 18:51:21 [INFO] ▶ Analyzing 0db6045735b02268054781a13d0b6b88f43f99f3a7da684696366195bd1e7284
2020/03/24 18:51:21 [INFO] ▶ Analyzing 4b3a8b9001b3e27157b28f6de9ebc73ec011278c493fb2ce9d41204646f4c7df
2020/03/24 18:51:21 [INFO] ▶ Analyzing f81d6a7971e1f5e99c989d9b35fe77d2aa4c0bbdca67ae5993283cc104b5c62a
2020/03/24 18:51:22 [INFO] ▶ Analyzing aafa8e855419644a1429299c91f7fda262df77e7bc2e4af31f9f25d27c33689b
2020/03/24 18:51:22 [INFO] ▶ Analyzing da1ec8cf896f03b035f081b445b6bea4a705071ac18efb4c66aca96f5b4fa9ea
2020/03/24 18:51:22 [INFO] ▶ Analyzing e6110c3a36fb9f8c1527744857ba47aa2fefe6f97b2986b0bdd84f6d02c0d252
2020/03/24 18:51:22 [WARN] ▶ Image [docker.elastic.co/beats/filebeat:7.6.1] contains 7 total vulnerabilities
2020/03/24 18:51:22 [ERRO] ▶ Image [docker.elastic.co/beats/filebeat:7.6.1] contains 7 unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.5.3 --no-progress docker.elastic.co/beats/filebeat:7.6.1
2020-03-24T16:51:24.897Z        INFO    Need to update DB
2020-03-24T16:51:24.897Z        INFO    Downloading DB...
2020-03-24T16:51:30.982Z        INFO    Reopening DB...
2020-03-24T16:51:38.287Z        INFO    Detecting RHEL/CentOS vulnerabilities...

docker.elastic.co/beats/filebeat:7.6.1 (centos 7.7.1908)
========================================================
Total: 642 (UNKNOWN: 0, LOW: 65, MEDIUM: 468, HIGH: 106, CRITICAL: 3)
```
