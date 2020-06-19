# Integration of Kubernetes with jenkins and Github
## to create resources like Pods, ReplicaSet, Deployment, PVC and Service, etc on the top of K8s.

1. Create container image that’s has Jenkins installed  using Dockerfile  Or You can use the Jenkins Server on RHEL 8/7
2. When we launch this image, it should automatically starts Jenkins service in the container.
3. Create a job chain of job1, job2, job3 and  job4 using build pipeline plugin in Jenkins 
4. Job1 : Pull  the Github repo automatically when some developers push repo to Github.
5. Job2 : 
   i. By looking at the code or program file, Jenkins should automatically start the respective language interpreter installed image container to deploy code on top of Kubernetes ( eg. If code is of  PHP, then Jenkins should start the container that has PHP already installed )
   ii.  Expose your pod so that testing team could perform the testing on the pod
   iii. Make the data to remain persistent ( If server collects some data like logs, other user information )
6. Job3 : Test your app if it  is working or not.
7. Job4 : if app is not working , then send email to developer with error messages and redeploy the application after code is being edited by the developer
