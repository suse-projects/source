# SUSE Projects

This is the source repo for the [SUSE Projects](https://suse-projects.github.io) page.

This page is a compilation of open source software that SUSE has contributed to in any capacity, either as the inventor or as a collaborator.

## Contributing

If you would like to submit a project for inclusion, please fork the repository, create a branch, make changes as outlined below, and submit a pull request.

### Adding A Project

To add a project, please create a YAML file in `data/projects/{category}` with the name of your project, normalized in lowercase, with `-` in place of whitespace.

For example, a project named "Rancher Desktop" in the Development category would be saved in `data/projects/development/rancher-desktop.yaml`.

```yaml
---
name: Rancher Desktop
repository: https://github.com/rancher-sandbox/rd
twitter:
website:
description: Kubernetes on your desktop.
```

The project must have, at the minimum, the following fields:

- name
- repository

For it to be a Featured project it also needs the description field and a logo (see below). If it does not have a website, the repository URL will be used instead. If it does not have a Twitter handle, it will be dynamically excluded from the card if the project is Featured.

If the project does not have a value for a key, it is not necessary to include the key for any reason other than clarity. Missing keys and keys with no value are ignored.

### Project Logos

If your project has a logo, please upload it in SVG (preferred) or PNG to `static/logos` and name it the same as the project's YAML file (e.g. lowercase, with space replaced by `-`).

A logo is not required, but only projects with logos can be Featured.

### Featuring a Project

If the project is to be featured, add it to the `featured` key in `config.yaml`. The number of featured projects is set in the `featuredLimit` variable in `config.yaml`. Only the first projects up to that limit will appear as featured projects in the cards at the top of the page.

Featured projects must have a logo (see above).

### Project Categories

Please place your project in one of the existing category directories. If it fits into more than one category, place it in the one where you think it fits **the best**. Categories should be broad and inclusive. For example, Operations is better than Package Managers because a package manager is part of an operations workflow.

Try to fit entries into a noun for what the software enables. Kubewarden enables Security for Kubernetes, so although it could go into Kubernetes, it fits better in Security.

- Kubernetes
- Security
- Storage
- Operations
- Development
- Infrastructure

If your project doesn't fit into one of these, please create a new directory and explain your reasons for the new category in your pull request.

## Disabling a Project

Any project can be disabled by adding `disabled: true` to the YAML. This allows projects to be temporarily removed without having to delete their content entirely.

## Deployment

Once a PR is merged, the site is built by GitHub Actions and then pushed to the [organizational repo](https://github.com/suse-projects.github.io). From there GitHub publishes it to [the final destination](https://suse-projects.github.io).
