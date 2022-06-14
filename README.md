# README

This project maintains the Kubernetes manifests for the services of NIC ASDD LMS project. The project also maintains skaffold.yaml to start all services in a local development environment. Other services are required to be checked out alongside this repo i.e. at the same directory level

Required directory structure:

        |
        --infra
        --admin-portal
        --another services
        --yet-another-service
        --...

Steps to run:

1. Install minikube and skaffold
2. Start minikube and enable ingress addon using the following command

        minikube start --driver=docker
        eval $(minikube -p minikube docker-env)
        minikube addons enable ingress

3. Clone this repository

        git clone https://github.com/nic-asdd-lms/infra.git

4. Clone all other repositories in the NIC ASDD LMS

        git clone https://github.com/nic-asdd-lms/admin-portal.git
        git clone https://github.com/nic-asdd-lms/signup-login-logout-api.git
        cd signup-login-logout-api.git
        git checkout 1.1

5. Run the following command and note down the minikube ip address

        minikube ip

6. Edit the hosts file to add the ip mapping for the minikube ip address (e.g. 192.168.49.2 lms.nic.in)

        sudo nano /etc/hosts

7. Start skaffold

        skaffold dev

8. Open browser and go to url mapped in the hosts file, for example: <https://lms.nic.in/>
9. In case the browser displays a warning page, bypass it by typing the string "thisisunsafe" on the browser window

Refer: <https://skaffold.dev/>
