# Filebeat

Filebeat, image is based on the Alpine base image with 0 vulnerabilities.

## Current Docker image (~89.1MB)

Security scanning using Clair
```
clair-scanner secureimages/filebeat:7.6.2-alpine-3.11.6
2020/04/25 12:25:11 [INFO] ▶ Start clair-scanner
2020/04/25 12:25:12 [INFO] ▶ Server listening on port 9279
2020/04/25 12:25:12 [INFO] ▶ Analyzing a5304328ea0f44bd1ac8bb5416ad6b7cc3b747ac232c6af66d7d9f12e9854344
2020/04/25 12:25:12 [INFO] ▶ Analyzing 361b7ced52eb24355ccd8390cbab87f78b73dbae9fcdaf2e9872340228060727
2020/04/25 12:25:12 [INFO] ▶ Analyzing 060220809583296228af99342caf9660b809b67644ee9d334f35f8f782070614
2020/04/25 12:25:12 [INFO] ▶ Analyzing a164bf8ffeb111b3c7e62506a7d379b0965ea13e4744dfda3223f3546285607f
2020/04/25 12:25:12 [INFO] ▶ Image [secureimages/filebeat:7.6.2-alpine-3.11.6] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.6.0 --no-progress secureimages/filebeat:7.6.2-alpine-3.11.6
2020-04-25T09:25:18.782Z        INFO    Need to update DB
2020-04-25T09:25:18.782Z        INFO    Downloading DB...
2020-04-25T09:25:24.412Z        INFO    Detecting Alpine vulnerabilities...

secureimages/filebeat:7.6.2-alpine-3.11.6 (alpine 3.11.6)
=========================================================
Total: 0 (UNKNOWN: 0, LOW: 0, MEDIUM: 0, HIGH: 0, CRITICAL: 0)
```

## Official Docker image (~364MB)

[https://www.docker.elastic.co/](https://www.docker.elastic.co/)
```
docker pull docker.elastic.co/beats/filebeat:7.6.2
```

Security scanning using Clair
```
clair-scanner docker.elastic.co/beats/filebeat:7.6.2
2020/04/25 12:25:39 [INFO] ▶ Start clair-scanner
2020/04/25 12:25:45 [INFO] ▶ Server listening on port 9279
2020/04/25 12:25:45 [INFO] ▶ Analyzing efabb8e7a64ff0670af40775b5aa02a8e19f73baa9f9e24aef8ce37a563f632d
2020/04/25 12:25:45 [INFO] ▶ Analyzing bb63212aca9342a902d10f609ba1f4ce40d385c1554078bc54071ba27d383360
2020/04/25 12:25:45 [INFO] ▶ Analyzing aa7dc99135a9b21504837fef219cee447efbc9f2a81db10c8086d21bc90e9d31
2020/04/25 12:25:45 [INFO] ▶ Analyzing 2d6dc39f2239e0ac7041d822167f8da7a82fbfc6e09f327aedae7add0cc7d105
2020/04/25 12:25:45 [INFO] ▶ Analyzing ca134feed31354a762feb1e11b8d561220931fd140ea3b67c51715d532e9f3d6
2020/04/25 12:25:45 [INFO] ▶ Analyzing 3edbef2095c1512b77230615efb105d301c3864da8e823d45e821d064acee707
2020/04/25 12:25:45 [INFO] ▶ Analyzing ad3bda3a3516a18caebaa311c6deb1788d7ace6a505af562bf6e1f71a045212f
2020/04/25 12:25:45 [WARN] ▶ Image [docker.elastic.co/beats/filebeat:7.6.2] contains 18 total vulnerabilities
2020/04/25 12:25:45 [ERRO] ▶ Image [docker.elastic.co/beats/filebeat:7.6.2] contains 18 unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.6.0 --no-progress docker.elastic.co/beats/filebeat:7.6.2
2020-04-25T09:25:49.679Z        INFO    Need to update DB
2020-04-25T09:25:49.679Z        INFO    Downloading DB...
2020-04-25T09:25:59.555Z        INFO    Detecting RHEL/CentOS vulnerabilities...

docker.elastic.co/beats/filebeat:7.6.2 (centos 7.7.1908)
========================================================
Total: 638 (UNKNOWN: 0, LOW: 62, MEDIUM: 467, HIGH: 106, CRITICAL: 3)
```
