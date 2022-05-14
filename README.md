# EPICS PV WebSocket Configuration Environment

Configuration Environment for [EPICS PV WebSocket](https://github.com/ornl-epics/pvws) for [the Advanced Light Source (ALS) and Upgrade (ALS-U) Project](https://als.lbl.gov/als-u/overview/) at [Lawrence Berkeley National Laboratory](https://lbl.gov).

## Please

One should understand that 
- This repository is a **simple tool** to help users to setup, maintain, and upgrade EPICS PV WebSocket easily.

## Pre-requirement packages

### Debian 11

```bash
git make sudo which curl wget libjson-pp-perl 
```


### JAVA and MAVEN

Default JAVA and MAVEN configuration are for Debian 11. Please set JAVA and MAVEN according to your system.

```
```

Please check several rules in `configure/RULES_REQ` for preparation of your own JAVA and MAVEN environment.
Note that `JAVA_HOME`,`JAVA_PATH`, `MAVEN_HOME`, and `MAVEN_PATH` must be defined without any variables.

### Tomcat9

We don't need the Tomcat service running, but does the package itself. The default Tomcat9 is for the Debian 11.
Please check several Makefile rules for Tomcat9 such as `make tomcat.......`

```bash
$ make vars FILTER=TOMCAT_

------------------------------------------------------------
>>>>          Current Environment Variables             <<<<
------------------------------------------------------------

TOMCAT_DEFAULT_PORT = 8083
TOMCAT_DEFAULT_SERVER_XML = server.xml
TOMCAT_HOME = /usr/share/tomcat9
TOMCAT_INSTALL_LOCATION = /opt/tomcat9
TOMCAT_MAJOR_VER = 9
TOMCAT_MINOR_VER = 0.58
TOMCAT_SRC = apache-tomcat-9.0.58.tar.gz
TOMCAT_URL = "https://archive.apache.org/dist/tomcat/tomcat-9/v9.0.58/bin/apache-tomcat-9.0.58.tar.gz"
TOMCAT_VER = 9.0.58
```


## EPICS Environment Variables

The default EPICS Environment Variables are defined as

```bash
% make vars FILTER=EPICS_

------------------------------------------------------------
>>>>          Current Envrionment Variables             <<<<
------------------------------------------------------------

EPICS_CA_ADDR_LIST = localhost
EPICS_CA_AUTO_ADDR_LIST = YES
EPICS_CA_MAX_ARRAY_BYTES = 16384
EPICS_PVA_ADDR_LIST =
EPICS_PVA_AUTO_ADDR_LIST = YES
EPICS_PVA_BROADCAST_PORT = 5076
EPICS_PVA_NAME_SERVERS =
EPICS_CA_ADDR_LIST = localhost
EPICS_CA_AUTO_ADDR_LIST = YES
EPICS_CA_MAX_ARRAY_BYTES = 16384
```

## Build, install, and Service

* 
```
make init
make build
make install
make exist
make exist LEVEL=3
```

```
/opt/pvwebsocket/pvws.bash startup
/opt/pvwebsocket/pvws.bash shutdown
/opt/pvwebsocket/pvws.bash status
/opt/pvwebsocket/pvws.bash info
```


* https://localhost:15577/pvws/


## SystemD (WIP)

```
#
#make sd_start (WIP)
#make sd_status (WIP)
```

