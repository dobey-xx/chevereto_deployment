Currently it's only available to deploy as a docker container.
I wanted to use it within my kubernetes playground so I've created these files to deploy it within kubernetes.

I've already setup a NGINX-Ingress and Cert-Manager, so this deployment assumes you already have that.

Run in the following order to be sure it's all happy
1. run the pvc.yaml to create the 2 claims for the persistent storage, one is for your images and one is for your database
2. run the secret.yaml to create the secret which holds your user/pass and root_pass for the mariaDB pod, encoded in base64.
3. run the deploymentdb.yaml to create the mariaDB deployment
4. run the deployment.yaml to create the chevereto deployment
5. run the services.yaml to assign a clusterIP to both deployments
6. run the ingress.yaml to create the ingress to connect this to the outside world.


