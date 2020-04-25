---
date: 2020-03-23
description: "Postagem relacionada com a criação do portfólio/blog."
featured_image: "/images/post.jpg"
title: "Desenvolvimento do Projeto"
---

---

#### 1 - INSTALAÇÃO DA FERRAMENTA E ESTRUTURA BASE DO PROJETO

Primeiro, instalamos a ferramenta de desenvolvimento que iríamos usar, um static generator chamado Hugo. Seguindo a documentação, conseguimos montar uma base e inicializar o projeto sem muitos problemas. É uma ferramenta relativamente simples e de fácil manuseio.

Junto com a instalação da ferramenta, adicionamos também ao projeto um tema pronto chamado Ananke que será o layout base do website. A adição de temas prontos agiliza a construção dos sites e permite uma personalização básica do projeto por parte dos desenvolvedores.

Feito isso, temos a base do nosso projeto criado assim:

![](/images/base.jpg)

Começaremos assim, a personalizar o site.

---
#### 2 - PERSONALIZAÇÃO GERAL DO SITE

Primeiro, mudamos o nome do site, adicionamos uma descrição na home page e depois criamos as seções de menu: Blog, Projetos Pessoais, Quem somos e Tech Stack.

Para a criação das seções de menu, foram criadas pastas específicas para cada um deles, em que dentro das mesmas seria feito um arquivo principal, contendo título, descrição e imagem. Ademais, um arquivo para cada postagem relacionada a sua seção do menu, contendo título, data, descrição e imagem.

Ao criar as seções do menu, o próprio Hugo inclui as mesmas no cabeçalho da página em ordem alfabética.

Posteriormente, personalizamos o banner de cada seção de menu com imagens relacionadas ao tema e então a personalização geral do site já estava praticamente finalizada. 

Sobre a questão de paginações e rotas, o Hugo facilita muito na estruturação e o próprio tema que utilizamos já vem configurado previamente, então não foi preciso nos preocuparmos muito com isso, apenas descobrindo como estava estruturado no próprio tema foi possível fazer as personalizações necessárias.

![](/images/personalizacao_geral.jpg)

---
#### 3 - PERSONALIZAÇÃO DA SEÇÃO “QUEM SOMOS”

Para personalizar a seção “Quem somos”, foi necessário fazer alterações diretamente no layout. Devido ao tema instalado usar um layout padronizado para cada tipo de página, configuramos o projeto para que apenas as alterações feitas no layout da “Quem somos” não afetassem outras single-pages.

Portanto:
- Criamos no diretório de nosso projeto (não no do tema) um arquivo HTML que sobrescreve apenas o layout da página “Quem Somos”;
- Criamos um arquivo de CSS onde seriam escritos os estilos da página e os importei como parâmetro no arquivo de configuração do projeto;
- Por fim, fizemos as personalizações necessárias.

![](/images/personalizacao_quem_somos.jpg)

---
#### 4 - ALIMENTANDO O SITE COM CONTEÚDO

Por fim, com o site totalmente personalizado, fizemos a postagem do blog entry (esta postagem) e a do Tech Stack. Além disso, nós criamos alguns posts genéricos em cada uma das seções apenas para o site não ficar vazio, já que nós mesmos não tínhamos conteúdo relevante para preenchê-lo no momento.
