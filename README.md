# wordpress-mysql-helm-chart

Dependance
use commands

kubectl get nodes
Usage

Clone this git repository

Execute next commands from repository directory
check that all templates are valid

helm template .
install chart

helm install . --generate-name
Check your WordPress service External IP address with next command (may take some time)
kubectl get service -n demo-application
By-default namespace that used in the chart called demo-application. If you changed it, make sure you define the proper namespace in kubectl get command.

Now you can check this IP address with web-browser

Helm Variables

Defined in values.yaml

Name	Default Value	Difinition
namespace	wp-mysql	Kubernetes namespace
wordpress:

Name	Default Value	Difinition
deployment.image	wordpress:4.8-apache	Docker image for Wordpress
deployment.replicaCount	1	Number of Pods to run
service.type	LoadBalancer	Kubernetes Service type
service.port	80	service port
service.nodePort	80	Publishing port
resources	``	optional resources requests/limits
mysql:

Name	Default Value	Difinition
deployment.image	mysql:5.6	Docker image for MySQL
deployment.replicaCount	1	Number of Pods to run
service.type	ClusterIP	Kubernetes Service type
service.port	3306	Publishing port
pvc.accessMode	ReadWriteOnce	PVC Access mode
pvc.storage	2Gi	PVC Storage size
ingress:

Name	Default Value	Difinition
ingress.enabled	true	enable / disable engress plugin
ingress.annotations	``	Annotations of ingress object
hosts.host	chart-example.local	domain host value
hosts.paths		URL sub folder path
ingress.tls		SSL Certificate path
Uninstall

Execute the next command to get the list of helm releases
helm list
Execute the next command to uninstall helm release by RELEASE_NAME
helm uninstall RELEASE_NAME
License

MIT License

Copyright (c) 2020 sevilbeyza
