# Demo Vagrant - Application Terramino

Projet de mise en avant d'une machine virtuelle via Vagrant avec provisionning pour executer l'application Terramino (demo educative via Docker de HashiCorp).


## 📦 Technologies utilisées

- Vagrant : pour automatiser la création et le provisioning d'une machine virtuelle
- VirtualBox : comme provider pour héberger la VM
- Ubuntu 20.04 : système d’exploitation de la VM (via box `ubuntu/bionic64`)
- Docker & Docker Compose : installés automatiquement dans la VM via un script fourni
- Git : utilisé pour cloner le projet Terramino dans la VM

## 🔧 Configuration automatqiue

via Vagrantfile :
