# kafka-rest-proxy

Puppet module for deploying the kafka-rest-proxy (https://github.com/confluentinc/kafka-rest)

Read more about [here](http://docs.confluent.io/1.0/installation.html#installation-yum)


### Usage

This app is managed by [Supervisord](https://github.com/Supervisor/supervisor).

```
supervisorctl status kafka-proxy

supervisorctl start kafka-proxy

supervisorctl stop kafka-proxy

supervisorctl restart kafka-proxy

```

You can access the lightweight admin web interface on port :9001

__NOTE:__ If you want to add other configurations to kafka-rest-proxy you should do it by setting a new environment variable in the [service file](https://github.com/Financial-Times/up-service-files/blob/master/kafka-rest-proxy%40.service). The kafka-rest-proxy start script will translate all the environment variables into configurations. The pattern is RP_{CONFIG_NAME}. Example: RP_FETCH_MESSAGE_MAX_BYTES=16777216 will be translated to fetch.message.max.bytes=16777216 in the configuration file.
