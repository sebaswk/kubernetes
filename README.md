# KUBERNETES REPOSITORY
This repository has kubernetes archives with simple manifest templates.


## File guide
| Manifest name | Description |
|:------|-------------|
| [Namespace](Namespace.yml) | Create a Namespace |
| [Pod](podDeployment.yml) | Create pod |
| [Service](service.yml) | Create service |
| [Application Load Balancer](loadbalancerService.yml) | Create an Aplication Load Balancer |
| [Pod with Ingress Controller](podIngressKong.yml) | Create pod with ingress controller Kong |
| [ConfigMap](configMap.yml) | Create config map |
| [Pod with ConfigMap](podConfigMap.yml) | Create pod with Config Map |


## Install KUBECTL
Install kubectl in its latest version on linux:
https://github.com/sebaswk/bash/blob/main/kubectlInstall.sh

#### Configure KUBECTL
*This setup requires AWS Cli to be installed.*
##### Command:
- aws eks update-kubeconfig --name "cluster name"

##### Test:
- kubectl get pods --all-namespaces
- kubectl run -i --tty --rm debug --image=busybox --restart=Never -- sh

## Probable mistakes
*If you have permission problems in your cluster, review the "configmap" that contains the users and roles that can modify it.*

##### Command:
- kubectl -n kube-system edit configmap aws-auth

##### It should look something like this: (In this case, the cluster is in AWS EKS)
- mapUsers: |
    - userarn: arn:aws:iam::999999999999:user/useradmin
    - username: useradmin
    - groups:
        - system:masters

### Kong - Konga
- Kong: https://docs.konghq.com/kubernetes-ingress-controller/latest/deployment/eks/
- Kong - Konga: https://github.com/Kuari/kong-konga-docker-compose


## About me
https://github.com/sebaswk
