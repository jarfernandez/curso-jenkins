# curso-jenkins
[Vagrantfile](https://www.vagrantup.com/docs/vagrantfile/) para provisionar las máquinas del curso de [Jenkins](https://jenkins.io/) https://www.udemy.com/the-complete-jenkins-course-for-developers-and-devops

Se crean dos máquinas virtuales:
* En una se instala Jenkins con [Ansible](https://www.ansible.com/)
* La otra es para instalar [Tomcat](http://tomcat.apache.org/). La instalación de Tomcat se ha de realizar de forma manual.

Para crear las máquinas virtuales y lanzar la instalación de Jenkins, ejecutar el siguiente comando:
```
$ vagrant up
```

Acceder a Jenkins con un navegador a http://localhost:8080

Para obtener la contraseña del usuario `admin` de Jenkins, ejecutar el siguiente comando:
```
$ vagrant ssh jenkins -c "sudo cat /var/lib/jenkins/secrets/initialAdminPassword"
```

---

Tags: ansible, devops, jenkins, ubuntu, vagrant, virtualbox