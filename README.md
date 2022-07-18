# Operate First toolbox

This is an Operate-First toolbox that comprises of the commonly used tooling to supplement workflows.

## Usage

### Create your toolbox container

```shell
$ toolbox create --image quay.io/operate-first/opf-toolbox:v0.9.0
Created container: opf-toolbox
Enter with: toolbox enter --container opf-toolbox-v0.9.0
```

This will create a container called `opf-toolbox-<version-id>`.

### Enter the toolbox

```shell
$ toolbox enter --container opf-toolbox-v0.9.0
```

### Tools included

- Kustomize
- SOPS
- KSOPS
- Helm
- Helm Secrets
- Hash Annotator
- Conftest
- YQ
- Make
- NPM and nodejs
- Prow's label_sync and peribolos
- pre-commit
- opfcli
- Kubeval
- kubectl
- OpenShift CLI (oc)
- Vault CLI

### Debugging Tips

You may see the following error when running a `kustomize build` using `ksops`:

> plugin was built with a different version of package internal/cpu

Toolbox will try to absorb as much from your parent environment as possible, this may result in environment variables
in the toolbox being overwritten by your own environment. Try sourcing these environment variables again to fix the issue
above:

```bash
XDG_DATA_HOME=/usr/share/.local/share
XDG_CACHE_HOME=/usr/share/.cache
XDG_CONFIG_HOME=/usr/share/.config
```

## Background Information

See [toolbox](https://github.com/containers/toolbox) for more info on how a toolbox works.
