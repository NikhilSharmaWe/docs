# Deployment

OpenFaaS can be deployed to a variety of container orchestrators such as Kubernetes, K3s, OpenShift, or to a single host with faasd.

!!! info "Kubernetes or faasd?"
    We recommend using Kubernetes or OpenShift when using OpenFaaS for work because it can scale well, and OpenFaaS Ltd can provide commercial support, should you need it. faasd is already being used in production by some companies, but you should make yourself aware of the tradeoffs. Users can move between either deployment option at a later date.

## OpenFaaS Community Edition (CE) for Kubernetes (Internal use, development and Proof of concept)

!!! warning "A foreword on security"
    Authentication is enabled by default with OpenFaaS, however you will also need to obtain a TLS certificate for your cluster if you are using OpenFaaS on the public Internet. Free certificates are available from LetsEncrypt.org.

There are three recommended ways to install OpenFaaS to a Kubernetes cluster:

* Using our CLI installer [arkade](https://arkade.dev/) - (recommended)
* With the Helm chart, Flux or ArgoCD (GitOps workflow)
* Or using the statically generated YAML files (not recommended)

Find out more about each option and how to deploy OpenFaaS to Kubernetes:

[Deploy to Kubernetes](/deployment/kubernetes/)

## OpenFaaS Pro/OpenFaaS for Enterprises (production, commercial use)

* [Deploy OpenFaaS Pro/for Enterprises](/deployment/pro)

See also:

* [Detailed comparison CE vs. Pro](https://docs.openfaas.com/openfaas-pro/introduction/)
* [View pricing](https://openfaas.com/pricing)

## faasd - Serverless for everyone else

faasd is OpenFaaS, reimagined without the complexity and cost of Kubernetes. It runs well on a single host with very modest requirements, and is largely API-compatible with OpenFaaS on Kubernetes. Under the hood it uses [containerd](https://containerd.io/) and [Container Networking Interface (CNI)](https://github.com/containernetworking/cni) along with the same core components from OpenFaaS CE.

When should you use faasd over OpenFaaS CE on Kubernetes?

* You're building automation/glue-code, web portals, cron jobs, bots, or webhook receivers.
* You want to be able to run your code locally, using containers.
* You want a way to do remote deployments over a REST API.
* You either don't have the bandwidth to manage or learn Kubernetes.
* You don't need planet scale.

You may also be interested in:

* Deploying to constrained IoT or edge devices
* Shrink-wrapping functions into a VM image to deploy for customers or clients.

[Deploy faasd](https://github.com/openfaas/faasd/)

## OpenShift

OpenShift is a variant of Kubernetes produced by RedHat.

You can deploy to OpenShift using our CLI installer <a href="https://arkade.dev/">arkade</a> or with the standard helm chart.

[Deploy to OpenShift](/deployment/openshift/)

