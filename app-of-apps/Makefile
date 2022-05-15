upgrade-local:
	helm upgrade -i -n argocd -f values-local.yaml app-of-apps .

upgrade-eks:
	helm upgrade -i -n argocd -f values-eks.yaml app-of-apps .

delete:
	helm delete -n argocd app-of-apps

template-local:
	helm template -f values-local.yaml app-of-apps .

template-eks:
	helm template -f values-eks.yaml app-of-apps .