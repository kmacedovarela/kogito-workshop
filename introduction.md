# 1. Introduction

This is a series of guided exercises that will allow you to experiment the authoring of decisions and business rules using Kogito. You will work with decision authoring with Kogito tooling, along with the packaging and consumption of the decisions in the Kogito engine that is supported in Red Hat Process Automation 7.11x.

Here is an overview of the guided exercises:

* Local development environment setup: get your development environment ready to go with VSCode and GraalVM.
* Local environment setup for Kafka: use docker to quickly start a Kafka environment in your local environment. The Kafka broker will be used in the event-driven lab. 
* Getting start with Kogito applications: create a decision application using the Kogito maven archetype, try out the business modeling tools in VSCode, experience hot reload of business assets during development and test your application using JVM and native compilation.
* Event-driven decision aplications: create a project from scratch and understand all that is needed to have your decisions reacting to events and publishing the results back through events and using the CloudEvents specification.

Let's get started by preparing your development environment.