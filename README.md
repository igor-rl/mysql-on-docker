![header-igor-projetos](https://github.com/igor-rl/assets/blob/main/img/github-projetcs-header.jpg)

# MYSQL ON DOCKER
![MySQL](https://img.shields.io/badge/MySQL-00758F?style=for-the-badge&logo=mysql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)


## Índice
[🐬 MYSQL ON DOCKER](#-mysql-on-docker)<br>
[🚀 Instalação e utilização](#-instalação-e-utilização)<br>
[🌐 Conexão via docker.host.internal](#-conexão-via-dockerhostinternal)<br>
[🖥️ Configuração do docker.host.internal no windows](#️-configuração-do-dockerhostinternal-no-windows)


## 🐬 MYSQL ON DOCKER
**Sobre este projeto:**<br>
Este projeto permite configurar um banco de dados MySQL de maneira rápida e fácil utilizando o Docker, ideal para ambientes de desenvolvimento. A configuração usa a imagem oficial do MySQL 8.0 no Docker, criando um ambiente pronto para ser utilizado em testes e desenvolvimento.

**Extra Hosts:**<br>
O arquivo `docker-compose.yaml` contém uma configuração extra_hosts `docker.host.internal`. Essa configuração permite que qualquer aplicação do seu ambiente de desenvolvimento - seja local, no docker ou kubernets - acesse o banco de dados MySQL. Isso é util pois não é necessário criar um novo container para cada aplicação que deseja acessar o banco de dados. <br>

**Vantagens:**
- Ter os mesmos dados de conexão para todas as aplicações, facilitando a configuração e manutenção do ambiente;
- Não é necessário criar um novo container para cada aplicação que deseja acessar o banco de dados;
- A configuração é feita uma única vez e pode ser utilizada por todas as aplicações do ambiente de desenvolvimento.
- Os dados do banco de dados são mantidos em um único container, facilitando a manutenção e backup dos dados.

## 🚀 Instalação e utilização

<ul>

**1️⃣ Clonar o repositório**

Primeiro, clone o repositório para sua máquina local:
```bash
git clone https://github.com/igor-rl/seu-repositorio.git
cd seu-repositorio
```

##

**2️⃣ Configuração do Docker**

Certifique-se de ter o Docker instalado em sua máquina. Caso não tenha, você pode baixar e instalar o Docker [aqui](https://www.docker.com/products/docker-desktop/).<br>
Com o Docker instalado, basta rodar o seguinte comando para subir o MySQL no Docker:
```bash
docker-compose up -d
```

##

**3️⃣ Acessar o container do banco de dados**

Para acessar o banco de dados dentro do container, execute:
```bash
docker exec -it mysql bash
```

Em seguida, você pode entrar no MySQL com o seguinte comando:
```bash
mysql -u root -p
```
Digite a senha `root` para acessar o banco.

##

**4️⃣ Criar um banco de dados**
Após acessar o MySQL, você pode criar o banco de dados de exemplo:
```sql
CREATE DATABASE exemplo;
```
Esse comando criará um banco de dados chamado `example`, que pode ser utilizado no seu projeto de desenvolvimento.
</ul>
<br>

## 🌐 Conexão via docker.host.internal
Qualquer aplicação local, docker ou kubernets pode acessar o banco de dados MySQL utilizando o host `docker.host.internal` no lugar de `localhost`.

**Exemplo de conexão sql**
```
mysql -h docker.host.internal -u root -p
```

Caso ainda não tenha configurado o `docker.host.internal` no seu sistema, siga as instruções abaixo:


<br>

## 🖥️ Configuração do docker.host.internal no windows
<ul>

**1️⃣ Abra o prompt de comando como administrador**

Clique com o botão direito do mouse no ícone do prompt de comando e selecione "Executar como administrador".

##

**2️⃣ Edite o arquivo hosts**

Digite o seguinte comando para abrir o arquivo `hosts` no bloco de notas:
```bash
notepad C:\Windows\System32\drivers\etc\hosts
```

##

**3️⃣ Adicione a entrada docker.host.internal**

Adicione a seguinte linha ao arquivo `hosts`:

```plainttext
127.0.0.1 docker.host.internal
```
Isso irá mapear docker.host.internal para o IP local, permitindo que os containers se conectem ao host.

##

4️⃣ Salve e feche o arquivo
Depois de adicionar a linha acima, salve o arquivo e feche o Bloco de Notas.

Agora, os containers Docker no Windows poderão acessar o host utilizando docker.host.internal.
</ul>

##

<br>

<div align="center">

[![GitHub](https://img.shields.io/badge/GitHub-Igor_Lage-blue?style=social&logo=github)](https://github.com/igor-rl) 

![Static Badge](https://img.shields.io/badge/18--03--2025-black)


</div>
