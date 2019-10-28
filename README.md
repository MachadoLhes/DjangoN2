# DjangoN2
Teste de Django para o cargo de N2 na equipe de Ongoing da B2W Digital

A aplicação deste repositório segue o tutorial de Django Girls, disponível em: https://tutorial.djangogirls.org/pt/

A aplicação utiliza a versão LTS *(Long Term Suport)* mais recente do Django - `Django 2.2.6 LTS`

---

## Rodando a aplicação com Docker

Esta aplicação pode rodar em um container Docker, para fazê-lo, temos duas opções:

## 1 - Rodando a imagem diretamente do DockerHub

A imagem desta aplicação está disponível no [DockerHub](https://hub.docker.com/r/machadolhes/django_n2), faça o download com o comando:

```shell
$ docker pull machadolhes/django_n2
```

Para executá-la, rode o seguinte comando:

```shell
$ docker run -p 8000:80 machadolhes/django_n2:latest
```

> **Observação:** A aplicação está sendo executada na `porta 80` do container, então estamos mapeando a `porta 8000` do host para a porta correspondente no container

A aplicação estará disponível em [`localhost:8000`](localhost:8000)

## 2 - Construindo localmente a imagem

Este repositório possui um arquivo `docker-compose`, isso facilitará o processo, caso queira construir a imagem localmente. Para isso, é primeiramente necessário possua o `docker-compose` instalado em sua máquina. 

### 2.1 - Instalando o docker-compose

Iremos instalá-lo com o seguinte comando:

```shell
$ sudo apt install docker-compose
```

### 2.2 - Construindo a imagem

Simplesmente rode o comando:

```shell
$ docker-compose build
```

A imagem será construída e ficará disponível com o nome `machadolhes/django_n2:latest`

### 2.3 - Subindo o container

Finalmente, para subir o container:

```shell
$ docker-compose up
```

A aplicação estará disponível em [`localhost:8000`](localhost:8000)

---

## Como rodar esta aplicação localmente?

> **Observação:** Este tutorial leva em consideração que o sistema operacional utilizado seja Linux

## 1 - Utilizando o **venv**

O **ambiente virtual** - venv, abreviando - é uma ferramenta utilizada para criar ambientes Python isolados. Isso faz com que as dependências sejam sempre instaladas em uma virtualenv específica, não mais no sistema operacional

### 1.1 - Primeiramente crie uma pasta para seus ambientes virtais

```shell
$ mkdir ~/venvs 
$ cd ~/venvs
```

> Sinta-se livre para escolher o nome que quiser para a pasta de ambientes virtuais

### 1.2 - Em seguida, crie seu ambiente virtual

```shell
$ python3 -m venv myvenv
```

> Sinta-se livre para escolher o nome que quiser para seu ambiente virtual, neste caso, utilizamos o nome `myvenv`

### 1.3 - Ative seu ambiente virtual
Para ativar seu ambiente virutal, será necessário rodar o seguinte comando:

```shell
$ . myvenv/bin/activate
```

Você saberá que seu ambiente virtual está funcionando quando ver a indicação com o nome do seu venv entre parêntesis como prefixo na linha de comando no seu console:

```shell
(myvenv) $ 
```

Como criamos o venv utilizando **Python3**, a partir de agora podemos nos referir a essa versão apenas por `python` na linha de comando

## 2 - Instalando o Django

**Django** é um framework para desenvolvimento rápido para web, escrito em Python, que utiliza o padrão model-template-view

### 2.1 - Atualizando o pip
Antes de mais nada, devemos garantir que temos instalada a última versão do **pip**, que é o software que usamos para instalar o Django:

```shell
(myvenv) ~$ python -m pip install --upgrade pip
```

### 2.2 - Instalando dependências
O projeto possui um arquivo chamado `requirements.txt`, contendo as dependências desta aplicação, rode o comando a seguir para instalar tais dependências:

```shell
(myvenv) ~$ cd ${PASTA_DO_PROJETO}
(myvenv) djangoN2$ pip install -r requirements.txt
```

> **Observação:** ${PASTA_DO_PROJETO} se refere ao diretório resultante do comando `git clone` utilizado para clonar este repositório

## 3 - Rodando a aplicação
Após as dependências terem sido instaladas, inicie a aplicação com o seguinte comando:

```shell
(myvenv) djangoN2$ python manage.py runserver
```

O console exibirá algumas informações sobre o processo que está sendo executável e você poderá acessar a aplicação através do endereço: http://127.0.0.1:8000/

ツ