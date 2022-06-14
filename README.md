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

1.Install minikube and skaffold, if not available
2.Enable ingress addon and start minikube using the following command, if not done already

        minikube addons enable ingress

3.Clone this repository using the following command

        git clone https://github.com/nic-asdd-lms/infra.git

4.Clone all other repositories in the NIC ASDD LMS

        git clone https://github.com/nic-asdd-lms/admin-portal.git

5.Start minikube using the following commands

        minikube start --driver=docker
        eval $(minikube -p minikube docker-env)

6.Using following command note down output and add to host file (e.g. 192.168.49.2 lms.nic.in)

        minikube ip
        sudo nano /etc/hosts
        skaffold dev

7.Open browser and go to required url, for example: <https://lms.nic.in/>
8.In case of browser warning page being displayed, type string "thisisunsafe" on the browser window to get pass the browser warning

Refer: <https://skaffold.dev/>
