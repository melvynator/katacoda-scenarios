In this step, you will learn how to create a deployment in the Elastic Cloud for APM purposes as well as how to configure a demo application to collect and send APM data to your deployment.

<iframe style="width: 700px;height: 400px;" src="https://www.youtube.com/embed/a4_o9QetfWA" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Let's try it out!

You can load the Jenkins' dashboard via the following URL https://[[HOST_SUBDOMAIN]]-8080-[[KATACODA_HOST]].environments.katacoda.com/

1. Download the JAR:
`wget -O elastic-apm-agent-1.16.0.jar https://search.maven.org/remotecontent?filepath=co/elastic/apm/elastic-apm-agent/1.16.0/elastic-apm-agent-1.16.0.jar`{{execute}}

2. Download the app using git:
`git clone https://github.com/elastic/opbeans-java`{{execute}}

3. Create the build:
`
cd opbeans-java/opbeans/
mvn package
`{{execute}}

4. Start the agent
`java -javaagent:elastic-apm-agent-1.16.0.jar -Delastic.apm.service_name=opbeans-java -Delastic.apm.server_urls=https://5d685bf6d4d3494d8afae70f85eb7a93.apm.europe-west1.gcp.cloud.es.io:443 -Delastic.apm.secret_token=fNHQlOr0Z7uZPgZ3N8 -jar my-application.jar`{{copy}}

