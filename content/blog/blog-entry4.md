---
date: 2020-05-31
description: "Postagem relacionada com a integração do Disqus no blog/portfólio e a criação da página Projetos Pessoais"
featured_image: "/images/disqus.jpg"
title: "Disqus e Projetos Pessoais"
---

---
Aqui descrevemos como integramos o Disqus para adicionar a funcionalidade de comentários em nosso site, a construção da página de projetos pessoais e como habilitamos o botão/ícone para o nosso repositório do GitHub em todas as páginas.

## Disqus
### Integrando domínio com Disqus e configurando
Para podermos usar o Disqus como comentários em nosso blog, nós devemos integrar a plataforma com o nosso domínio. 

Primeiro, criaremos uma nova instância do site na plataforma do Disqus. Criamos um nome de usuário que será exibido na seção de comentários, um Shortname (um identificador único assinado à um site Disqus), selecionamos a categoria e a linguagem.

![Criando novo site Disqus](/images/disqus1.png)

E então passamos para a próxima etapa da configuração onde inserimos o domínio que queremos integrar à instância do Disqus que está sendo criada e outras configurações menos importantes/cosméticas mais relacionadas à interação com a comunidade como: aparência, descrição, política de comentários etc.

![Configurando novo site Disqus](/images/disqus2.png)

### Habilitando Disqus no site
Convenientemente, o tema que escolhemos para o nosso blog já vem com a opção de habilitar o Disqus. Bastou apenas adicionarmos a seguinte linha de código com o Shortname no nosso arquivo de configuração que já conseguimos habilitar o Disqus:
`disqusShortname = YOURSHORTNAME`

No entanto, para adicioná-lo do zero também é simples. Se disponível, bastaria selecionar a plataforma em que nosso blog é desenvolvido e seguir as instruções e documentação.
![Escolha da plataforma](/images/disqus3.png)

Caso não disponível, como seria o nosso caso, bastaria adicionar alguns scripts e configurar algumas variáveis no código para habilitarmos a funcionalidade, seguindo [a documentação](https://disqus.com/admin/install/platforms/universalcode/).

![Configuração universal](/images/disqus4.png)

E então, nosso blog já estará pronto para receber comentários dos leitores.

![Disqus funcionando no site](/images/disqus5.png)

## Projetos Pessoais
Para alimentar a seção de projetos pessoais do blog, simplesmente criamos posts em que detalhamos algum projeto passado nosso. 

Fizemos um resumo/briefing da proposta do projeto e suas funcionalidades, detalhamos as tecnologias utilizadas para cada etapa do desenvolvimento, adicionamos screenshots das aplicações para ilustrar e deixamos o link do repositório do github para qualquer um que se interessasse pelo código.

A página pode ser acessada pelo menu acima ou por [esse link](http://www.devlog.host/projetos_pessoais/).

## Acesso ao GitHub do blog/portfólio
Para habilitar o botão/ícone do GitHub em todas as páginas do site, apenas inserimos a linha de código: 

``` github = "https://github.com/Nakahwra/devlog" ```

nos parâmetros de configuração, pois o tema [Ananke](https://themes.gohugo.io/gohugo-theme-ananke/) já vem com essa função pronta.

---