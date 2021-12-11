### k8s ingress (native container gcp loadbalancer NEG),SSL,IP Public Static, HPA Autoscale

##### Deployment = Rolling Update, readinessProbe/livenessProbe ######

##### HPA (Horizontal Pod Autoscaler) = Trigger by CPU pods ######

##### BackendConfig = Config timeout for ingress #####

##### Service = with config annotations NEG (container-native load balancing) cloud.google.com/neg: '{"ingress": true}' #####
 
##### Ingress = Use Global Loadbalancer GCP with config annotations Global IP Public,GCP SSL #####


note :
GKE must be run in VPC-native for support NEG 


standard ingress vs ingress with NEG (container-native load balancing)
![alt text](https://cloud.google.com/kubernetes-engine/images/neg.svg)
Benefits:
- container-native load balancer talks directly with the Pods, and connections have fewer network hops, both latency and throughput are improved.
- you have visibility into the round-trip time (RTT) from the client to the HTTP(S) load balancer, including Stackdriver UI support. This makes troubleshooting your services at the NEG-level easier
- Container-native load balancing offer native support in Google Kubernetes Engine for several features of HTTP(S) Load Balancing, such as integration with GCP services like Cloud Armor, Cloud CDN, and Cloud Identity-Aware Proxy
- GKE Dataplane V2 (Cilium + eBPF) is implemented without kube-proxy and does not rely on iptables for service routing. This removes a major bottleneck for scaling Kubernetes services in very large clusters
