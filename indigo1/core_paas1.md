# Core PaaS

The Core PaaS provide the basic functionalities/tools to steer the performance of all other PaaS services. In particular: 
* the availability and scalability of the core services
* the monitoring of the Computational and Storage resources and of the PaaS µServices 
* the accounting of the resource usage in terms of computing and storage

Components & Services:
 * [Accounting](accounting1.md)
 * [Monitoring](zabbix-probes1.md)
 * [Kubernetes](kubernetes1.md)
 
 
 <a id="install"></a>
## Installation and Configuration

In order to install:
* the Accounting components please follow its [Instalation & Configuration Guide](https://indigo-dc.gitbooks.io/accounting/content/)
* For the Monitoring Components, the Zabbix-probes plugins, detailed instructions on installation and configuration can be found:
  * for the Zabbix Probes - [here](https://indigo-dc.gitbooks.io/monitoring/content/zabbix_probes.html)
  * for the Zabbix Wrapper - [here](https://indigo-dc.gitbooks.io/monitoring/content/zabbix_wrapper.html)
* for the Kubernetes clusters deployments please follow their specific [documentation](https://indigo-dc.gitbooks.io/kubernetes/content/)


