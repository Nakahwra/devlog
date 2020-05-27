---
date: 2020-05-26
description: "Postagem relacionada com o registro do domínio"
featured_image: "/images/dns.jpg"
title: "Registrando um domínio e configurando registro MX"
---

---
#### 1 - COMPRANDO UM NOME DE DOMÍNIO FQDN, CONFIGURANDO REGISTROS DNS E APONTANDO PARA O SERVIDOR 

Para a terceira entrega do Projeto Interdisciplinar, decidimos escolher como plataforma para o registro do nosso host de domínio FQDN (em inglês, Fully Qualified Domain Name, ou em Português, Nome de Domínio Completamente Qualificado) a [Hostinger](https://www.hostinger.com.br/). Após a escolha, efetuamos a compra deste domínio: [devlog.host](http://www.devlog.host/).

Em seguida, para a configuração dos registros de DNS (em inglês, Domain Name System, ou em português, Sistema de Nomes de Domínio) utilizamos o recurso chamado de [Route 53](https://aws.amazon.com/pt/route53/) da AWS (host de hospedagem do nosso blog/portfólio). Passos para a configuração:

- Acessando o recuso do Route 53, iremos criar uma nova zona hospeada.

![](/images/dns1.jpg)

![](/images/dns2.jpg)

- Nos campos de criação, informamos o nome de domínio em que havíamos adquirido.

![](/images/dns3.jpg)

- Depois da criação, foram gerados automaticamente pelo Route 53 os NS (Nameservers) e o SOA (Service-oriented architecture).

![](/images/dns4.png)

- Em seguida, criamos 3 conjuntos de registros: *.delog.host, www.delog.host e (espaço em branco)devlog.host e apontamos os mesmos para o IP do nosso servidor, para que o nosso domínio pudesse ser acessível através de "qualquercoisa".devlog.host, www.devlog.host e também apenas devlog.host (sem nada antes do domínio).

![](/images/dns5.jpg)

![](/images/dns6.jpg)

![](/images/dns7.jpg)

Ademais, no apontamento para o servidor navegamos até o gerenciamento do nosso domínio no site da Hostinger e substituímos os NS (Nameservers) que apontavam para os servidores da plataforma pelos nossos gerados pelo recurso do Route 53 como citado anteriormente. Com isso, o nosso blog já estava acessível pelo domínio que havíamos adquirido.

![](/images/dns8.png)

---
#### 2 - CONFIGURANDO REGISTRO MX (MAIL EXCHANGER)

Primeiramente, criamos uma conta no [Zoho Mail](https://www.zoho.com/pt-br/mail/) para que pudéssemos possuir um e-mail com domínio próprio. Prontamente, seguimos as etapas necessárias descritas no site para configurar o nosso e-mail e ligá-lo ao domínio através do registro MX:

- Primeiro, verificamos a propriedade do nosso domínio através da criação de um registro CNAME.

![](/images/mx1.jpeg)

- Em seguida, fizemos a configuração do registro MX no Route 53, fazendo com que as entradas de recepção de e-mails no DNS apontem para os registros MX do Zoho Mail. 

![](/images/mx2.jpg)

- Configuramos o SPF (Sender Policy Framework) através da criação de um registro TXT com os valores específicados na imagem abaixo para conceder permissão de enviar e-mails usando o nosso nome de domínio.

![](/images/mx3.jpg)

- Também configuramos o DKIM (DomainKeys Identified Mail) com a criação de outro registro TXT para um melhor recebimento e envio de e-mails, pois ele utiliza criptografia para validar se um e-mail é seguro ou não.

![](/images/mx4.jpeg)

Desta forma, o registro MX está configurado e o nosso receptor de e-mails está apontando para os servidores do Zoho Mail. Assim, podemos enviar e receber e-mails com o e-mail criado (webmaster@devlog.host) através da plataforma.

![](/images/mx5.jpg)

Afinal, fizemos o encaminhamento dos e-mails recebidos através da plataforma para um e-mail pessoal do [Gmail](https://gmail.com/):

- Acessamos o nosso e-mail pessoal e fomos até as configurações.

![](/images/gmail1.jpg)

- Nas configurações, entramos na aba de "Contas e importação".

![](/images/gmail2.jpg)

- Escolhemos na parte de "Enviar e-mail como:" a opção de "Adicionar outro endereço de e-mail".

![](/images/gmail3.jpg)

- Em seguida, informamos um nome desejado para o nosso e-mail que será adicionado na conta pessoal e o endereço de e-mail que havíamos criado no Zoho Mail.

![](/images/gmail4.jpg)

- Para podermos enviar e receber e-mails, configuramos o servidor STMP de acordo com os dados do Zoho Mail, além de informamos o nome de usuário (e-mail) e a senha.

![](/images/smtp.jpg)

![](/images/gmail5.jpg)

- Também informamos o código de confirmação enviado ao nosso e-mail da plaforma do Zoho.

![](/images/gmail6.jpg)

Por fim, depois de todos os passos podemos receber os e-mails que são direcionados a webmaster@devlog.host através de um e-mail pessoal, conseguindo também enviar e responder os e-mails encaminhados por meio do mesmo.