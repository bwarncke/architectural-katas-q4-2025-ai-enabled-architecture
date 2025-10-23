# Infrastructure Hosting

## Context and Problem Statement
We need to run the application and host the corresponding data somewhere.
Should we use a cloud provider and if so, which one?

## Considered Options

* Hosting the applications in an outsourced data center using a managed service provider
* Hosting in AWS
* Hosting in Azure

## Decision Outcome

Chosen option: "Hosting in AWS", because the startup costs for running in the public cloud are lower compared with typical 3 year leasing and data center build out costs 
as well as the availability of platform as a service for several key needs. This also translates to getting up and running faster. 
Between the cloud options, we selected AWS versus Azure for the highly opinionated reason that our whole team would be 
happy if we never have to use Azure again in our careers. We could cite reasons for this at length but the gist of it is that in our
experience AWS is a far superior provider, having used both extensively. While this may not seem like a sound reason, 
sometimes it is important to just document that an option was chosen for subjective reasons versus objective.


### Consequences

* Good, because we gain speed on building out the infrastructure.
* Good, because we have workable options for infrastructure as code which cover nearly everything we would use, versus having to cobble together various tools for doing the same in our DC
* Good, because we gain capabilities which reduce (not eliminate) our own hiring and team complexity, such as managed databases and security options
* Good, because we gain disaster recovery at a greatly reduced cost versus the related options when using our own DC or managed colo.
* Bad, because the capitalization model with the cloud is less favorable (if it is even capitalized,
  depending on where we operate and whether GAAP is in use)
* Bad, to a small degree, because we almost certainly introduce vendor lock-in by using tech which we can't take elsewhere as-is

### Nota Bene
* We are not considering or describing a plan for managing costs during the build-out period where we are maintaining the existing system and infra while also paying for the new system and infra. This is out of scope due to time constraints but would be part of a more detailed architecture plan if the initial plan is approved