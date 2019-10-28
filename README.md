

# Ansible Superset
[Superset](https://superset.incubator.apache.org/) is a modern BI app with a simple interface, feature-rich when it comes to views, that allows the user to create and share dashboards.
This app is simple and doesn’t require programming, and allows the user to explore, filter and organise data. The best part is… it’s Open Source!
This repository contains **ansible playbook** that allows to install  superset on the disterbuted cluster.

# Installation
For installation, please set ansible varaibles in the **hosts** file correctly. and run the play book that you want.
Thist repository contains two playbooks. 
Also it's possbile to encrypt hosts file with **ansible-valut** to transfer sensetive varaibles .
Th

There are two groups of hosts in the hosts file, **webserver** and **worker** hosts and  it's possbile to install webserver and worker on one node.


---
**NOTE**

Currently this plabooks supports **Debian** and also **gevent** as worker class for **gunicorn** and **celery** . 
 Contributing is oepn and welcome!

---


Here is the list of varaibles with description and example:

| Varaible | Hosts |Description| Example |
|--|--|--|--|
|SUPERSET_HOME  |Webserver, Worker  | | /home/superset
|SUPERSET_VERSION|Webserver, Worker| | 0.34.1
|REDIS_HOST|Webserver, Worker| | localhost
|REDIS_PORT|Webserver, Worker|| 6379
|REDIS_DB| Webserver, Worker|Redis database to store superset data on it| superset
|DB_TYPE| Webserver, Worker| Database driver name to use it on **sqlalchemy** urI| mysql or sqlite|
|DB_USERNAME| Webserver, Worker||superset|
|DB_PASSWORD| Webserver, Worker||superset|
|DB_NAME|  Webserver, Worker|| superset
|SECRET_KEY| Webserver, Worker| ||
| MAPBOX_API_KEY| Webserver, Worker| Mapbox token for using some map based visualization on superset|
|SQLALCHEMY_TRACK_MODIFICATIONS|Webserver, Worker|| True|
|SQLLAB_TIMEOUT|Webserver, Worker| |60|
|SUPERSET_WEBSERVER_TIMEOUT|Webserver, Worker|| 60|
|GUNICORN_BIND|Webserver| |0.0.0.0:8000|
|GUNICORN_TIMEOUT|Webserver||60|
|GUNICORN_WORKERS|Webserver||4|
|CELERY_WORKER|Worker||4
|CELERY_POOL|Worker||gevent

