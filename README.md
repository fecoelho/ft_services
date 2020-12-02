# ft_services
O projeto consiste na implementação de uma infraestrutura com diversos serviços utilizando kubernetes. Projeto escolar realizado na [42 São Paulo](https://www.42sp.org.br/).
---
### ToC 📋

- [Introdução](#introducao)
	- [Componentes](#componentes)
	- [Tecnologias](#tecnologias)
- [Como Usar o ft_services](#como-usar)
	- [Instalar Dependências](#installation)
	- [Como Executar o ft_services](#usage)
- [Ports](#ports)

---

<a name="introducao"></a>
## Introdução

O objetivo desse projeto é a implementação e gerenciamento de **Clusters** com o **Kubernetes**
O projeto consiste na implementação de uma infraestrutura com diversos serviços utilizando Kubernetes. Portanto, instalaremos um cluster que agrupa vários containers de serviço. Cada serviço funciona em um container dedicado, e os containeres têm o mesmo nome do serviço associado. Por motivos de desempenho, os containeres são construídos no ```Alpine Linux```. Para completar o projeto, precisamos dos próximos componentes:

<a name="componentes"></a>
### Componentes

- ```MetalLB```: É um Load Balancer que gerencia o acesso externo aos seus serviços. É a única entrada para o cluster.

- ```Nginx```: É um servidor HTTP e de reverse proxy, um servidor proxy de correio e um servidor proxy TCP / UDP genérico.

- ```MariaDB```: É um sistema de gerenciamento de banco de dados derivado do MySQL com GPL (General Public License).

- ```Wordpress```: É um CMS (Content Managament System) voltado para a criação de qualquer tipo de página web.

- ```phpMyAdmin```: É uma ferramenta de software livre destinada a administrar MySQL na web.

- ```InfluxDB```: É um banco de dados de série temporal de código aberto desenvolvido por InfluxData.

- ```Telegraf```: É o agente de servidor de código aberto para ajudá-lo a coletar métricas de suas pilhas, sensores e sistemas.

- ```Grafana```: É um software gráfico e de análise de código aberto. Permite consultar, visualizar, alertar e explorar suas métricas do Time Series Database Storage (TSDB).

<a name="tecnologias"></a>
### Tecnologias

- ```Docker```: É um projeto de código aberto que automatiza a implantação de aplicativos em containeres de software.

- ```Kubernetes```: Is an open-source system for automating the deployment, scaling, and handling of containerized applications.

- ```Minikube```: É um sistema de código aberto para automatizar a implantação, dimensionamento e manuseio de aplicativos em contêineres.

- ```Alpine Linux```: É uma distribuição Linux baseada em musl e BusyBox, que tem como objetivo ser leve e segura por padrão.



[Back To The Top](#ft_services)

<a name="como-usar"></a>
## Como Executar o ft_services

<a name="installation"></a>
### Instalar Dependências

1º - Atualize seu sistema:
```console
> sudo apt-get update -y
> sudo apt-get upgrade -y
```

2º - Instale os pacotes nescessários:
```console
> sudo apt-get install curl
> sudo apt-get install apt-transport-https
> sudo apt-get install ca-certificates
> sudo apt-get install software-properties-common
```

3º - Instale o Docker

```console
> curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
> sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
> sudo apt update
> apt-cache policy docker-cesudo
> sudo apt-get install docker-ce
```
> ⚠️ Para evitar digitar sudo sempre que executar o comando docker, adicione seu nome de usuário ao grupo docker 
```console
> sudo usermod -aG docker $(whoami);
> su - ${USER}
```

4º - Instale o Minikube:
```console
> wget https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
> sudo cp minikube-linux-amd64 /usr/local/bin/minikube
> sudo chmod 755 /usr/local/bin/minikube
```

5º - Instale o Kubectl
```console
> curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl
> chmod +x ./kubectl
> sudo mv ./kubectl /usr/local/bin/kubectl
```
[Back To The Top](#ft_services)

<a name="usage"></a>
### Executar o ft_services

Após ter instalado todas as dependências, basta rodar o seguinte comando na pasta que clonou: 

```console
> ./setup.sh
```

[Back To The Top](#ft_services)

---

<a name="ports"></a>
### Ports

- ```Nginx``` on Port 80(http), 443(https), and 22(ssh)
- ```FTP``` on port 21, and 30021(passive mode)
- ```Wordpress``` on port 5050
- ```PhpMyAdmin``` on port 5000
- ```MySQL``` on port 3306
- ```Grafana``` on port 3000
- ```Influxdb``` on port 8086

[Back To The Top](#ft_services)

---
