.PHONY: local mount create delete
REPO=flow-3
TIMESTAMP=tmp-$(shell date +%s )

local:
	@eval $$(minikube docker-env) ;\
	docker image build -t $(REPO):$(TIMESTAMP) -f Dockerfile .
	kubectl set image -f kubernetes/deploy/deployment.yaml flow-3=$(REPO):$(TIMESTAMP)

create:
	@eval $$(minikube docker-env) ;\
	docker image build -t $(REPO):create -f Dockerfile .
	kubectl create -f kubernetes/deploy/

delete:
	kubectl delete -f kubernetes/deploy/

mount:
	@echo "Setting up mount as symlink in /Users/.minikube-mounts folder"
	$(shell sudo mkdir /Users/.minikube-mounts)
	$(shell sudo ln -s ${PWD}/website/ /Users/.minikube-mounts/flow-3)
	@echo $(shell ls /Users/.minikube-mounts)
