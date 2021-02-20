# Filebeat

Filebeat, image is based on the Alpine base image with 0 vulnerabilities.

## Current Docker image (~134MB)

Security scanning using Clair
```
clair-scanner secureimages/filebeat:7.11.1-alpine-3.13.2
2021/02/20 14:07:38 [INFO] ▶ Start clair-scanner
2021/02/20 14:07:39 [INFO] ▶ Server listening on port 9279
2021/02/20 14:07:39 [INFO] ▶ Analyzing b73bac2fe5a7b9d1abcbf0138798281e20b11e59b4605b104d38e914fa35b4d2
2021/02/20 14:07:39 [INFO] ▶ Analyzing b586b65594e155db285f3603498c511abcc4f9326978f388d72c23d9e19f1e9a
2021/02/20 14:07:40 [INFO] ▶ Analyzing 11074a0eb17c52c89fc7b38aabe87abe4866d5d7fd3222088d8979d2256c6553
2021/02/20 14:07:40 [INFO] ▶ Analyzing c6740d2cbafd1429ac712e19156aadc6bbfa67ab441f6198eb5d0b6a95ebdf72
2021/02/20 14:07:40 [WARN] ▶ Image [secureimages/filebeat:7.11.1-alpine-3.13.2] contains 1 total vulnerabilities
2021/02/20 14:07:40 [ERRO] ▶ Image [secureimages/filebeat:7.11.1-alpine-3.13.2] contains 1 unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.16.0 --no-progress secureimages/filebeat:7.11.1-alpine-3.13.2
2021-02-20T14:07:45.386Z        INFO    Need to update DB
2021-02-20T14:07:45.386Z        INFO    Downloading DB...
2021-02-20T14:07:49.715Z        INFO    Detecting Alpine vulnerabilities...
2021-02-20T14:07:49.716Z        INFO    Trivy skips scanning programming language libraries because no supported file was detected

secureimages/filebeat:7.11.1-alpine-3.13.2 (alpine 3.13.2)
==========================================================
Total: 0 (UNKNOWN: 0, LOW: 0, MEDIUM: 0, HIGH: 0, CRITICAL: 0)
```

## Official Docker image (~464MB)

[https://www.docker.elastic.co/](https://www.docker.elastic.co/)
```
docker pull docker.elastic.co/beats/filebeat:7.11.1
```

Security scanning using Clair
```
clair-scanner docker.elastic.co/beats/filebeat:7.11.1
2021/02/20 14:07:54 [INFO] ▶ Start clair-scanner
2021/02/20 14:08:01 [INFO] ▶ Server listening on port 9279
2021/02/20 14:08:01 [INFO] ▶ Analyzing 291eb894538de0baee3beecbbb57ef8668b00974b05062ff0d78c0dc110820ac
2021/02/20 14:08:01 [INFO] ▶ Analyzing d9b504b12382781d4843f5c883a298cc101ef3bf4a6423078f6087870d0ad97d
2021/02/20 14:08:01 [INFO] ▶ Analyzing 4f5ea70d4e27565ad580bd3f8b23497b85472dd219b4efc3fce224c03f1d2e19
2021/02/20 14:08:01 [INFO] ▶ Analyzing e02bd4e87f7068e2be7d5dc7ca0d0d92894d373dbf498c394ef3fdc650deee8f
2021/02/20 14:08:01 [INFO] ▶ Analyzing 151ed2407ec62a9806beacb554b0988e2528ad23cbe4682782e7a568c32331b9
2021/02/20 14:08:01 [INFO] ▶ Analyzing ad9e9b9d1ac23e712513c75a2f4539d7093f354f58658e614b91f18e5a9ea76a
2021/02/20 14:08:01 [INFO] ▶ Analyzing 75e6b2ba556fc8efc354c2271fbb2178f0c7fe4552841e35bc4174d34abf999f
2021/02/20 14:08:01 [INFO] ▶ Analyzing aefa17bf7efc1c99711eb7dadadee52218613d1e7a8442c9c6f6ce1b69ad50b0
2021/02/20 14:08:01 [INFO] ▶ Analyzing 1e1c74f0882de87659f3477eb5b429e296c2c6bea7ef9c00b2f60a9ea86c6458
2021/02/20 14:08:01 [INFO] ▶ Analyzing ed391717e18c80e07213eaa13dd3ea493e6c13248024c6f612620cec3c658f7c
2021/02/20 14:08:01 [INFO] ▶ Analyzing 19fc046ca80c94fe8eccf27f2400c97862ffb8de6657778e5cee8e440ef051eb
2021/02/20 14:08:01 [INFO] ▶ Image [docker.elastic.co/beats/filebeat:7.11.1] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.16.0 --no-progress docker.elastic.co/beats/filebeat:7.11.1
2021-02-20T14:08:02.983Z        INFO    Need to update DB
2021-02-20T14:08:02.983Z        INFO    Downloading DB...
2021-02-20T14:08:12.834Z        INFO    Detecting RHEL/CentOS vulnerabilities...
2021-02-20T14:08:12.842Z        INFO    Trivy skips scanning programming language libraries because no supported file was detected

docker.elastic.co/beats/filebeat:7.11.1 (centos 7.9.2009)
=========================================================
Total: 596 (UNKNOWN: 0, LOW: 357, MEDIUM: 235, HIGH: 4, CRITICAL: 0)
```
