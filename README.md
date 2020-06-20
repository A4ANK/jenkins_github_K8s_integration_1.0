# Integration of Kubernetes(using nfs-server & 3rd party nfs-client Dynamic provisioning) with jenkins and Github.
## to create resources like Pods, Deployment, PVC and Service, etc on the top of K8s.

1. Create container image that’s has Jenkins installed  using Dockerfile  Or You can use the Jenkins Server on RHEL 8/7
2. When we launch this image, it should automatically starts Jenkins service in the container.
3. Create a job chain of job1, job2, job3 and  job4 using build pipeline plugin in Jenkins 
4. Job1 : Pull  the Github repo automatically when some developers push repo to Github.
5. Job2 : 
   i. create persistentVolumeClaim.
   ii. create service for the application.
   iii. create deployment for the application.
6. Job3 : Test your app if it  is working or not.
7. Job4 : if app is not working , then send email to developer with error messages and redeploy the application after code is being edited by the developer
