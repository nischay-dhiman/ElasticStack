# ElasticStack
The Elastic (ELK) Stack brings fast, reliable, and relevant search to all of your operational data, regardless of the type of data.


This example Docker Compose configuration very similar to the [original](https://github.com/elastic/stack-docker) demonstrates many components of the
Elastic Stack, all running on a single machine under Docker with specific versions of ElasticSearch, Kibana, APM.

## Prerequisites
- Docker and Docker Compose.
  * Windows and Mac users get Compose installed automatically
with Docker for Windows/Mac.

  * Linux users can read the [install instructions](https://docs.docker.com/compose/install/#install-compose) or can install via pip:
```
pip install docker-compose
```

* Windows Users must set the following 2 ENV vars:
  * `COMPOSE_CONVERT_WINDOWS_PATHS=1`
  * `PWD=/path/to/checkout/for/stack-docker`
    * for example I use the path: `/c/Users/nick/elastic/stack-docker`
    * Note: you're paths must be in the form of `/c/path/to/place` using `C:\path\to\place` will not work
  * You can set these two ways:
    1. Temporarily add an env var in powershell use: `$Env:COMPOSE_CONVERT_WINDOWS_PATHS=1`
    2. Permanently add an env var in powershell use: `[Environment]::SetEnvironmentVariable("COMPOSE_CONVERT_WINDOWS_PATHS", "1", "Machine")`
      > Note: you will need to refresh or create a new powershell for this env var to take effect
    3. in System Properties add the environment variables.


* At least 4GiB of RAM for the containers. Windows and Mac users _must_
configure their Docker virtual machine to have more than the default 2 GiB of
RAM:

* Linux Users must set the following configuration as `root`:

```
sysctl -w vm.max_map_count=262144
```
By default, the amount of Virtual Memory [is not enough](https://www.elastic.co/guide/en/elasticsearch/reference/current/vm-max-map-count.html).

## Starting the stack

This is accomplished using the docker-compose.yml file:
```
docker-compose up
```

Point a browser at [`http://localhost:5601`](http://localhost:5601) to see the results.
