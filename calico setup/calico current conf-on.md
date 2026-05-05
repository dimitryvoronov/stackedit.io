## calico conf-on


### node-to-node BGP mesh
based on
nodeToNodeMeshEnabled: true
bgp: Enabled
кажд нода калико имеет связь (bgp session) с другой
10.210.128.128/27 - vlan dedicated for k8s
10.210.131.0/25 - dedicated subnet to see k8s services in network?
/25 дает не более 128 кластер сервисов доступно получается

172.31.252.0/22 -  calico subnet
pod cidr 
block /26 here, so 





```yaml
++++
---
apiVersion: crd.projectcalico.org/v1
kind: BGPConfiguration
metadata:
# name: ru-dc1s-a-int
name: default
spec:
logSeverityScreen: Info
nodeToNodeMeshEnabled: true
asNumber: 65000
serviceClusterIPs:
- cidr: 10.210.131.0/25 -  доступ к сервисам кубера для уровня V
---
apiVersion: crd.projectcalico.org/v1
kind: BGPPeer
metadata:
name: ru-dc1s-a-int-csw01
spec:
peerIP: 10.210.254.10
asNumber: 65002
---
apiVersion: crd.projectcalico.org/v1
kind: BGPPeer
metadata:
name: ru-dc1s-a-int-csw02
spec:
peerIP: 10.210.254.11
asNumber: 65002
+++++

apiVersion: operator.tigera.io/v1
kind: Installation
metadata:
name: default
spec:
# Configures Calico networking.
calicoNetwork:
# Note: The ipPools section cannot be modified post-install.
ipPools:
- cidr: 172.31.252.0/22
encapsulation: None
natOutgoing: Enabled
nodeSelector: all()
bgp: Enabled

```


# 
#
#




<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyMTYwMTExOTMsNTA3MjI0ODUsLTE4ND
k3ODY5NTZdfQ==
-->