[![Codefresh build status]( https://g.codefresh.io/api/badges/pipeline/breadnet/Static%20sites%2FKubernetes%20Site?type=cf-2)]( https://g.codefresh.io/public/accounts/breadnet/pipelines/new/632df06584b536311cef3e1b)
[![wakatime](https://wakatime.com/badge/user/befd4d51-df71-4caa-90ba-09a83c0524b0/project/6be1f56d-02cb-4305-8a66-6e36f53a82a9.svg)](https://wakatime.com/badge/user/befd4d51-df71-4caa-90ba-09a83c0524b0/project/6be1f56d-02cb-4305-8a66-6e36f53a82a9)


## What is this

This site contains a boat load of manifest files that I have written (and some ripped from the internet) as well as generated ones

## Why do this

I am string for my [CKA](https://documentation.breadnet.co.uk/certifications/cka/) and want to also have a load of examples to hand when ever I need

## How this site works

This site is available at [kubernetes.breadnet.co.uk](https://kubernetes.breadnet.co.uk)

Where it is split up on the left nav bar by `kind` in a sense

## Contributing

You will need to fork the repo to your own account

Once you have made your changes, please open a Pull Request on to **main** 

### Pre requisites

1. [Mkdocs installed](https://www.mkdocs.org/user-guide/installation/)
2. [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)

### Running the site locally

```shell
mkdocs serve -w .
```

We need to use the `-w .` flag as the manifest files exist outside the `docs` directory

### Write your documentation

Try and follow some basic formatting like the below

#### Tile of pages

They should be represented like the below

```markdown
---
title: Bradley is cool
---

# Bradley is cool
```

#### Including Manifest files

As it stands, all manifest files _should_ go in to a folder called `manifests`

Try and split them up by `kind`

Then include them in your file with

```markdown
;--8<-- "manifests/<kind>/file.yaml"
```

_note_ : Remove the `;` when doing it, the `;` was just added to [Escape Snippet notation](https://facelessuser.github.io/pymdown-extensions/extensions/snippets/#escaping-snippets-notation)