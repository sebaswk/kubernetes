# KUBERNETES REPOSITORY
This repository has kubernetes files with simple everyday templates.


## File guide
| Templates name | Description |
|:------|-------------|
| [Namespace](namespace.yml) | Create a Namespace |
| [Alb](alb.yml) | Create an Aplication Load Balancer |


## Install KUBECTL
Install kubectl in its latest version on linux:
https://github.com/sebaswk/bash/blob/main/kubectlInstall.sh

#### Configure KUBECTL
*This setup requires AWS Cli to be installed.*
##### Command:
- aws eks update-kubeconfig --name "cluster name"

##### Test:
- kubectl get pods --all-namespaces


### Probable mistakes
*If you have permission problems in your cluster, review the "configmap" that contains the users and roles that can modify it.*

##### Command:
- kubectl -n kube-system edit configmap aws-auth

##### It should look something like this: (In this case, the cluster is in AWS EKS)
- mapUsers: |
    - userarn: arn:aws:iam::356198252393:user/eksadmin
    - username: eksadmin
    - groups:
        - system:masters


## About me
https://github.com/sebaswk