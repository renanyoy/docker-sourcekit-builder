# `docker-sourcekit-builder` builds Swift Toolchain for ubuntu 14.04 with `libsourcekitdInProc.so`

## Build `sourcekit-builder` image
```console
docker build -t sourcekit-builder:30p4 https://github.com/norio-nomura/docker-sourcekit-builder.git
```

## Build `sourcekit` image using context created by `sourcekit-builder`
```console
docker run --rm sourcekit-builder:30p4 context | docker build -t norionomura/sourcekit:30p4 -
```

## Extract Installer Package from `sourcekit-builder`
```console
docker run --rm sourcekit-builder:30p4 context|tar xv - "*.tar.gz"
x ./swift-3.0-PREVIEW-4-<hash of commit in swift-dev>-with-sourcekit.tar.gz
```
