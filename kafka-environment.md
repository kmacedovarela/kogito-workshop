# 2.  Kafka Environment

Kafka is an open-source even streaming platform, and currently, one of the most popular tools. In event-driven architectures, the Kafka `topics` are used as the communication layer in between the services. Each service can now be considered a `consumer`or a `producer`, in other words, each service can publish or consume events to/from the `topics`.  

Red Hat supports the integration between RHPAM and AMQ Streams (Kafka). To follow the labs, you should have an accessible Kafka server. The Kogito Engine (decision engine) will communicate with the topics that we will create in the Kafka server. When working with event-driven applications, you will have decoupled decision services that can react to certain events and publish the result of the decision back in form of events. 

In this step, we will set up a Kafka environment in your local environment using Docker. If you already have a local Kafka broker and you want to use it, that is totally fine!

**IMPORTANT:** When using AMQ Streams (Kafka) in OpenShift, a secure communication is required in between the client applications and the Kafka broker. Extra configurations in the client applications like `kafka.sasl.mechanism`, `kafka.security.protocol`, `kafka.sasl.jaas.config` and `kafka.sasl.login.callback.handler.class` are not needed when TLS communication is not enabled.

## 2.1. Pre requisites

* Docker 

## 2.2. Setting up a local Kafka environment using Docker

1. In your local machine, access the enablement's base folder:

   ```
   $ cd ~/enablement
   ```

2. Clone the repository containing the docker files we need:

   ```
   $ git clone https://github.com/hguerrero/amq-examples
   ```

   The docker-compose file available in this quickstart should bootstrap everything you need to have your Strimzi up and running: Zookeeper, Kafka server v2.5.0, Apicurio Registry and a Kafka Bridge. 

3. Access the `amq-examples/strimzi-all-in-one/` folder:

   ```
   $ cd amq-examples/strimzi-all-in-one/
   ```

4. Start the Kafka environment:

   ```
   docker compose up 
   ```

The necessary images will be downloaded and the containers should be up and ready for you to use in a couple of minutes. In order to stop the environment, you can hit `ctrl+c`. Whenever you want to start it, just navigate to the directory `~/enablement/amq-examples/strimzi-all-in-one/` and run the `docker compose up` command.

### Next steps

At this point you should have VSCode with the Business Automation extension and Kafka on your environment. Let's get started an create our decision service!