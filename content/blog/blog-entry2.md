---
date: 2020-04-25
description: "Postagem relacionada com a configuração do servidor na nuvem."
featured_image: "/images/nuvem.jpg"
title: "Criando um servidor na nuvem"
---

---

#### 1 - CONFIGURANDO SERVIDOR NA NUVEM

Para a segunda entrega do Projeto Interdisciplinar, deveríamos configurar um servidor na nuvem para fazermos o upload do blog e torná-lo acessível pela internet. 

Decidimos utilizar a plataforma EC2 da Amazon Web Services onde podemos alugar computadores virtuais para rodarmos a nossa aplicação.

---
#### 2 - CRIANDO E CONFIGURANDO INSTÂNCIA DO SERVIDOR

Através da plataforma do EC2 conseguimos criar uma instância de servidor. Para o sistema operacional que rodará nele, escolhemos o Ubuntu 18.04 por recomendação do professor Ricardo.

![](/images/instancia.png)

Abrimos também uma porta do tipo HTTP 80/TCP, além da SSH 22/TCP padrão, para que pudessemos acessar o servidor pela internet e deixamos os resto das configurações como padrão.

![](/images/instancia2.png)

Feito isto, prosseguiremos para o launch da instância e baixaremos a chave privada que usaremos pra acessar o servidor por SSH.

![](/images/instancia3.png)

---