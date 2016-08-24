# Kubectl as a snap

This is a snapcraft build definition that will allow anyone with a precompiled
kubectl binary to package it up as a snap.  The snapcraft.yaml is the build
directive that defines the confinement, build operations (at this time a simple
copy operation), and additional meta about the package.

## To Build

We piloted this using the snapbox:onbuild docker image. And we make the
assumption you have a `kubectl` binary for your associated arch present in
`$PWD` with the `snapcraft.yaml`

```
docker run --rm -v $PWD:/snap jujusolutions/snapbox:onbuild
```

Once complete, the container will self-destruct leaving behind your snap ready
to be side-loaded into any snapd enabled distribution.

## Installation

```
sudo snap install ./kubectl_#_arch.snap
```

