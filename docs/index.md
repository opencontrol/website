# ![OpenControl Logo](img/oclogo.png)

# A YAML-Powered Antidote To Bureaucracy #

## It's a powerfully simple idea.

To improve the quality of our software development, we use continuous integration.
To improve the reliability of our deployment, we use continuous delivery.
To improve the security of our systems, we can use continuous authorization.

Simply put, the tools that we use to develop and operate software, should also be
used to generate and validate assessment and authorization packages.

Every commit runs the tests.
Every passing build, updates the system security plan.
Every deployment includes updates to continuous monitoring.

> Software as Code.

> Tests as Code.

> Infrastructure as Code.

> Compliance as Code.

## It's a schema.

By adopting a standard approach to documenting "controls" (whether Technical, Operational, or Management) we can rapidly build a community of vendors and operators. You can see [the current (and evolving) OpenControl schema here.](schema)

## It's a set of tools and best practices.

Right now we're excited about:

 * [Concourse.ci](http://concourse.ci) (see an example at [https://dragon.somegood.org](https://dragon.somegood.org))
 * GitBook (see how the 18F have used this to produce the [System Security Plan for Cloud.Gov](https://masonry-gitbook.cloud.gov/index.html))

There are more details about how to use this set of tools to [build a continuous authorization pipeline](pipelines.md).

## It's a community.

This community includes vendors that provide documentation of controls in a standard
schema, government agencies and other regulators that document certifications in
another schema, and operators who use the OpenControl process to authorize their
systems.

You can see the [full list of current members here.](members)
