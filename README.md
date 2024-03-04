# pash (aka python-bash)

Chatbot-style graphical interface written in Python/Streamlit that allows execution of (some) bash commands in the container.

The multi-architecture build supports the following platforms:

- `amd64`
- `arm64`
- `ppc64le`

The manifest is uploaded here: `quay.io/jpetnik/pash:v1`

## Run a container

```bash
podman run -d --rm -p 8501:8501 quay.io/jpetnik/pash:v1
```

## Deploy into a Red Hat OpenShift Cluster

Kustomize is used to change the configuration for different environments:

```bash
# replicas: 1; annotation env: dev
oc apply -k deploy/overlays/dev

# replicas: 2; annotation env: test
oc apply -k deploy/overlays/test

# replicas: 3; annotation env: prod
oc apply -k deploy/overlays/prod
```
