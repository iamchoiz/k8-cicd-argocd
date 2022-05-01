# k8-cicd-argocd

### ArgoCD

![Untitled](k8-cicd-argocd%2048326e5e23074ce6ac400f237e34b5a8/Untitled.png)

### ArgoCD 설치

- git clone [https://github.com/DACHANCHOI/k8-cicd-argocd.git](https://github.com/DACHANCHOI/k8-cicd-argocd.git)
- cd k8-cicd-argocd/argo-cd
- make template-local
- make upgrade-local

### ArgoCD Project 배포

![Untitled](k8-cicd-argocd%2048326e5e23074ce6ac400f237e34b5a8/Untitled%201.png)

- kubectl apply -f AppProject.yaml

![Untitled](k8-cicd-argocd%2048326e5e23074ce6ac400f237e34b5a8/Untitled%202.png)

### ArgoCD Application 배포

1. yaml파일로 배포
    1. kubectl apply -f Application.yaml

![Untitled](k8-cicd-argocd%2048326e5e23074ce6ac400f237e34b5a8/Untitled%203.png)