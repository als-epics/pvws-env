# EPICS PV WebSocket Configuration Environment

Configuration Environment for [EPICS PV WebSocket](https://github.com/ornl-epics/pvws) for [the Advanced Light Source (ALS) and Upgrade (ALS-U) Project](https://als.lbl.gov/als-u/overview/) at [Lawrence Berkeley National Laboratory](https://lbl.gov).

## Please

One should understand that 
- This repository is a **simple tool** to help users to setup, maintain, and upgrade EPICS PV WebSocket easily.

## Pre-requirement packages

```bash
git make sudo which
```


## JAVA and MAVEN

Please check two rules `conf.jdk.macos` and `conf.mvn.macos` in `configure/RULES_REQ' for preparation of your own JAVA and MAVEN environment.
Note that `JAVA_HOME`,`JAVA_PATH`, `MAVEN_HOME`, and `MAVEN_PATH` must be defined without any variables.


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
make sql.show
```

## Build, install, and Service

```
make init
make build
make install
make exist
```

```
/opt/pvwebsocket/pvws.bash startup
/opt/pvwebsocket/pvws.bash shutdown
/opt/pvwebsocket/pvws.bash info
```

```
https://localhost:15577/pvws/
```

## SystemD (WIP)

```
#
#make sd_start (WIP)
#make sd_status (WIP)
```

