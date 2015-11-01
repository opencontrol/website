# OpenControl Pipelines

Continuous Authorization pipelines can be constructed using the
open source [Concourse.ci](https://Concourse.ci) tool.
There is a running example of this at [https://dragon.somegood.org](https://dragon.somegood.org).
![OpenControl Pipeline Screenshot](img/screenshot.png)

The [example pipeline is available on github.](https://github.com/opencontrol/example-pipelines)

The notional architecture of the OpenControl pipeline is below.
![Pipeline Architecture](img/OpenControl%20Architecture.png)

## Key Tools

OpenControl systems, components and authorizations are defined using YAML. So
much of the pipeline is simply merging of various YAML files. This is performed
using a tool called ["Spruce"](https://blog.starkandwayne.com/2015/10/08/introducing-spruce-a-more-intuitive-spiff).

Spruce merges yaml files from left to right, so the template for the system
authorization will always be listed first. Files of each of the required schemas
will come next, and finally an "override" file for system-specific controls
will be merged last.

Once a complete system-security-plan (SSP) YAML has been generated, it can be
transformed into a variety of formats. For human-readable documentation, the YAML
should be converted to Markdown, and then passed into GitBook. GitBook can output
HTML, PDF, or various ePUB formats.

Producing configuration for your continuous monitoring tools can be generated directly
from the SSP YAML, using various python libraries. 
