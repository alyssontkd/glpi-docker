# Projeto glpi-docker
Este projeto visa disponibilizar a versão 9.2.3 do GLPI utilizando uma imagem docker customizada.

# Versões utilizadas na geração das imagens
Abaixo estão listadas, para fins de documentação, todas as versões utilizadas para a execução deste projeto, contudo acredito que você não tera problemas em executar esses passos com outras versões e distribuições linux.

## Docker
**Para descobrir a versão do docker, digite o comando abaixo:**
```
# docker --version
```
**O retorno do comando acima será algo como:**
```
Docker version 18.03.1-ce, build 9ee9f40
```

## Docker Compose
**Para descobrir a versão do docker, digite o comando abaixo:**
```
# docker-compose --version
```
**O retorno do comando acima será algo como:**
```
docker-compose version 1.21.2, build a133471
```

## Sistema Operacional 
**Para descobrir a versão do sistema operacional digite o comando**
```
# lsb_release -irc
```
**O retorno será algo como o trecho abaixo:**
```
Distributor ID: Ubuntu
Release:        18.04
Codename:       bionic
```

## GLPI
**O GLPI que está sendo instalado neste projeto é a versão 9.2.3**

## MySQL
**A versão do MySQL utilizada foi a versão 5.7**


# Como instalar os pré-requisitos? 
## Instalando o docker via repositório do Ubuntu
**A instalação padrão via repositório do Ubuntu consite em um simples comando 'apt'**
```
$ sudo apt install docker.io
```
**Para iniciar o docker digite o comando:**
```
$ sudo systemctl start docker
$ sudo systemctl enable docker
```
**Prontinho! Para testar se seu docker foi instalado com sucesso digite o comando do docker que retorna a versão instalada. veja abaixo o camando e a saída**
```
$ docker --version
Docker version 18.03.1-ce, build 9ee9f40
```

## Instalando o docker a partir do repositório oficial do docker
**Para iniciar a instalação via repositório oficial do docker, há a necessidade de instalar todos os pré-requisitos**
```
$ sudo apt update
$ sudo apt install apt-transport-https ca-certificates curl software-properties-common
```
**Adicione o repositório docker ao repositório do seu sistema operacional. Para isso crie o arquivo '/etc/apt/sources.list.d/docker.list'. neste arquivo cole uma das seguintes linhas descritas abaixo:**
```
deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable
```
OR
```
deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic edge
```
OR
```
deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic nightly
```

**Agora adicione a chave GPG do docker e atualize as referencias do repositório**
```
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
$ sudo apt update
```

**Finalmente agora poderemos instalar o docker**
```
$ sudo apt install docker-ce
```

**Prontinho! Para testar se seu docker foi instalado com sucesso digite o comando do docker que retorna a versão instalada. veja abaixo o camando e a saída**
```
$ docker --version
Docker version 18.03.1-ce, build 9ee9f40
```

# Instalando o docker-compose
**Baixe a última versão do docker-compose**
```
$ sudo curl -L https://github.com/docker/compose/releases/download/1.21.2/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose
```
**Aplique as permissoes de execução ao arquivo**
```
$ sudo chmod +x /usr/local/bin/docker-compose
```
**Pronto! Seu docker-compose já deve estar instalado. Valide a instalação com o comando abaixo:**
```
# docker-compose --version
```
**O retorno do comando acima será algo como:**
```
docker-compose version 1.21.2, build a133471
```


# Inicializando o GLPI neste projeto
**Agora seu sistema operacional já está com o docker e docker-compose instalado, entao basta clonar este repositório ou baixar os arquivos e colocar na para '/var/www/docker' e mandar recompilar a imagem.**
__Para clonar o repositório digite:__
```
$ git clone https://github.com/alyssontkd/glpi-docker.git
```
__Agora entre no diretório e rode o docker-compose:__

```
# cd '/var/www/docker/glpi-docker
# docker-compose up -d
```
**Depois deste comando a imagem será recompilada e ao fim o GLPI podera ser acessado via URL: http://127.0.0.1**


# Dicas importantes
**Para verificar se os pods estão rodando:** 
``` 
$ docker ps -a
```
