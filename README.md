# Filebeat

Filebeat, image is based on the Alpine base image with 0 vulnerabilities.

## Current Docker image

Security scanning using Clair
```
clair-scanner secureimages/filebeat:7.5.2-alpine-3.11.3
2020/01/27 11:17:40 [INFO] ▶ Start clair-scanner
2020/01/27 11:17:41 [INFO] ▶ Server listening on port 9279
2020/01/27 11:17:41 [INFO] ▶ Analyzing c60e0e5e0b8cce2c353f5af4186afb2cde56680bc78ff165fd2368a003530178
2020/01/27 11:17:41 [INFO] ▶ Analyzing 9c987d60a25690394afd21d0040ea358de354f9e6d85f64fc567b4401095ba6f
2020/01/27 11:17:41 [INFO] ▶ Analyzing bfa5b4811a0091414bc5d325ed5d9fb9d04afbfd4a916386c9d251bec82fc3cb
2020/01/27 11:17:41 [INFO] ▶ Analyzing 1599adc1f46d9f5a5c602828ab07100a4f37e0edf58c42ccc95ad1cfa9fafdf5
2020/01/27 11:17:41 [INFO] ▶ Image [secureimages/filebeat:7.5.2-alpine-3.11.3] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.4.3 --no-progress secureimages/filebeat:7.5.2-alpine-3.11.3
2020-01-27T09:17:48.046Z        INFO    Need to update DB
2020-01-27T09:17:48.046Z        INFO    Downloading DB...
2020-01-27T09:17:51.712Z        INFO    Reopening DB...
2020-01-27T09:17:53.508Z        INFO    Detecting Alpine vulnerabilities...

secureimages/filebeat:7.5.2-alpine-3.11.3 (alpine 3.11.3)
=========================================================
Total: 0 (UNKNOWN: 0, LOW: 0, MEDIUM: 0, HIGH: 0, CRITICAL: 0)
```

## Official Docker image

[https://www.docker.elastic.co/](https://www.docker.elastic.co/)
```
docker pull docker.elastic.co/beats/filebeat:7.5.2
```

Security scanning using Clair
```
clair-scanner docker.elastic.co/beats/filebeat:7.5.2
2020/01/27 11:17:58 [INFO] ▶ Start clair-scanner
2020/01/27 11:18:03 [INFO] ▶ Server listening on port 9279
2020/01/27 11:18:03 [INFO] ▶ Analyzing efabb8e7a64ff0670af40775b5aa02a8e19f73baa9f9e24aef8ce37a563f632d
2020/01/27 11:18:03 [INFO] ▶ Analyzing 8706db73e5428abc28e1d1be7b3d8c13b7e39f0a6580b9fab82728b15984c6f4
2020/01/27 11:18:03 [INFO] ▶ Analyzing 4bd4f666bcb3e27d9db725d34cf9c2d234977d55693f277d0c6e50cd1f5712f7
2020/01/27 11:18:03 [INFO] ▶ Analyzing 29cb5a5679845065da60b6ed2de08ae2d22212345c44edd44fa1cab6a6d98ed8
2020/01/27 11:18:03 [INFO] ▶ Analyzing e9946cf44d321eab63d40c7ae01b1f62cb722dee4e475cb2ef05f035ed50a4b7
2020/01/27 11:18:03 [INFO] ▶ Analyzing 05f1f1e88d7ad4fa75dcc1d748ef4f79d83c696c335996050a308f3698cb082c
2020/01/27 11:18:03 [INFO] ▶ Analyzing d1aee9216638173973ffa854272506ff5afb3a72a49c9a3f185b8b12a6048a31
2020/01/27 11:18:03 [WARN] ▶ Image [docker.elastic.co/beats/filebeat:7.5.2] contains 6 total vulnerabilities
2020/01/27 11:18:03 [ERRO] ▶ Image [docker.elastic.co/beats/filebeat:7.5.2] contains 6 unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.4.3 --no-progress docker.elastic.co/beats/filebeat:7.5.2
2020-01-27T09:18:07.243Z        INFO    Need to update DB
2020-01-27T09:18:07.243Z        INFO    Downloading DB...
2020-01-27T09:18:11.484Z        INFO    Reopening DB...
2020-01-27T09:18:17.264Z        INFO    Detecting RHEL/CentOS vulnerabilities...

docker.elastic.co/beats/filebeat:7.5.2 (centos 7.7.1908)
========================================================
Total: 637 (UNKNOWN: 0, LOW: 61, MEDIUM: 468, HIGH: 103, CRITICAL: 5)
```
