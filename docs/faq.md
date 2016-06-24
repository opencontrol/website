# OpenControl: Questions

<script async class="speakerdeck-embed" data-id="1b3d6494fb12408dbe8f1cfe65eca769" data-ratio="1.77777777777778" src="//speakerdeck.com/assets/embed.js"></script>

## What?

What license is this under?

> The code portions are all licensed under Apache 2.0, except what has been contributed
directly by the US Government, which is in the public domain within the US. Internationally, the US Government licenses its code under [Creative Commons Zero 1.0](https://github.com/opencontrol/compliance-masonry/blob/master/LICENSE.md). All written content
has been licensed as [Creative Commons Zero](https://creativecommons.org/publicdomain/zero/1.0/).

What regulations can I use this for?

> The principles behind OpenControl can be applied to any regulatory environment,
or in fact any operational environment with running systems and software. Currently,
the community repositories include FedRAMP Low and Moderate definitions using the
NIST 800-53 certification, as well as a newly defined [Lightweight Authority to Operate](https://gsablogs.gsa.gov/innovation/2014/12/10/it-security-security-in-an-agile-development-cloud-world-by-kurt-garbars/) (LATO) NIST 800-53 baseline from the [General Services Administration](http://gsa.gov (GSA)).

What about PCI?

> [We've got it!](https://github.com/opencontrol/compliance-masonry/blob/6c9a3ff81710dedb816ccb7d9edd1a50e84ce015/fixtures/standards/PCI-DSS-MAY-2015.yaml)

What about FedRAMP High?

> Coming soon.

What about HIPAA?

> Coming soon.

What about ICD-503?

> No current plans - join the project and contribute!

What about SOX?

> No current plans - join the project and contribute!

## Why?

Why would I want this?

> For organizations in highly regulated environments, filling out compliance documentation is a huge commitment of time, staff, and resources. OpenControl will be a set of tools that will finall allow compliance to be directly incorporated to a continuous integration and deployment framework.

## How?

Why did you use Concourse?

> There are a lot of great continuous integration tools out there, including Jenkins,
Travis, Bamboo, Wercker, and more. OpenControl pipelines can be defined using
any CI tool. We felt that the "dependency-injection" style of job and resource
declaration in Concourse made it a good fit for the semantics of OpenControl.

Why didn't you use OpenSCAP?

> The Security Content Automation Protocol (SCAP) is developed by the US Government to check for the presence of common vulnerabilities, or secure configurations on common technologies. OpenSCAP and OpenControl are extremely complementary - they are solving different problems. As the name implies, [OpenSCAP](https://github.com/OpenSCAP), a collection of open source SCAP tools provided by Red Hat, is about _automating_ whether or not technologies with SCAP profiles in fact possess the security claims or "benchmarks" provided by [NIST](https://web.nvd.nist.gov/view/ncp/repository) or have common vulnerabilities in [MITRE's database](https://cve.mitre.org/).
> 
> If your organization already uses SCAP, OpenSCAP may be a great solution to run those tests, and then output the results to [Compliance Masonry](https://github.com/opencontrol/compliance-masonry), an OpenControl tool. You use Compliance Masonry to map and automation of the _results_ of those tests to the actual compliance documentation, which was always the missing piece from SCAP based systems. SCAP systems still required humans to manually entire information into static documentation. Via Compliance Masonry, OpenControl is [agnostic as to the source of your test results](https://github.com/opencontrol/compliance-masonry#long-term-plan-diagram) and whether not any compliance control is in fact implemented. It maps those controls to tests, and also renders the final compliance documentation.
>
> Also of note is that the SCAP standard is [extremely verbose and complex XML](http://scap.nist.gov/schema/scap/1.2/scap-source-data-stream_1.2.xsd). Developers of net-new technologies have usually not written benchmarks in SCAP, and as a result, benchmarks significantly lag behind technological development. By using YAML and creating a more developer focused framework, we hope that secure baselines evolve more quickly in parallel with SCAP enabled enterprise benchmarks provided by NIST.

Why didn't you use XSLT?

> We do! Often `.xslt` files are used up-stream, and imported.

How do I get started using this?

> We need to write a "getting started" tutorial. As a quick bootstrap, use the
tutorial on the Concourse.ci website, and then checkout the example pipeline.

## Who?

Who came up with this mess?

> The ideas of continuous authorization have been around for a long time. The term
'OpenControl' was coined by Joshua McKenty, and first used in [a keynote presentation
at All Things Open 2015](https://speakerdeck.com/joshuamckenty/all-things-open-opencontrol) in Raleigh, North Carolina.
The presentation includes some history, and explicit thanks to key originators at
both 18F and Pivotal, as well as the creators of Cloud Audit. Special thanks goes
to Diego Lapiduz and Noah Kunin.
