# SUSE Projects

This is the source repo for the [SUSE Projects](https://suse-projects.github.io) page.

## Adding A Project

To add a project, please create a YAML file in `data/projects/{category}` with the name of your project, normalized in lowercase, with `-` in place of whitespace.

For example, a project named "SLE BCI" in the Development category would be saved in `data/projects/development/sle-bci.yaml`.

```yaml
---
name: Rancher
repository: https://github.com/rancher
twitter: https://twitter.com/Rancher_Labs
website: https://rancher.com
description: Deploy and manage Kubernetes anywhere.
```

The project must have, at the minimum, the following fields:

- name
- repository

For it to be a featured project it also needs the description field. If it does not have a website or twitter handle, these will be dynamically excluded.

## Featured Projects

If the project is to be featured, add it to the `featured` key in `config.yaml`. The number of featured projects is set in the `featuredLimit` variable in `config.yaml`. Only the first projects up to that limit will appear as featured projects in the cards at the top of the page.

Featured projects must have a logo added to `static/logos` as a SVG (preferred) or PNG (alternate) file of the same name as the project's YAML file (e.g. lowercase, with space replaced by `-`). These will be picked up automatically and shown on the page.

## Categories

Please place your project in one of the existing categories:

- Kubernetes
- Security
- Storage
- Operations
- Development
- Infrastructure

If your project doesn't fit into one of these, please create a new directory and explain your reasons for the new category in your issue or pull request.
