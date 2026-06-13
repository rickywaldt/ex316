# Network

K8s has a flat network by default, pods, VM's, endpoints etc can freely communicate within the cluster. There are three types of network policies in OCP of which tier 1 (ANP) and tier 2 (NP) are discussed. ANP is Admin Network Policy, which has priority over Network Policy. UDN is User Defined Network to restrict namespace access, meaning cross-namespace communication is not possible. CUDN is Cluster Used Defined Network, which can tie multiple namespaces to the CUDN, meaning pods in namespaces within the same CUDN can communicate.
