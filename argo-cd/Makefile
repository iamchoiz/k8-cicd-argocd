upgrade:
	helm upgrade -i argocd \
	  -n argocd \
	  --create-namespace \
	  -f values.yaml \
	  .

delete:
	helm delete -n argocd argocd

template:
	helm template -n argocd -f values.yaml argocd .
