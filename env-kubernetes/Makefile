include ../Makefile

build: clean
	helm repo add carzone $(CHART_REPO)
	helm repo update

install: clean build
	helm install carzone/$(CHART) --name $(RELEASE) -f ./myvalues.yaml -f ./secrets.yaml --version $(CHART_VERSION) $(ARGS)

upgrade: clean build
	helm upgrade $(RELEASE) jenkins-x/$(CHART) -f myvalues.yaml -f secrets.yaml --version $(CHART_VERSION) $(ARGS)
