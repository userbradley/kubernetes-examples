![Codefresh build status]( https://g.codefresh.io/api/badges/pipeline/breadnet/Static%20sites%2FKubernetes%20Site?type=cf-1&key=eyJhbGciOiJIUzI1NiJ9.NjA2NDk2ODIzMDk5OTgxZTRjODFmMTNi.5gYRawM6ODqOOVHDq1eDn1cma2Df2_jcXcQ4oAsb9wM)
[![wakatime](https://wakatime.com/badge/user/befd4d51-df71-4caa-90ba-09a83c0524b0/project/d8d255aa-cd90-4619-97dc-e0fd99677606.svg)](https://wakatime.com/badge/user/befd4d51-df71-4caa-90ba-09a83c0524b0/project/d8d255aa-cd90-4619-97dc-e0fd99677606)

## What is this

This site contains a boat load of manifest files that I have written (and some ripped from the internet) as well as generated ones

## Why do this

I am studying for my [CKA](https://documentation.breadnet.co.uk/certifications/cka/) and want to also have a load of examples to hand when ever I need

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