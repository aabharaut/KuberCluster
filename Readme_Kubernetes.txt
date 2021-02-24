Follow https://www.amundsen.io/amundsen/k8s_install/ for Amundsen Deployment into Kubernetes cluster using Helm 

Prerequisites:
1. kubectl command line client setup (https://kubernetes.io/docs/tasks/tools/install-kubectl/)
2. helm commmand line client setup (https://helm.sh/docs/intro/quickstart/)

Get started:
1. Add chart repository using command 
$ helm repo add stable https://charts.helm.sh/stable

2. List available chart values inside stable repo
$ helm search repo stable

3. install elasticsearch microservice using its chart value 
$helm install stable/elasticsearch --generate-name

4. clone the amundsen git repository 
$ git clone https://github.com/amundsen-io/amundsen.git

5. cd amundsen/amundsen-kube-helm

6. copy the templates/helm/values.yaml to amundsen/amundsen-kube-helm and amend the --values to this values.yaml
helm install my-amundsen ./templates/helm --values values.yaml

Error related to elasticsearch may appear due to execution of step 3. 
To remove it, disabled elasticsearch from values.yaml (step 358) and requirements.yaml (block everything) 

7. execute step 6 again.