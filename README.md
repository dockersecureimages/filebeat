# Filebeat

Filebeat, image is based on the Alpine base image with 0 vulnerabilities.

## Current Docker image (~99.1MB)

Security scanning using Clair
```
clair-scanner secureimages/filebeat:7.7.0-alpine-3.11.6
2020/05/14 12:01:42 [INFO] ▶ Start clair-scanner
2020/05/14 12:01:43 [INFO] ▶ Server listening on port 9279
2020/05/14 12:01:43 [INFO] ▶ Analyzing a5304328ea0f44bd1ac8bb5416ad6b7cc3b747ac232c6af66d7d9f12e9854344
2020/05/14 12:01:43 [INFO] ▶ Analyzing 540a17242364c451525198cbf4897b8f4776ff8564c5e8831d89454995ce830c
2020/05/14 12:01:43 [INFO] ▶ Analyzing 49db92f0f436f46b8f8b05ced7602b652c039f4ac5e633ba02e7115464b5c639
2020/05/14 12:01:43 [INFO] ▶ Analyzing 3bc6bde56d50b95b470bde74b8b953901307f52a73c397e92065fc66775a666c
2020/05/14 12:01:43 [INFO] ▶ Image [secureimages/filebeat:7.7.0-alpine-3.11.6] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.7.0 --no-progress secureimages/filebeat:7.7.0-alpine-3.11.6
2020-05-14T09:01:50.934Z        INFO    Need to update DB
2020-05-14T09:01:50.934Z        INFO    Downloading DB...
2020-05-14T09:01:56.433Z        INFO    Detecting Alpine vulnerabilities...

secureimages/filebeat:7.7.0-alpine-3.11.6 (alpine 3.11.6)
=========================================================
Total: 0 (UNKNOWN: 0, LOW: 0, MEDIUM: 0, HIGH: 0, CRITICAL: 0)
```

## Official Docker image (~408MB)

[https://www.docker.elastic.co/](https://www.docker.elastic.co/)
```
docker pull docker.elastic.co/beats/filebeat:7.7.0
```

Security scanning using Clair
```
clair-scanner docker.elastic.co/beats/filebeat:7.7.0
2020/05/14 12:02:01 [INFO] ▶ Start clair-scanner
2020/05/14 12:02:07 [INFO] ▶ Server listening on port 9279
2020/05/14 12:02:07 [INFO] ▶ Analyzing c53e4ebe5d0a558645655ec8b3e667ed7cae98e3252a08914c1ab5a08cef4da0
2020/05/14 12:02:07 [INFO] ▶ Analyzing 7ee8489d6b75b80f4437379dd7311da314dd7b6228d1fda662e434ec4df65ad7
2020/05/14 12:02:08 [INFO] ▶ Analyzing b244c28fb4aa256abae070a83350b0540412e6bd8e65c2ce8b21f0fd23eefb50
2020/05/14 12:02:08 [INFO] ▶ Analyzing 38cb7366c61ab68fda022d02d0273b37d3c5489502d9928355d0d61608168dd2
2020/05/14 12:02:08 [INFO] ▶ Analyzing b5221612681c51ce98332c6cd5be065c8b1a7bec13274da204ae9f3ba8bb04f3
2020/05/14 12:02:08 [INFO] ▶ Analyzing 4ede8c62bb6309fdeaa10130fe2431869bbcabb024ca69b30e4b38a1ee945ed0
2020/05/14 12:02:08 [INFO] ▶ Analyzing 4365ca9972c295dc3a5141a798a6abd27aeb9d056b91f91f2297564d156ff943
2020/05/14 12:02:08 [INFO] ▶ Analyzing 6092af5db3113fd0f36ebdc52c4f5df7aa52ba2f0c9169590be28cbda68464b0
2020/05/14 12:02:08 [INFO] ▶ Image [docker.elastic.co/beats/filebeat:7.7.0] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.7.0 --no-progress docker.elastic.co/beats/filebeat:7.7.0
2020-05-14T09:02:11.759Z        INFO    Need to update DB
2020-05-14T09:02:11.759Z        INFO    Downloading DB...
2020-05-14T09:02:22.625Z        INFO    Detecting RHEL/CentOS vulnerabilities...

docker.elastic.co/beats/filebeat:7.7.0 (centos 7.8.2003)
========================================================
Total: 600 (UNKNOWN: 0, LOW: 361, MEDIUM: 234, HIGH: 5, CRITICAL: 0)
```
