In this step, you will learn how to download Filebeat and configure it for a web server. You will also learn how to start Filebeat and ingest the logs from an Nginx web server, sending each log event to the Cloud deployment created in the previous step.
<iframe style="width: 700px;height: 400px;" src="https://www.youtube.com/embed/a4_o9QetfWA" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Let's try it out!

1. Download Filebeat:
`
curl -L -O https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-7.7.0-linux-x86_64.tar.gz
tar xzvf filebeat-7.7.0-darwin-x86_64.tar.gz
cd filebeat-7.7.0-darwin-x86_64/
`{{execute}}

2. Enable the module **NGINX**:

`./filebeat modules enable nginx`{{execute}}
