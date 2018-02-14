# docker-zabbix-agent
Simple zabbix-agent inside the docker + [iostat metrics](https://github.com/lesovsky/zabbix-extensions/tree/master/files/iostat)

## Docker run

* Save `zabbix_agentd.conf`

```
docker run --rm -v ${PWD}:/pwd -ti zabbix-agent cp /etc/zabbix/zabbix_agentd.conf /pwd/
```

* Edit `zabbix_agentd.conf`

* Run container:

```
docker run -ti --privileged -v ${PWD}/zabbix_agentd.conf:/etc/zabbix/zabbix_agentd.conf -v /dev:/dev --net=host -ti zabbix-agent
```

## Kubernetes run

Example [zabbix-agent.yaml](zabbix-agent.yaml) daemonset.

You can run it like:

```
kubectl apply -f https://raw.githubusercontent.com/kvaps/docker-zabbix-agent/master/zabbix-agent.yaml
```
