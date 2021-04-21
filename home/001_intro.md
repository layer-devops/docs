# Introduction

LayerCI is a cloud-hosted DevOps platform that creates newly provisioned VMs for every code change extremely efficiently.
We monitor which files are used by which steps, and automatically skip any repetitive setup work.

## What are LayerCI VMs useful for?

Many DevOps tasks can be solved in seconds if you can create VMs quickly:

- **Creating staging environments**: it's easy to create staging environments as needed, and they can be spun up in seconds because the new VM contains a copy of the database that was set up in the last run.
- **Running End-to-End (E2E) tests**: E2E tests can be run in parallel quickly and easily if you can duplicate the entire test VM, saving valuable time for yourself and your developers. 
- **Building and pushing container images**: build and push your container images effortlessly with the same version of Docker you use in production.

## Is it hard to get started?

We integrate seamlessly with GitHub and GitLab. Getting a "hello world" VM created only takes about five minutes:

1. Install LayerCI onto a repository of your choice.
2. Create files named 'Layerfile' anywhere in your repository.
3. Push your commit, we'll immediately start building its Layerfiles in parallel.

You don't have to replace your entire CI system.
When you install LayerCI, it'll show up as an extra status beside traditional CIs like CircleCI or GitLab CI in the pull request page.


<a class="btn btn-lg btn-success" href="/onboarding">Try an interactive tutorial</a>

## How is LayerCI different from a traditional cloud provider?

LayerCI is built as a DevOps platform, and not for hosting production code.

Our VMs use memory snapshotting to work like Docker containers. They're faster and more developer-friendly than a traditional VM.

We can create dozens of VMs per branch, because we automatically hibernate them when they're not in use.

Because the configuration looks like a Dockerfile, you don't need to configure a complicated build process either.

You simply write a `Layerfile` (similar to a `Dockerfile`) and we'll use memory snapshots to automatically reuse the work done the last time the pipeline ran.

## How is LayerCI different from a traditional CI provider?

Traditional CI systems will only allow you to build artifacts and run unit tests - you can't easily create a fresh copy of your entire backend to run meaningful tests.

LayerCI is meant to be as simple as a traditional "docker-build" CI system, but as powerful as provisioning a new VM from scratch.

## How expensive is it?

For personal projects, free.

For startups and larger teams, we have two offerings: a flat fee of $5/developer/month or $35/developer/month (when billed annually) to keep incentives aligned.

For enterprise organizations, we are happy to provide a quote upon request. More information on the features of each offering can be found on our [pricing page](https://layerci.com/pricing).

We don't want to charge per build minute because that would incentivize us to slow things down for profit. 
