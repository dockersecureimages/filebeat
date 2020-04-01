# Filebeat

Filebeat, image is based on the Alpine base image with 0 vulnerabilities.

## Current Docker image

Security scanning using Clair
```
clair-scanner secureimages/filebeat:7.6.2-alpine-3.11.5
2020/04/01 15:53:11 [INFO] ▶ Start clair-scanner
2020/04/01 15:53:11 [INFO] ▶ Server listening on port 9279
2020/04/01 15:53:11 [INFO] ▶ Analyzing dac63304c60354902922613d675ec533c6e10879f72d49b7602575ae5d5f9257
2020/04/01 15:53:11 [INFO] ▶ Analyzing 3509c840171f10fb79f120c6120ab7622f80af864bb0a0000d1e8cffcb1716a0
2020/04/01 15:53:12 [INFO] ▶ Analyzing c55e764811a47aabc6516eff0e31b0b98296184c20987105c32d6eb8e4dae03d
2020/04/01 15:53:12 [INFO] ▶ Analyzing cde7261a555f76a94a672dc2ded2fd88226c0a25a836f3726b577b40339b947f
2020/04/01 15:53:12 [INFO] ▶ Image [secureimages/filebeat:7.6.2-alpine-3.11.5] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.5.3 --no-progress secureimages/filebeat:7.6.2-alpine-3.11.5
2020-04-01T12:53:17.789Z        INFO    Need to update DB
2020-04-01T12:53:17.789Z        INFO    Downloading DB...
2020-04-01T12:53:25.935Z        INFO    Reopening DB...
2020-04-01T12:53:27.993Z        INFO    Detecting Alpine vulnerabilities...

secureimages/filebeat:7.6.2-alpine-3.11.5 (alpine 3.11.5)
=========================================================
Total: 0 (UNKNOWN: 0, LOW: 0, MEDIUM: 0, HIGH: 0, CRITICAL: 0)
```

## Official Docker image

[https://www.docker.elastic.co/](https://www.docker.elastic.co/)
```
docker pull docker.elastic.co/beats/filebeat:7.6.2
```

Security scanning using Clair
```
clair-scanner docker.elastic.co/beats/filebeat:7.6.2
2020/04/01 15:53:32 [INFO] ▶ Start clair-scanner
2020/04/01 15:53:38 [INFO] ▶ Server listening on port 9279
2020/04/01 15:53:38 [INFO] ▶ Analyzing efabb8e7a64ff0670af40775b5aa02a8e19f73baa9f9e24aef8ce37a563f632d
2020/04/01 15:53:38 [INFO] ▶ Analyzing bb63212aca9342a902d10f609ba1f4ce40d385c1554078bc54071ba27d383360
2020/04/01 15:53:38 [INFO] ▶ Analyzing aa7dc99135a9b21504837fef219cee447efbc9f2a81db10c8086d21bc90e9d31
2020/04/01 15:53:38 [INFO] ▶ Analyzing 2d6dc39f2239e0ac7041d822167f8da7a82fbfc6e09f327aedae7add0cc7d105
2020/04/01 15:53:38 [INFO] ▶ Analyzing ca134feed31354a762feb1e11b8d561220931fd140ea3b67c51715d532e9f3d6
2020/04/01 15:53:38 [INFO] ▶ Analyzing 3edbef2095c1512b77230615efb105d301c3864da8e823d45e821d064acee707
2020/04/01 15:53:38 [INFO] ▶ Analyzing ad3bda3a3516a18caebaa311c6deb1788d7ace6a505af562bf6e1f71a045212f
2020/04/01 15:53:38 [WARN] ▶ Image [docker.elastic.co/beats/filebeat:7.6.2] contains 18 total vulnerabilities
2020/04/01 15:53:38 [ERRO] ▶ Image [docker.elastic.co/beats/filebeat:7.6.2] contains 18 unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.5.3 --no-progress docker.elastic.co/beats/filebeat:7.6.2
2020-04-01T12:53:40.715Z        INFO    Need to update DB
2020-04-01T12:53:40.715Z        INFO    Downloading DB...
2020-04-01T12:53:48.193Z        INFO    Reopening DB...
2020-04-01T12:53:55.641Z        INFO    Detecting RHEL/CentOS vulnerabilities...

docker.elastic.co/beats/filebeat:7.6.2 (centos 7.7.1908)
========================================================
Total: 640 (UNKNOWN: 0, LOW: 64, MEDIUM: 467, HIGH: 106, CRITICAL: 3)
```
