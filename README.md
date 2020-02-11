# Filebeat

Filebeat, image is based on the Alpine base image with 0 vulnerabilities.

## Current Docker image

Security scanning using Clair
```
clair-scanner secureimages/filebeat:7.6.0-alpine-3.11.3
2020/02/11 20:43:45 [INFO] ▶ Start clair-scanner
2020/02/11 20:43:46 [INFO] ▶ Server listening on port 9279
2020/02/11 20:43:46 [INFO] ▶ Analyzing c60e0e5e0b8cce2c353f5af4186afb2cde56680bc78ff165fd2368a003530178
2020/02/11 20:43:46 [INFO] ▶ Analyzing 98152958745799e48c65c74561564b63a262ffdf13e510733bec1f0010d8d1fe
2020/02/11 20:43:46 [INFO] ▶ Analyzing 5c2d8d5b8676e57747f7f81352056818f8ddc51486874619ba2adad43066a2ad
2020/02/11 20:43:46 [INFO] ▶ Analyzing 8449c5ae1228479dfee65007f82c1f6725b13ec761c6811b940c9d9aecc138d2
2020/02/11 20:43:46 [INFO] ▶ Image [secureimages/filebeat:7.6.0-alpine-3.11.3] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.4.3 --no-progress secureimages/filebeat:7.6.0-alpine-3.11.3
2020-02-11T18:43:53.072Z        INFO    Need to update DB
2020-02-11T18:43:53.072Z        INFO    Downloading DB...
2020-02-11T18:43:57.065Z        INFO    Reopening DB...
2020-02-11T18:44:00.406Z        INFO    Detecting Alpine vulnerabilities...

secureimages/filebeat:7.6.0-alpine-3.11.3 (alpine 3.11.3)
=========================================================
Total: 0 (UNKNOWN: 0, LOW: 0, MEDIUM: 0, HIGH: 0, CRITICAL: 0)
```

## Official Docker image

[https://www.docker.elastic.co/](https://www.docker.elastic.co/)
```
docker pull docker.elastic.co/beats/filebeat:7.6.0
```

Security scanning using Clair
```
clair-scanner docker.elastic.co/beats/filebeat:7.6.0
2020/02/11 20:44:05 [INFO] ▶ Start clair-scanner
2020/02/11 20:44:11 [INFO] ▶ Server listening on port 9279
2020/02/11 20:44:11 [INFO] ▶ Analyzing efabb8e7a64ff0670af40775b5aa02a8e19f73baa9f9e24aef8ce37a563f632d
2020/02/11 20:44:11 [INFO] ▶ Analyzing 156447c385d9ccdcbd5bc8747205808f0dff413e8617c8c3f420d52af08bf9e3
2020/02/11 20:44:11 [INFO] ▶ Analyzing d0d23ce68c53da2203d6cd7f24d78ae849ebf6ccbc6ba3c16da5a270b2e4291d
2020/02/11 20:44:11 [INFO] ▶ Analyzing 21d601a8a892ebbeec9f918ba03792664fd601a2fa337f557bfba2c7620b0616
2020/02/11 20:44:11 [INFO] ▶ Analyzing b2850ad1df76fd27808cfc9abd0c2ab2020d0d017c34c03a4d457cb63746b22e
2020/02/11 20:44:11 [INFO] ▶ Analyzing b58c612d37c47cfdb0da8a5573343347a94efc81d76820b0fa9c7924b3da6ed7
2020/02/11 20:44:11 [INFO] ▶ Analyzing 6bd9aff2e5942fd3086366ff683856e03be762c531941e27c657ce8397eab4c5
2020/02/11 20:44:11 [WARN] ▶ Image [docker.elastic.co/beats/filebeat:7.6.0] contains 7 total vulnerabilities
2020/02/11 20:44:11 [ERRO] ▶ Image [docker.elastic.co/beats/filebeat:7.6.0] contains 7 unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.4.3 --no-progress docker.elastic.co/beats/filebeat:7.6.0
2020-02-11T18:44:13.498Z        INFO    Need to update DB
2020-02-11T18:44:13.498Z        INFO    Downloading DB...
2020-02-11T18:44:17.496Z        INFO    Reopening DB...
2020-02-11T18:44:23.424Z        INFO    Detecting RHEL/CentOS vulnerabilities...

docker.elastic.co/beats/filebeat:7.6.0 (centos 7.7.1908)
========================================================
Total: 626 (UNKNOWN: 0, LOW: 59, MEDIUM: 461, HIGH: 103, CRITICAL: 3)
```
