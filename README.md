# gitops-cicd

## Deploy keys

1. Go to https://github.com/fhopfensperger/gitops-cicd/settings/keys/new

2. Create a new ssh key
```bash
$ ssh-keygen -t rsa -b 4096 -C "tekton-argo@fhopfensperger-github-com" -f tekton-argo-fhopfensperger-github-com
-> No passphrase
```

3. Copy ssh key to your clipboard
```bash
pbcopy < tekton-argo-fhopfensperger-github-com.pub
```

4. Add pub key to your new deploy key and check "Allow write access"

## Install sealed secrets

1. Install latest version
```bash
$ kubectl apply -f https://github.com/bitnami-labs/sealed-secrets/releases/download/v0.12.6/controller.yaml
```

2. Wait until pods are running
```bash
$ kubectl get po -n kube-system
```

## Create a docker acces token

1. Go to your container repo: https://hub.docker.com/settings/security

2. Create a access token
