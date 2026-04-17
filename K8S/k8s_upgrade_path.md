# k8S upgrade

### Current version:
1.29.8

## related componetes to consider

 1. Calico
 Deployed via tigera operator
 2. Api's not v1beta or beta
 possible problem:

     kubectl api-versions|grep -i alp
   ==     k8s.nginx.org/v1alpha1 == 
  ==      monitoring.coreos.com/v1alpha1 == (Seems related to alertmanager, part of Prometheus)
3. 


## k8s versions are:

Releases:
https://kubernetes.io/releases/

### Current v1.35

EOL:
https://kubernetes.io/releases/#end-of-life-releases



## Order of upgrade

### 1. calico update to v3.29 
Need to find out which tigera operator provides it.
tigera-operator one of the releases:
[v1.36.11](https://github.com/tigera/operator/releases/tag/v1.36.11)
[v1.36.8](https://github.com/tigera/operator/releases/tag/v1.36.8)


### 2. k8s upgrade to v1.32 (still EOL)

### 3. calico update to v3.30 (pre-latest version)
tigera-operator:
related releases, one of :
[v1.38.2](https://github.com/tigera/operator/releases/tag/v1.38.2) - Calico version: v3.30.1
[v1.38.5](https://github.com/tigera/operator/releases/tag/v1.38.5) - Calico version: v3.30.2

it supports v1.31 -  v1.35

### 4. k8s upgrade to v1.35

### ideally 5. calico update to latest v3.31




 

<!--stackedit_data:
eyJoaXN0b3J5IjpbNDM1NDY2MzI0XX0=
-->