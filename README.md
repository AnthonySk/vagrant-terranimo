# Demo Vagrant - Application Terramino

Project to bring forward a virtual machine via Vagrant with provisioning to run the Terramino application (educational demo via HashiCorp's Docker).


## 📦 Technologies used

- Vagrant : automatize creation & provisioning VM
- VirtualBox : provider for host VM 
- Ubuntu 24.04 : VM OS (via box `hashicorp-education/ubuntu-24-04`)
- Docker & Docker Compose : Installed automatically in VM with script
- Git : used for clone the Terramino project in VM

## 🔧 Automatically configuration

via Vagrantfile :
- Configure Ubuntu 24.04
- redirect ports
- Provisionning :
	- Launch 'install-dependencies.sh'
		- Install Docker
		- Clone repo 'terramino-go'
		- Create script 'reload-terramino '
	- Launch terranimo automatically
	- Create restart-terranimo command
	- Create start-terranimo command
	- Create reload-terramino command
	
## ▶ Launch VM

Since root of project in bash : 
- vagrant up

Go the terranimo : 
- Backend : http://localhost:8080
- Frontend : http://localhost:8081

## Manage VM

- vagrant halt # shutdown
- vagrant destroy # delete VM 




![Vagrant](https://img.shields.io/badge/Vagrant-2.3+-blue?logo=vagrant)
