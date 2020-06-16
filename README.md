# PAG_stack

## Prometheus, Alert Manager, Grafana (PAG) stack for dynamic monitoring

* Prometheus is an open-source systems monitoring and alerting toolkit originally built at SoundCloud. Since its inception in 2012, many companies and organizations have adopted Prometheus, and the project has a very active developer and user community. It is now a standalone open source project and maintained independently of any company

* Alert-Manager handles alerts sent by client applications such as the Prometheus server. It takes care of deduplicating, grouping, and routing them to the correct receiver integration such as email, PagerDuty, or OpsGenie. It also takes care of silencing and inhibition of alerts.

* Grafana is a multi-platform open source analytics and interactive visualization web application. It provides charts, graphs, and alerts for the web when connected to supported data sources. It is expandable through a plug-in system. End users can create complex monitoring dashboards using interactive query builders.

## Why this Reposiotry?

- Found many repositories with PAG stack deployment docker-compose file, but all used [node-exporter](https://github.com/prometheus/node_exporter).
- But, if you have collectd intsalled on the system you want to monitor, I couldn't find a pre-made docker-compose file which did that.

*For node-exporter you can checkout the **[master](https://github.com/ADI10HERO/PAG_stack/tree/master)** branch of this repo*

# What will be deployed with this docker-compose?

**1.** Prometheus server scraping itself, cAdvisor and collectd-exporter

**2.** Alertmanager for alerting, using this is fairly simple. You can send Slack, IRC even Email notifications.

**3.** Grafana (3 amazing dashboards already available, check references)

**4.** cAdvisor, this is used to monitor the docker-host, the machine on which all these containers will run.

**5.** Collectd exporter, not diving into architectural details, this is used to make collectd metrics available to prometheus

**6.** simple-webhook-reciever, this is a very simple http reciever ([written by me](https://hub.docker.com/r/adi10hero/simple-webhook-reciever)) to show the alerts on browser, as mentioned you can set up slack, email, etc but a simple webhook will give your alerts a platform without any external configurations, a good start, isn't it?

## Next steps
- [ ] Add basic auth to routes using caddy 
- [ ] Improving the gui and add features of [simple-webhook-reciever](https://github.com/adi10hero/simple-webhook-reciever/)


#### Contributing
- Fork the repository
- Add a feature
- Test it
- Make a PR, add test results in the PR
- Get it reviewed and merged :)


#### Note:
Any kind of contribution is most welcome

##### Refernces:
- Original compose's template : [dockprom](https://github.com/stefanprodan/dockprom)


