# goharbor-arm
ARM64 images for Harbor registry

## Usage

- pull images
```
for i in goharbor/harbor-core:v2.5.0 goharbor/harbor-jobservice:v2.5.0 goharbor/notary-signer-photon:v2.5.0 goharbor/harbor-db:v2.5.0 goharbor/harbor-registryctl:v2.5.0 goharbor/redis-photon:v2.5.0 goharbor/harbor-portal:v2.5.0 goharbor/trivy-adapter-photon:v2.5.0 goharbor/nginx-photon:v2.5.0 goharbor/registry-photon:v2.5.0 goharbor/notary-server-photon:v2.5.0 goharbor/chartmuseum-photon:v2.5.0 goharbor/prepare:v2.5.0 goharbor/harbor-log:v2.5.0 goharbor/harbor-exporter:v2.5.0 ; do IMAGE=$(echo ${i##goharbor/} |cut -d: -f1); docker pull  mikrobithu/$IMAGE:dev-arm; docker tag mikrobithu/$IMAGE:dev-arm  goharbor/$IMAGE:v.2.5.0 ; docker tag mikrobithu/$IMAGE:dev-arm  goharbor/$IMAGE:v.dev-arm ; done
```
with podman:
 ```
for i in goharbor/harbor-core:v2.5.0 goharbor/harbor-jobservice:v2.5.0 goharbor/notary-signer-photon:v2.5.0 goharbor/harbor-db:v2.5.0 goharbor/harbor-registryctl:v2.5.0 goharbor/redis-photon:v2.5.0 goharbor/harbor-portal:v2.5.0 goharbor/trivy-adapter-photon:v2.5.0 goharbor/nginx-photon:v2.5.0 goharbor/registry-photon:v2.5.0 goharbor/notary-server-photon:v2.5.0 goharbor/chartmuseum-photon:v2.5.0 goharbor/prepare:v2.5.0 goharbor/harbor-log:v2.5.0 goharbor/harbor-exporter:v2.5.0 ; do IMAGE=$(echo ${i##goharbor/} |cut -d: -f1); podman pull  docker.io/mikrobithu/$IMAGE:dev-arm; podman tag mikrobithu/$IMAGE:dev-arm  goharbor/$IMAGE:v.2.5.0 ; podman tag mikrobithu/$IMAGE:dev-arm  goharbor/$IMAGE:v.dev-arm ; done
```

- download harbor installer (https://github.com/goharbor/harbor/releases/download/v2.5.0/harbor-online-installer-v2.5.0.tgz)
- prepare harbor.yml (https://goharbor.io/docs/2.5.0/install-config/)
- run installer: `install.sh --with-notary --with-trivy --with-chartmuseum`

## Test And Package
### 导出v2.5.0

```
for i in goharbor/harbor-core:v2.5.0 goharbor/harbor-jobservice:v2.5.0 goharbor/notary-signer-photon:v2.5.0 goharbor/harbor-db:v2.5.0 goharbor/harbor-registryctl:v2.5.0 goharbor/redis-photon:v2.5.0 goharbor/harbor-portal:v2.5.0 goharbor/trivy-adapter-photon:v2.5.0 goharbor/nginx-photon:v2.5.0 goharbor/registry-photon:v2.5.0 goharbor/notary-server-photon:v2.5.0 goharbor/chartmuseum-photon:v2.5.0 goharbor/prepare:v2.5.0 goharbor/harbor-log:v2.5.0 goharbor/harbor-exporter:v2.5.0 ; do IMAGE=$(echo ${i##goharbor/} |cut -d: -f1); docker tag mikrobithu/$IMAGE:dev-arm  goharbor/$IMAGE:v2.5.0; done
```

### 导出dev-arm，离线包使用的版本实际为dev-arm
```
for i in goharbor/harbor-core:v2.5.0 goharbor/harbor-jobservice:v2.5.0 goharbor/notary-signer-photon:v2.5.0 goharbor/harbor-db:v2.5.0 goharbor/harbor-registryctl:v2.5.0 goharbor/redis-photon:v2.5.0 goharbor/harbor-portal:v2.5.0 goharbor/trivy-adapter-photon:v2.5.0 goharbor/nginx-photon:v2.5.0 goharbor/registry-photon:v2.5.0 goharbor/notary-server-photon:v2.5.0 goharbor/chartmuseum-photon:v2.5.0 goharbor/prepare:v2.5.0 goharbor/harbor-log:v2.5.0 goharbor/harbor-exporter:v2.5.0 ; do IMAGE=$(echo ${i##goharbor/} |cut -d: -f1); docker tag mikrobithu/$IMAGE:dev-arm  goharbor/$IMAGE:dev-arm; done
```



### 导出digiboy2008，进行归档
```
for i in goharbor/harbor-core:v2.5.0 goharbor/harbor-jobservice:v2.5.0 goharbor/notary-signer-photon:v2.5.0 goharbor/harbor-db:v2.5.0 goharbor/harbor-registryctl:v2.5.0 goharbor/redis-photon:v2.5.0 goharbor/harbor-portal:v2.5.0 goharbor/trivy-adapter-photon:v2.5.0 goharbor/nginx-photon:v2.5.0 goharbor/registry-photon:v2.5.0 goharbor/notary-server-photon:v2.5.0 goharbor/chartmuseum-photon:v2.5.0 goharbor/prepare:v2.5.0 goharbor/harbor-log:v2.5.0 goharbor/harbor-exporter:v2.5.0 ; do IMAGE=$(echo ${i##goharbor/} |cut -d: -f1); docker tag mikrobithu/$IMAGE:dev-arm  digiboy2008/$IMAGE:dev-arm; done
```

## Build (in vagrant)

requirments:
- make
- vagrant
- virtualbox

`make all`
