---
---

# OpenControl: High Level Questions

## What?

What license is this under?

> The code portions are all licensed under Apache 2.0, except what has been contributed
directly by the US Government, which is in the public domain within the US. Internationally, the US Government licenses its code under [Creative Commons Zero 1.0](https://github.com/opencontrol/compliance-masonry/blob/master/LICENSE.md). All written content
has been licensed as [Creative Commons Zero](https://creativecommons.org/publicdomain/zero/1.0/).

What regulations can I use this for?

> The principles behind OpenControl can be applied to any regulatory environment,
or in fact any operational environment with running systems and software. Currently,
the community repositories include FedRAMP Low and Moderate definitions using the
NIST 800-53 certification, as well as a newly defined [Lightweight Authority to Operate](https://gsablogs.gsa.gov/innovation/2014/12/10/it-security-security-in-an-agile-development-cloud-world-by-kurt-garbars/) (LATO) NIST 800-53 baseline from the [General Services Administration](http://gsa.gov) (GSA).

What about PCI?

> [We've got it!](https://github.com/opencontrol/compliance-masonry/blob/6c9a3ff81710dedb816ccb7d9edd1a50e84ce015/fixtures/standards/PCI-DSS-MAY-2015.yaml)



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



## Who?

Who came up with this concept?

> The ideas of continuous authorization have been around for a long time. The term
'OpenControl' was coined by Joshua McKenty, and first used in [a keynote presentation
at All Things Open 2015](https://speakerdeck.com/joshuamckenty/all-things-open-opencontrol) in Raleigh, North Carolina.
The presentation includes some history, and explicit thanks to key originators at
both 18F and Pivotal, as well as the creators of Cloud Audit. Special thanks goes
to Diego Lapiduz and Noah Kunin.

# OpenControl: Community Questions

I have two clients each with an ATO and tus an SSP. It's reasonably straightforward to pull each family of controls into separate .md files in GitHub (well, I'm using GitLab now). The next step is to convert the controls into OC YAML Components, but this is not 1:1. Does a suggested mapping exist?

I understand that each site will have its differences, but there is likely to be a fair amount of commonality. If the process can be reduced to a script that handles 90% of the controls and a process for massaging the 20% that didn't "fit" correctly, I believe this may help facilitate adoption.

>Components will likely correspond to components of your software stack, such as the underlying infrastructure, the web framework, the database, etc. We recommend organizing this way, rather than by component family.
Therefore, the mapping exists from those components to each of the relevant controls, rather than the other way around. That being said, given a list of components, you could certainly produce the reverse. For example, the Amazon S3 component takes care of controls X, Y, and Z. You could also potentially make components that correspond to certain general types of applications, such as a static site or a traditional three-tier architecture. Perhaps in your cases, these could get even more specific.

Only a few (<20) controls are specified in the AWS opencontrols git:
https://github.com/opencontrol/aws-compliance

For FedRAMP-high we need all 421 controls implemented per the FedRAMP spreadsheet:
https://www.fedramp.gov/assets/resources/documents/FedRAMP_Security_Controls_Baseline.xlsx

Is it possible to write a script to auto-populate the AWS opencontrol files with the appropriate controls from the FedRAMP-high spreadsheet?

>A couple of clarifications:

> - The FedRAMP baselines would be represented as an [OpenControl Certification](https://github.com/opencontrol/schemas#certifications).
> - The AWS implementations of those controls would be represented as a set of [OpenControl Components](https://github.com/opencontrol/schemas#components), as seen in [that repository](https://github.com/opencontrol/aws-compliance).

> There used to be a repository for the former, but it was deleted since it wasn't being maintained. I think it would be relatively straightforward to write a script to create OpenControl Certification YAML files from the spreadsheet you linked above. See also: using them from OSCAL.

> - [FedRAMP baselines in OSCAL](https://github.com/usnistgov/OSCAL/tree/master/content/fedramp.gov)
> - [Using OSCAL with Compliance Masonry](https://github.com/opencontrol/compliance-masonry/issues/343)
> - Re: AWS control implementations, see [opencontrol/aws-compliance#5](https://github.com/opencontrol/aws-compliance/issues/5).