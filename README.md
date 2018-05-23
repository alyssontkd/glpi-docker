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


# Inicializando o GLPI neste projeto


# Dicas importantes
