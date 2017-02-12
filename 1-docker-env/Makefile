.PHONY: local
REPO=flow-1
TIMESTAMP=tmp-$(shell date +%s )

local:
	@eval $$(minikube docker-env) ;\
	docker image build -t $(REPO):$(TIMESTAMP) -f Dockerfile .
	kubectl set image deployment $(REPO) *=$(REPO):$(TIMESTAMP)
