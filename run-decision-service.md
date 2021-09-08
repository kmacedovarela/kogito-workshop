# Run the Decision Service in Cloud

## Deploy the decision in OpenShift

1. **Login** in your OCP cluster and **create** a new project

   ~~~
   oc new-project decision-lab01
   ~~~

2. **Build** the _Quarkus Uberjar_

   ~~~
   mvn clean package -Dquarkus.package.type=uber-jar -DskipTests
   ~~~

3. **Create** a new image from binaries:

   ~~~
   oc new-build registry.access.redhat.com/openjdk/openjdk-11-rhel7:latest --binary --name=discount -l app=discount
   oc start-build discount --from-file target/*-runner.jar --follow
   ~~~

   Optionally, check that the _ImageStreams_ are correctly created:

   ~~~
   $ oc get is
   NAME               IMAGE REPOSITORY                                                                                                        TAGS     UPDATED
   discount           default-route-openshift-image-registry.apps.cluster-972c.972c.sandbox1438.opentlc.com/decision-lab01/discount           latest   13 seconds ago
   openjdk-11-rhel7   default-route-openshift-image-registry.apps.cluster-972c.972c.sandbox1438.opentlc.com/decision-lab01/openjdk-11-rhel7   latest   About a minute ago
   ~~~

4. **Create** the application:

   ~~~
   oc new-app --name discount discount
   ~~~

5. **Expose** the application (create a route)

   ~~~
   oc expose svc/discount
   ~~~

## Probe the decision

1. **Retrieve** the service URL:

   ~~~
   oc get route discount -o jsonpath='{.spec.host}'
   ~~~

2. **Open** the file `dmn-test.http` and **update** the `URL` variable with the result of the previous command.

3. **Trigger** the REST call through **Send Request** link (right above the `POST` line)

4. **Check** that the service reply

> **Alternatively:** through the `curl` command:
> 
> ~~~
> export URL=<your url>
> curl --request POST \
>   --url $URL \
>   --header 'accept: application/json' \
>   --header 'content-type: application/json' \
>   --header 'user-agent: vscode-restclient' \
>   --data '{"Cart": [{"category": "electronics","price": 80},{"category": "food","price": 20}]}'
> ~~~

## Clean up your environment

Optionally, if you want to remove everything:

~~~
oc delete all -l app=discount
~~~
