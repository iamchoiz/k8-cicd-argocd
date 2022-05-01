# k8-cicd-argocd

### ArgoCD

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/7d5c8ad5-75dd-49df-a26a-c803425a6f5d/Untitled.png)
### ArgoCD 설치

- git clone [https://github.com/DACHANCHOI/k8-cicd-argocd.git](https://github.com/DACHANCHOI/k8-cicd-argocd.git)
- cd k8-cicd-argocd/argo-cd
- make template-local
- make upgrade-local

### ArgoCD Project 배포

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c1a9f695-b658-4d34-bfa8-f98fcefba260/Untitled.png)
- kubectl apply -f AppProject.yaml

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/65a4c52d-edcd-47c1-8281-6db7d65b51b4/Untitled.png)
### ArgoCD Application 배포

1. yaml파일로 배포
    1. kubectl apply -f Application.yaml

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/dea47da5-b5a5-4873-90fe-2ad75e0ac173/Untitled.png)
