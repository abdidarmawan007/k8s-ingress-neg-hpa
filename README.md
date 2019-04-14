### k8s ingress (native container gcp loadbalancer NEG),SSL,IP Public Static, HPA Autoscale

##### Deployment = Rolling Update, readinessProbe/livenessProbe ######

##### HPA (Horizontal Pod Autoscaler) = Trigger by CPU pods ######

##### Service = with config annotations NEG (container-native load balancing) cloud.google.com/neg: '{"ingress": true}' #####

##### Ingress = Use Global Loadbalancer GCP with config annotations Global IP Public,GCP SSL #####


note :
command for create Global IP Public and GCP SSL for Ingress

gcloud beta compute --project={your-gcp-project} addresses create {name-ip} --global --network-tier=PREMIUM

gcloud beta compute ssl-certificates create {name-ssl} --domains {your-domain}

