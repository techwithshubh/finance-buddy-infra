# Finance Buddy Application Infra Configuration

1. This repo contains finance buddy k8s configurations.
2. These configurations are used by ArgoCD for deployment.
3. Each deployment file maintains the version of image that is changed when Github Actions pipeline executes in parent repo.
4. This repo uses [ArgoCD Tutorial](https://www.youtube.com/watch?v=MeU5_k9ssrs) as reference.

# How

Ref: [Kustomize](https://kubectl.docs.kubernetes.io/installation/kustomize/homebrew/)

1. Github Actions uses Kustomize `brew install kustomize` to update the version of docker image

```
kustomize build dev/ | kubectl apply -f -
kustomize edit set image FINANCE_BUDDY_UI_IMAGE=techwithshubh/finance-ui:0.0.2
```