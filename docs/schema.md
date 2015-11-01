# OpenControl: Schema

The OpenControl pipeline combines three types of yaml files:
certifications, components, and systems.

## Certification Schema



## Component Schema

Here is an example component schema:

```
name: User Account and Authentication (UAA) Server
references:
- name: User Account and Authentication (UAA) Server
  url: http://docs.pivotal.io/pivotalcf/concepts/architecture/uaa.html
governors:
- name: Cloud Foundry Roles
  url: https://cf-p1-docs-prod.cfapps.io/pivotalcf/concepts/roles.html
satisfies:
  NIST-800-53:
    AC-2: Cloud Foundry accounts are managed through the User Account and Authentication (UAA) Server.
```

## System Schema
