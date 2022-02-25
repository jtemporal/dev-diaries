---
bookCollapseSection: false
weight: 21
title: "Colocando no ar"
---

# Colocando no ar

Para colocar o GitFichas no ar, eu segui os passos que eu sempre sigo. Se você quiser entender mais detalhes desse passo a passo, [tem um tutorial pra você aqui](https://jtemporal.com/do-tema-ao-ar/). Aqui vou falar sobre outros detalhes que não cubro no tutorial.

Para começar o código do GitFichas é privado. Isso quer dizer que a única pessoa que tem acesso a ele sou eu.

## O projeto é privado

Hoje, não tem nenhum motivo particular para isso, mas ao colocar o projeto no ar, minha ideia inicial era liberar uma ou duas fichas por semana. Para fazer isso, já que eu não tenho um CMS ligado no GitFichas, eu deixava os pull requests pré-prontos apenas para fazer o merge na data indicada. Assim, manter o código privado ia impedir de pessoas espiarem as fichas que iam sair.

## Tô usando Netlify

Além disso, eu aproveitei o GitFichas para finalmente aprender a usar o [Netlify](https://www.netlify.com). Esse serviço integra com o GitHub de uma forma tão linda que a configuração dele foi suuuuper intuitiva:

1. fiz a minha conta por lá;
2. associei a minha conta do GitHub com a conta do Netlify;
3. dei acesso ao Netlify para encontrar *apenas* o repositório do GitFichas (isso aqui me impressionou, já falo mais sobre);
4. esperei o primeiro build rolar (o primeiro sempre demora um tiquinho mais), e pronto.

Eu achei que ia ser mais complicado confesso, e talvez seja, se a configuração do seu site for mais complexa ou se você usar o Netlify para outras coisas como servir o site e afins. Como o meu site é servido pelo GitHub eu não precisei me preocupar com *mais nada*.

Depois disso, para cada novo pull request aberto, o bot do Netlify aparece para mostrar essa mensagem:

![Mensagem do Netlify em um pull request aberto](https://res.cloudinary.com/jesstemporal/image/upload/v1645814794/dev-diaries/netlify-message-on-pull-request_hgext1.png)

Essa mensagem é atualizada para cada commit que for feito o push para o GitHub. Para mim, que muitas vezes ajusto coisas do GitFichas pelo iPad, essa capacidade de pré-visualizar o site sem precisar rodar ele localmente é de grande ajuda.

## Acesso à um repositório específico

Voltando ao assunto que me impressionou: acesso para encontrar *apenas* um repositório.

No trabalho eu uso o mesmo perfil do GitHub que uso para os meus projetos pessoais. Por causa disso, eu fico 3x mais atenta a quais serviços tem acesso aos dados do meu perfil.

O fato de poder controlar tão detalhadamente quais repositórios o serviço tem acesso me impressionou pois normalmente não é isso que acontece.

Por exemplo, o Heroku consegue listar todos os repositórios da minha conta, para ser justa, ele não tem acesso as organizações a não ser que eu peça isso, mas ainda assim, o Netlify dá um passo além.

## Domínio

Pra finalizar eu comprei um domínio novo no Namecheap e configurei ele no GitHub.

É pelo namecheap que eu compro e gerencio todos meus domínios, eu acho ele fácil de usar e configurar. Por exemplo, o GitFichas tem dois domínios principais:

- [https://gitfichas.com](https://gitfichas.com) que mostra a página em português;
- [https://gitstudycards.com](http://gitstudycards.com) que redireciona para a página em inglês do projeto.

Esse redirecionamento eu faço direto pelo site do Namecheap sem precisar de mais nada. É muito prático.

## Anúncio oficial

Com o domínio no ar e as primeiras fichas publicadas eu fiz o que eu mais gosto de fazer e [escrevi um artigo no meu blog para contar que o projeto nasceu](https://jtemporal.com/conheca-o-gitfichas/). Basicamente pra contar a proposta do projeto, mostrar a carinha de uma ficha e deixar quem acompanha o meu trabalho a par da novidade.