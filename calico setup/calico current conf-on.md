## calico conf-on


# node-to-node BGP mesh
based on
```yaml

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
eyJoaXN0b3J5IjpbLTE0ODE4NDQ1MjNdfQ==
-->