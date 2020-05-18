In this step, you will learn how to create a deployment in the Elastic Cloud for APM purposes as well as how to configure a demo application to collect and send APM data to your deployment.

<iframe style="width: 700px;height: 400px;" src="https://www.youtube.com/embed/a4_o9QetfWA" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Let's try it out!

You can load the Jenkins' dashboard via the following URL https://[[HOST_SUBDOMAIN]]-8080-[[KATACODA_HOST]].environments.katacoda.com/

1. Download Filebeat:
`
cd /root/
curl -L -O https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-7.7.0-linux-x86_64.tar.gz
tar xzvf filebeat-7.7.0-linux-x86_64.tar.gz
cd filebeat-7.7.0-linux-x86_64/
`{{execute}}

2. Enable the module **NGINX**:
`./filebeat modules enable nginx`{{execute}}

3. Modify `/root/filebeat-7.7.0-linux-x86_64/filebeat.yml`{{open}} to set the connection information for Elastic Cloud:
`
cloud.id: "test:ZXVyb3BlLXdlc3QxLmdjcC5jbG91ZC5lcy5pbyQ5MjE3ODUwMjAzNjY0NmJmYjQ0NTQ0MDM4ZDllYjQ0YyRlODA5MmIwODVlNzM0ZjVmYWZjY2FmYjFkYTgyNzExNg=="
cloud.auth: "elastic:<password>"
`{{copy}}
Where `<password>` is the password of the `elastic` user.

5. Setup the dashboards and visualizations:
`./filebeat setup`{{execute}}

4. Now you can start collecting the logs by starting filebeat:
`./filebeat -e`{{execute}}
