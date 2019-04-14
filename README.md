### k8s ingress (native container gcp loadbalancer NEG),SSL,IP Public Static, HPA Autoscale

##### Deployment = Rolling Update, readinessProbe/livenessProbe ######

##### HPA (Horizontal Pod Autoscaler) = Trigger by CPU pods ######

##### Service = with annatation  NEG (container-native load balancing) cloud.google.com/neg: '{"ingress": true}' #####

