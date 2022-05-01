# k8-cicd-argocd

### ArgoCD
![Untitled](https://user-images.githubusercontent.com/77256060/166134042-5d874abd-8279-475d-9045-72d4747f36a8.png)
### ArgoCD 설치
- git clone [https://github.com/DACHANCHOI/k8-cicd-argocd.git](https://github.com/DACHANCHOI/k8-cicd-argocd.git)
- cd k8-cicd-argocd/argo-cd
- make template-local
- make upgrade-local
### ArgoCD Project 배포
- kubectl apply -f AppProject.yaml
![image](https://user-images.githubusercontent.com/77256060/166134060-689d1a99-2d5f-4635-8240-f5b769272422.png)
### ArgoCD Application 배포
1. yaml파일로 배포
    1. kubectl apply -f Application.yaml
![Untitled 3](https://user-images.githubusercontent.com/77256060/166134034-145030bf-8fc0-457c-a0f0-40a92ecfd0bb.png)
