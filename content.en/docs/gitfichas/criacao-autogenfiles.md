---
bookCollapseSection: false
weight: 22
title: "Creating Autogenfiles"
---

One nice day like many others, after creating quite a few repeated files I asked myself (and twitter):

{{< tweet user="jesstemporal" id="1418894698589138948" >}}

This test became [autogenfiles](http://jtemporal.com/autogenfiles?utm_source=devdiaries).

## Where did the necessity rise from

The [portfólio theme](https://lenpaul.github.io/portfolio-jekyll-theme/) I chose has a particularity: the way you list projects isn't through a collection of posts, and by a [Jekyll Collection](https://jekyllrb.com/docs/collections/), by the way this is the same structure I use for listing Brazilians projects to contribute to for the annual hacktoberfest list I curate every year.

Because of such particularity and because of how Jekyll works, every time I created a new card, I'd need to create a new file inside of 3 different folders:

- `projects`
- `_projects`
- `_posts`

I confess to not understand the inner works of how the folders connected to the listing, but building the website locally I identified the need for creating all the files.

## Configuring and using Autogenfiles on GitFichas

[Autogenfiles](http://jtemporal.com/autogenfiles/?utm_source=devdiaries) is made to be simple.

### Folder structure and variables file

You need a templates folder to create the templates in, and that folder must follow the same folder structure of your project. In this case, I needed 3 folders and each folder contained a file. The template folder structure ended up looking like this:

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

After the templates structure I also needed a file called `variables.yml` to take note of the values to be filled on each template. Note it is in Portuguese since up to this point the project had no intention of being localized to English:

```yaml
[variables]
ficha = 018
date = 2021-09-08
desc = git clone url
alt = O comando git clone ... na cloud.
```

### Templates

The templates so far were supposed to be as simple as possible. I copied them below:

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

### Creating all files with only just one command

After creating all of this structure I just needed to run the command `autogenfiles` that the files were “automagically” created without requiring me to lift a finger - other than to type the command that is.

So for each new card, instead of 3 very similar files I ended up editing only one reducing the chance for mistakes.

PS.: maybe I will write about implementing [autogenfiles](http://jtemporal.com/autogenfiles?utm_source=devdiaries), but for now you can [take a sneak peak at the code by clicking here](https://github.com/jtemporal/autogenfiles?utm_source=devdiaries).
