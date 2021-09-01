# 1. Introduction

## 1.1. Background

The [KIE Community](https://kie.org/) is a home for leading Open Source projects that play a role in delivering solutions around Process Automation, Decision Management and Artificial Intelligence (KIE stands for Knowledge Is Everything).

![Kogito]({%  image_path/logo.png %}){:width="400px"}

[Kogito](https://kogito.kie.org/) is a recent initiative under the KIE umbrella to leverage the battle-tested project **Drools, jBPM, and OptaPlanner** into a **Cloud Native Environment**.

It is designed from ground up to run at scale on cloud infrastructure. If you think about business automation think about the cloud as this is where your business logic lives these days. By taking advantage of the latest technologies ([Quarkus](https://quarkus.io/), [KNative](https://knative.dev/), etc.), you get amazingly fast boot times and instant scaling on orchestration platforms like [OpenShift][ocp].

[Red Hat Process Automation Manager][rhpam] and [Red Hat Decision Manager][rhdm] are the products built on top of KIE projects and offers the enterprise grade support.

[In version 7.11.x][announce], Red Hat introduced a first subset of **Kogito capabilities** to enable the decision services: **DMN, Rules, Event Driven Decisions**.

[rhpam]:https://www.redhat.com/en/technologies/jboss-middleware/process-automation-manager
[rhdm]:https://www.redhat.com/en/technologies/jboss-middleware/decision-manager
[announce]:https://www.redhat.com/en/about/press-releases/red-hat-rewrites-business-automation-playbook-end-end-kubernetes-native-decision-management-capabilities
[ocp]:https://www.redhat.com/en/technologies/cloud-computing/openshift

## 1.2. Practising Kogito

This is **a series of guided exercises** that will allow you to experiment the authoring of decisions and business rules using Kogito. You will work with decision authoring with _Kogito tooling_, along with the packaging and consumption of the decisions in the _Kogito engine_ that is supported in Red Hat Process Automation 7.11.x.

Here is an overview of the guided exercises:

- **Local development environment set-up**: get your development environment ready to go with VSCode and GraalVM.
- **Local environment set-up for Kafka**: use docker to quickly start a Kafka environment in your local environment. The Kafka broker will be used in the event-driven lab. 
- **Getting start with Kogito applications**: create a decision application using the Kogito Maven archetype, try out the business modeling tools in VSCode, experience hot reload of business assets during development and test your application using JVM and native compilation.
- **Event-driven decision applications**: create a project from scratch and understand all that is needed to have your decisions reacting to events and publishing the results back through events and using the CloudEvents specification.

Let's get started by preparing your development environment.