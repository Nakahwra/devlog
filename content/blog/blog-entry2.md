---
date: 2020-04-26
description: "Postagem relacionada com a configuração do servidor na nuvem."
featured_image: "/images/nuvem.jpg"
title: "Criando um servidor na nuvem"
---

---
#### 1 - CONFIGURANDO SERVIDOR NA NUVEM

Para a segunda entrega do Projeto Interdisciplinar, deveríamos configurar um servidor na nuvem para fazermos o upload do blog e torná-lo acessível pela internet. 

Decidimos utilizar a plataforma [EC2](https://aws.amazon.com/pt/ec2/) da Amazon Web Services onde podemos alugar computadores virtuais para rodarmos a nossa aplicação.

---
#### 2 - CRIANDO E CONFIGURANDO INSTÂNCIA DO SERVIDOR

Através da plataforma do EC2 conseguimos criar uma instância de servidor. Para o sistema operacional que rodará nele, escolhemos o Ubuntu 18.04 por recomendação do professor Ricardo.

![](/images/instancia.png)

Abrimos também uma porta do tipo HTTP 80/TCP, além da SSH 22/TCP padrão, para que pudessemos acessar o servidor pela internet e deixamos os resto das configurações como padrão.

![](/images/instancia2.png)

Feito isto, prosseguimos para o launch da instância e baixamos a chave privada que usaremos pra acessar o servidor por SSH.

![](/images/instancia3.png)

---
#### 3 - CONFIGURANDO SERVIDOR VIA SSH

Para acessarmos o nosso servidor, seguimos os passos indicados pela plataforma da AWS. Primeiro, mudamos a permissão da nossa pair key. Depois, conectamos à nossa instância utilizando o comando abaixo, onde inserimos a nossa chave e o DNS público do nosso servidor.

![](/images/ssh.png)

Tendo conectado à instância, poderemos começar a configurá-lo.

![](/images/ssh2.png)

Primeiro, atualizamos o sistema da instância com os comandos:

```
sudo apt-get update && sudo apt-get upgrade
```

Isto levará algum tempo e a instância estará pronta para ser configurada.

---
#### 4 - CONFIGURANDO WEB SERVICE

Configuramos na nossa instância o Apache2 (Apache HTTP server). Um servidor web open-source que irá gerenciar as requisições e servir os arquivos do projeto. Para instalá-lo, basta executar o comando:

```
sudo apt-get install apache2
```

Isto também levará algum tempo, porém terminado a instalação ele já estará praticamente pronto para uso.

---
#### 5 - CONFIGURANDO FIREWALL

Executamos comandos simples para habilitar e abrir portas no firewall.

##### Habilitando firewall:

```
sudo ufw enable
```

##### Habilitando portas HTTP  para que possamos acessar o servidor pela web:

```
sudo ufw allow 'Apache Full'
```

ou

```
sudo ufw allow 80/tcp
```

##### Habilitando porta SSH:

```
sudo ufw allow 'OpenSSH'
```

ou

```
sudo ufw allow 22/tcp
```

---
#### 5 - UPANDO PROJETO NO SERVIDOR

Feito todas essas configurações, já será possível acessar o servidor pela internet. Ele estará servindo uma página padrão do Apache2 que fica localizada no diretório /var/www/html e é nesse diretório que poderemos fazer o upload de nosso projeto.

![](/images/servidor.png)

Simplesmente acessamos o diretório, removemos o arquivo da página padrão do Apache mostrada acima e inserimos o nosso projeto buildado no diretório através de um clone do repositório do GitHub. Por fim, o nosso projeto está no ar e acessível pelo IP público da instância.


---