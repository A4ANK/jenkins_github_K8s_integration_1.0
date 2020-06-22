# Integration of Kubernetes(using NFS-server & 3rd party NFS-client Dynamic provisioning) with Jenkins and Github.
## To create resources like Pods, Deployment, PVC and Service, etc on the top of K8s.

Tasks to be created:-
1. Create container image that’s has Jenkins installed using Dockerfile Or You can use the Jenkins Server on RHEL 8/7
2. When we launch this image, it should automatically starts Jenkins service in the container.
3. Create a job chain of job1, job2, job3 and job4 using build pipeline plugin in Jenkins
4. Job1: Pull the Github repo automatically when some developers push repo to Github.
5. Job2:
   1. create a persistent volume claim.
   2. create service for the application.
   3. create a deployment for the application.
6. Job3: Test your app if it is working or not.
7. Job4: If an app is not working then trigger job 2 and then send email to the developer with error messages and then when the developer will do necessary changes in the code then redeploy the application.
![BuildPipelineView](images/view.png)

## Prerequisites:- 
A pre-installed K8s cluster(e.g. minikube). In minikube by default, there is no internal NFS dynamic provisioner is available for the storage class so it can claim a PVC or PV dynamically. so we are creating a NFS-client dynamic provisioner in the K8s cluster using a service account, cluster roles, etc., which basically uses RBAC (role-based access controls) Authorization.
[configure service accounts](https://kubernetes.io/docs/tasks/configure-pod-container/configure-service-account/)
[role based access controls](https://kubernetes.io/docs/reference/access-authn-authz/rbac/)

*Creating this part of the task is very easy in the Openshift Container Platform.
Also, install Github, Build Pipeline Plugin in Jenkins.
