In this step, you will learn how to create a deployment in the Elastic Cloud for APM purposes as well as how to configure a demo application to collect and send APM data to your deployment.

## Let's try it out!

1. Download the app using git:
`git clone https://github.com/elastic/opbeans-java`{{execute}}

2. Create the build:
`
cd opbeans-java/opbeans/
mvn package
`{{execute}}

3. Download the JAR:
`wget -O elastic-apm-agent-1.16.0.jar https://search.maven.org/remotecontent?filepath=co/elastic/apm/elastic-apm-agent/1.16.0/elastic-apm-agent-1.16.0.jar`{{execute}}

4. Start the agent
`java -javaagent:elastic-apm-agent-1.16.0.jar -Delastic.apm.service_name=opbeans-java -Delastic.apm.server_urls=<CLUSTER-URL> -Delastic.apm.secret_token=<PASSWORD> -jar ./target/opbeans-0.0.1-SNAPSHOT.jar`{{copy}}

5. You can load the app via the following URL https://[[HOST_SUBDOMAIN]]-8080-[[KATACODA_HOST]].environments.katacoda.com/
