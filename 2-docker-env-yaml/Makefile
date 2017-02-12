.PHONY: local create delete
REPO=flow-2
TIMESTAMP=tmp-$(shell date +%s )

local:
	@eval $$(minikube docker-env) ;\
	docker image build -t $(REPO):$(TIMESTAMP) -f Dockerfile .
	kubectl set image -f kubernetes/deploy/deployment.yaml flow-2=$(REPO):$(TIMESTAMP)

create:
	@eval $$(minikube docker-env) ;\
	docker image build -t $(REPO):create -f Dockerfile .
	kubectl create -f kubernetes/deploy/

delete:
	kubectl delete -f kubernetes/deploy/
