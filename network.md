# Network

K8s has a flat network by default, pods, VM's, endpoints etc can freely communicate within the cluster. There are three types of network policies in OCP of which tier 1 (ANP) and tier 2 (NP) are discussed. ANP is Admin Network Policy, which has priority over Network Policy. UDN is User Defined Network to restrict namespace access, meaning cross-namespace communication is not possible. CUDN is Cluster User Defined Network, which can tie multiple namespaces to the CUDN, meaning pods in namespaces within the same CUDN can communicate.

UDN is basically an API that creates NAD (Network Attachment Definition).

## CUDN

First create the namespace(s) with the UDN labels: k8s.ovn.org/primary-user-defined-network. You cannot edit an existing namespace for UDN.
