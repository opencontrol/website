# OpenControl: Schema

The OpenControl pipeline combines four types of yaml files:
standards, certifications, components, and systems.

## Standards Schema

Standards (such as NIST 800-53) provide a list of controls that can be
referenced in a certification, and include descriptions that may or may not
be included in the final documentation.

```yaml
# nist-800-53.yaml
---
standards:
  C-2:
    name: User Access
    description: There is an affordance for managing access by...
```

You can find the [complete file on github.](https://github.com/opencontrol/standards/federal/nist-800-53.yaml)

## Certification Schema

Certifications (such as FedRAMP Low) provide the scaffolding for a system's
authorization. They include a list of required controls.

Here is a fragment of the FedRAMP certification YAML, showing the schema.

```yaml
# FedRAMP-low.yaml
---
standards:
  nist-800-53:
    C-2: ~
    C-3: ~
```

You can find the [complete file on github.](https://github.com/opencontrol/certifications/federal/FedRAMP-low.yaml)


## Component Schema

Here is an example component schema:

```yaml
# CloudFoundry-UAA.yaml
---
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

You can find the [complete file on github.](https://github.com/cloudfoundry-community/opencontrol/component/CloudFoundry-UAA.yaml)


## System Schema

The System YAML file is the only OpenControl schema that is explicitly defined as
a spruce template. It combines the Standards, Certifications, and Components to
produce a complete System Security Plan.

This example is for an installation of Pivotal Cloud Foundry running on top of
Amazon Web Services, and includes a number of controls satisfied thru additional
software components (aka compensating controls).

```
# pcf-on-aws-fedramp.yaml
---


```

You can find the [complete file on github.](https://github.com/opencontrol/example-pipelines/pcf-on-aws-fedramp.yaml)
