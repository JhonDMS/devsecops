# DevSecOps

Este archivo tiene los apuntes de la investigación en el area DevSecOps

## Herramientas


* Threat Playbook Framework
* IDE (Sonar Lint, IntelliJ Idea, VS Code, Eclipse)
* Git
* JUnit
* Pre Commit Hooks
* Maven
* Zap Proxy
* Sonarqube
* Findbugs
* PMD
* IDE Plugins.(Sonar Lint)
* Chef Inspec (Compliance as code)
* Jenkins
* Bitbucket Pipelines
* Linux
* Wireshark

## Infraestructura como código
---------------------------

* Terraform
* Ansible
* Chef
* Chef Inspec
* Puppet
* Saltstack


### Ansible
 * Curso Udemy de Ansible.

### Terraform
* [Proveedor Bitbucket para terraform, permite crear repositorios](https://www.terraform.io/docs/providers/bitbucket/index.html)


## Jenkins

* [Jenkins Docker](https://github.com/jenkinsci/docker/blob/master/README.md)


## Seguridad
----

* [Zap Proxy](https://www.zaproxy.org/)
* dotdotpwn: Fuzzing para buscar acceso a directorios fuera del CGI Home

## Zap Proxy
---

### Análisis Zap Proxy



* [Path Traversal](http://projects.webappsec.org/Path-Traversal)
* [Path Traversal 2](http://cwe.mitre.org/data/definitions/22.html)


## OWASP
----



### Threat Model Playbook
----

* [Threat Playbook](https://we45.gitbook.io/threatplaybook/)


### WebGoat

Aplicación Java Web vulnerable para pruebas de seguridad. 

* [Aplicacion Web Vulnerable](https://github.com/WebGoat/WebGoat)


```
curl https://raw.githubusercontent.com/WebGoat/WebGoat/develop/docker-compose.yml | docker-compose -f - up
```

* http://localhost:8080/WebGoat
* http://10.252.226.114:8080/WebGoat


```
dotdotpwn -m http -h 10.252.226.114
```

## Videos
---

* Web application security: 10 things developers need to know   
https://youtu.be/qjrkV4RjgIU



## Glosario
---
* DAST: Dynamic Application Security Testing
* SAST: Static Application Security Testing

