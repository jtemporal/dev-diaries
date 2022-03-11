---
bookCollapseSection: false
weight: 22
title: "Criação do autogenfiles"
---

Um belo dia, depois de criar alguns arquivos repetidos eu me perguntei:

{{< tweet user="jesstemporal" id="1418894698589138948" >}}

Tradução: *será se dá pra usar jinja para automatizar geração de arquivos markdown?* e aí eu decidi fazer um teste. Esse teste virou o [autogenfiles](http://jtemporal.com/autogenfiles/).

## De onde surgiu a necessidade

O [tema de portfólio](https://lenpaul.github.io/portfolio-jekyll-theme/) que eu escolhi tem uma particularidade: a listagem de projetos não é a coleção de artigos, e sim de um [Jekyll Collection](https://jekyllrb.com/docs/collections/), essa mesma estrutura é a que eu uso para listar projetos para o hacktoberfest na lista anual de projetos brasileiros.

Por causa da particularidade desse tema, e por causa de como o Jekyll funciona, toda vez que eu criava uma ficha nova, eu precisava criar um novo arquivo markdown dentro de três pastas:

- `projects`
- `_projects`
- `_posts`

Eu confesso não entender muito bem a relação das três pastas e a listagem, mas fazendo os testes localmente eu identifiquei a necessidade criar esses arquivos. 

## Configuração e uso no GitFichas

O [autogenfiles](http://jtemporal.com/autogenfiles/) é feito para ser simples.

### Estrutura de pastas e arquivo de variáveis

Você precisa de uma pasta de templates que vai armazenar os templates que você precisa com a mesma estrutura de pastas do seu projeto. Nesse caso, eu precisei de três pastas e cada pasta precisou de um arquivo, a estrutura ficou assim:

```
templates
├── _posts
│   └── {{ date }}-{{ ficha }}.md
├── _projects
│   └── {{ ficha }}.md
└── projects
    └── {{ ficha }}.md

3 directories, 3 files
```

 Além da estrutura dos templates, precisei de um arquivo chamado `variables.yml` para anotar os valores a serem preenchidos em cada template.

```yaml
[variables]
ficha = 018
date = 2021-09-08
desc = git clone url
alt = O comando git clone ... na cloud.
```

### Templates

Os templates até aqui eram o mais simples possível. A seguir você pode ver com o que eles se parecem.

```yaml
---
layout: post
title: '#{{ ficha }} {{ desc }}'
image: "/assets/img/projects/{{ ficha }}/thumbnail.jpg"
---

<img  alt="{{ alt }}" src="/assets/img/projects/{{ ficha }}/full.jpg">
```

```yaml
---
layout: post
title: '#{{ ficha }} {{ desc }}'
image: "/assets/img/projects/{{ ficha }}/thumbnail.jpg"
---

<img alt="{{ alt }}" src="/assets/img/projects/{{ ficha }}/full.jpg">
```

```yaml
---
layout: post
title: "#{{ ficha }}"
permalink: /{{ ficha }}
image: "/assets/img/projects/{{ ficha }}"
redirect_to:
  - https://gitfichas.com/projects/{{ ficha }}
---

Redirect for {{ ficha }}
```

### Criando todos arquivos com apenas um comando

Depois de criar essa estrutura, era só executar o comando `autogenfiles` que os arquivos foram “automaticamente” gerados sem eu precisar editar cada um deles.

Então para cada nova ficha, eu passei a editar apenas um arquivo reduzindo os meus erros.

PS.: pode ser que eu escreva sobre a implementação do [autogenfiles](http://jtemporal.com/autogenfiles/), mas se você quiser [espiar o código basta clicar aqui](https://github.com/jtemporal/autogenfiles).
