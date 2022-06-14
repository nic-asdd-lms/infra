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
2. Enable ingress addon using the following command

        minikube addons enable ingress

3. Clone this repository

        git clone https://github.com/nic-asdd-lms/infra.git

4. Clone all other repositories in the NIC ASDD LMS

        git clone https://github.com/nic-asdd-lms/admin-portal.git

5. Start minikube and set up the docker environment variables

        minikube start --driver=docker
        eval $(minikube -p minikube docker-env)

6. Run the following command and note down the minikube ip address

        minikube ip

7. Edit the hosts file to add the ip mapping for the minikube ip address (e.g. 192.168.49.2 lms.nic.in)

        sudo nano /etc/hosts

8. Start skaffold

        skaffold dev

9. Open browser and go to url mapped in the hosts file, for example: <https://lms.nic.in/>
10. In case the browser displays a warning page, bypass it by typing the string "thisisunsafe" on the browser window

Refer: <https://skaffold.dev/>
