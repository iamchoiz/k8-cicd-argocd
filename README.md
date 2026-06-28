# k8-cicd-argocd

> Kubernetes(EKS) 환경에서 **ArgoCD**를 이용한 GitOps 기반 CD 파이프라인 구성 프로젝트  
> App of Apps 패턴, Helm 기반 배포, AWS Load Balancer Controller 설치를 포함합니다.

## ArgoCD Overview

![ArgoCD Overview](https://user-images.githubusercontent.com/77256060/166134042-5d874abd-8279-475d-9045-72d4747f36a8.png)

---

## Tech Stack

| Category | Tool |
|---|---|
| CD | ArgoCD |
| Container Orchestration | Kubernetes (EKS) |
| App Packaging | Helm |
| Ingress | AWS Load Balancer Controller |
| Declarative Setup | App of Apps 패턴 |

---

## 디렉토리 구조

```
.
├── argo-cd/                        # ArgoCD Helm Chart (설치용)
├── argo-declarartive-setup-yaml/   # ArgoCD AppProject, Application YAML
├── app-of-apps/                    # App of Apps 루트 애플리케이션
├── aws-load-balancer-controller/   # AWS ALB Ingress Controller Helm Chart
├── demo/                           # Nginx 기반 데모 앱
├── demo_app/                       # Tomcat 기반 데모 앱
├── kustomize_app/                  # Kustomize 배포 예시
├── sample-helm-1/                  # Helm 차트 샘플 1
└── sample-helm-2/                  # Helm 차트 샘플 2
```

---

## 1. ArgoCD 설치

```bash
git clone https://github.com/DACHANCHOI/k8-cicd-argocd.git
cd k8-cicd-argocd/argo-cd

# Local 환경 (minikube 등)
make template-local
make upgrade-local

# EKS 환경
make upgrade-eks
```

---

## 2. ArgoCD Project 배포

ArgoCD Project는 애플리케이션의 소스/목적지 클러스터를 제한하는 논리적 그룹입니다.

```bash
kubectl apply -f argo-declarartive-setup-yaml/AppProject.yaml
```

![ArgoCD Project](https://user-images.githubusercontent.com/77256060/166134060-689d1a99-2d5f-4635-8240-f5b769272422.png)

---

## 3. ArgoCD Application 배포

ArgoCD Application을 선언형 YAML로 배포합니다.

```bash
kubectl apply -f argo-declarartive-setup-yaml/Application.yaml
```

![ArgoCD Application](https://user-images.githubusercontent.com/77256060/166134034-145030bf-8fc0-457c-a0f0-40a92ecfd0bb.png)

---

## 4. AWS Load Balancer Controller 설치 (EKS)

EKS Ingress에 AWS ALB를 사용하기 위한 컨트롤러를 Helm으로 설치합니다.

```bash
cd aws-load-balancer-controller

# values-eks.yaml에서 clusterName 수정 후
make upgrade-eks
```

> EKS 클러스터 생성은 [terraform-eks](https://github.com/DACHANCHOI/terraform-eks) 레포를 참고하세요.
