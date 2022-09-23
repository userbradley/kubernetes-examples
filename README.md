# Kubernetes Manifests documentation

[![Codefresh build status]( https://g.codefresh.io/api/badges/pipeline/breadnet/Static%20sites%2FKubernetes%20Site?type=cf-2)]( https://g.codefresh.io/public/accounts/breadnet/pipelines/new/632df06584b536311cef3e1b)
[![wakatime](https://wakatime.com/badge/user/befd4d51-df71-4caa-90ba-09a83c0524b0/project/6be1f56d-02cb-4305-8a66-6e36f53a82a9.svg)](https://wakatime.com/badge/user/befd4d51-df71-4caa-90ba-09a83c0524b0/project/6be1f56d-02cb-4305-8a66-6e36f53a82a9)


## What is this

This is a public site I run to document the Kubernetes manifest files as well as all the possible values for them.

## Why this exists

I had trouble when learning Kubernetes with all the possibilities for the files, so I made this site (Will always be in Development)
for my self and peers, so we have a quick reference sheet.

## Where can I access it

[kubernetes.breadnet.co.uk](https://kubernetes.breadnet.co.uk) 

> :warning: The site is not active yet!

---

# Developing the site

## Adding pages

I encourage people to add pages. Please copy and paste from the `docs/template.md` and then find and replace parts etc. etc.

Once done, open a PR and I will review etc. etc.

## Building locally

### Pre-reqs:

1. mkdocs
2. pip

### Building site

git clone the repo

`mkdocs serve`

open [localhost:8000](http://localhost:8000)