# OpenControl: Questions

## What?

What license is this under?

> The code portions are all licensed under Apache 2.0, except what has been contributed
directly by the US Government, which is in the public domain. All written content
has been licensed as Creative Commons Zero.

What regulations can I use this for?

> The principles behind OpenControl can be applied to any regulatory environment,
or in fact any operational environment with running systems and software. Currently,
the community repositories include FedRAMP low and moderate definitions using the
NIST 800-53 certification, as well as a newly defined "LATO" authorization. 

What about PCI?

What about SOX?

What about HIPAA?

What about ICD-503?

What about FedRAMP?

## Why?

Why would I want this?


## How?

Why didn't you use XSLT?

Why didn't you use OpenSCAP?

Why did you use Concourse?

> There are a lot of great continuous integration tools out there, including Jenkins,
Travis, Bamboo, Wercker, and more. OpenControl pipelines can be defined using
any CI tool. We felt that the "dependency-injection" style of job and resource
declaration in Concourse made it a good fit for the semantics of OpenControl.


## Who?

Who came up with this mess?

> The ideas of continuous authorization have been around for a long time. The term
'OpenControl' was coined by Joshua McKenty, and first used in [a keynote presentation
at All Things Open 2015](https://slideshare.net/joshuamckenty/opencontrol) in Raleigh, North Carolina.
The presentation includes some history, and explicit thanks to key originators at
both 18F and Pivotal, as well as the creators of Cloud Audit. Special thanks goes
to Diego Lapiduz and Noah Kunin.
