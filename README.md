This project maintains the Kubernetes manifests for the services of NIC ASDD LMS project. The project also maintains skaffold.yaml to start all services in a local development environment. Other services are required to be checked out alongside this repo i.e. at the same directory level

Required directory structure:

       |
        --infra
            |
            --k8s
               |
                --.....
        --admin-portal

Steps to run:
1. Install minikube and skaffold, if not available
2. Enable ingress addon and start minikube using the following command, if not done already
3. minikube addons enable ingress
4. Clone this repository using the following command
5. git clone https://github.com/nic-asdd-lms/infra.git
6. Clone all other repositories in the NIC ASDD LMS
7. git clone https://github.com/nic-asdd-lms/admin-portal.git
8. Start minikube using the following commands
9. minikube start --driver=docker
10. eval $(minikube -p minikube docker-env)
11. minikube ip -> Note down output and add to host file (e.g. 192.168.49.2)
12. sudo nano /etc/hosts -> Add line "192.168.49.2    lms.nic.in"
13. skaffold dev
14. Open browser and go to required url, for example: https://lms.nic.in/

Refer: https://skaffold.dev/