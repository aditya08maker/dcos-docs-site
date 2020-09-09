---
layout: layout.pug
navigationTitle: Release notes for 1.13.10
title: Release notes for 1.13.10
menuWeight: 0
excerpt: Release notes for DC/OS 1.13.10, including Open Source attribution, and version policy.
---
DC/OS&trade; 1.13.10 was released on ??, 2020.

[button color="light" href="https://downloads.dcos.io/dcos/stable/1.13.10/dcos_generate_config.sh"]Download DC/OS Open Source[/button]

[button color="purple" href="https://downloads.mesosphere.com/dcos-enterprise/stable/1.13.10/dcos_generate_config.ee.sh"]Download DC/OS Enterprise* [/button]

New customers contact your sales representative or <a href="mailto:sales@mesosphere.io">sales@mesosphere.io</a> before attempting to download and install DC/OS Enterprise.

# Release Summary
DC/OS is a distributed operating system that enables you to manage resources, application deployment, data services, networking, and security in an on-premise, cloud, or hybrid cluster environment.

### DC/OS Fixed and Improved Issues

- COPS-6411 


- An issue where selecting *Install DC/OS CLI* presents a URL to a binary that is incorrect as been fixed. (COPS-6360) 
- Selecting **Run** on a job or selecting **Delete** to remove a group had no effect and threw an exception. (COPS-6324)
- DC/OS OSS UI was not displaying a user name, but instead showed a **User added through OIDC ID Token login** message. (COPS-6295, D2IQ-70199)
- After an upgrade, the dcos-telegraf directories had incorrect permissions leading to a problem launching tasks. (COPS-6232, D2IQ-69295)
- A critical error in Metronome where existing jobs appear to be lost after upgrade. (DCOS_OSS-5965, COPS-6174)
- Users were unable to remove empty folders from Metronome. (COPS-6139, D2IQ-68541)
- Zookeeper log messages are now being forwarded to syslog. (COPS-6128, D2IQ-68394)
- Exhibitor was writing JNA files to /tmp. (COPS-6111, D2IQ-68109, D2IQ-68868) 
- Using file-based secrets caused mount failure and issues in the json editor. (COPS-6085, D2IQ-68114, D2IQ-67819) 
- An unknown response code was received when querying DC/OS health endpoints. (COPS-5915, COPS-5979, D2IQ-65296, D2IQ-69169) 
- Fixed an issue with unmounting external persistent volumes in Mesos (COPS-5920, D2IQ-65497)
- The dcos-diagnostics component now rate limits diagnostic checks to avoid performance slowdowns in large clusters. (COPS-5915)
- An issue where a master node was not able to rejoin a cluster after failure/restart when another master is offline or being upgraded is now resolved. (COPS-1754)
- An issue where pressing *Enter* in the Secret ID textbox, reloads the DC/OS UI has been resolved. (D2IQ-14964)
COPS-6360
COPS-6355
COPS-6329
COPS-6324
COPS-6295
COPS-6232
COPS-6174
COPS-6139
COPS-6128
COPS-6111
COPS-6085
COPS-5979
COPS-5920
COPS-5915
cops-1754

D2IQ-70199
D2IQ-69295
D2IQ-68868
D2IQ-68541
D2IQ-68394
D2IQ-68114
D2IQ-68109
D2IQ-67844
D2IQ-67819
D2IQ-67284
D2IQ-65497
D2IQ-65296
D2IQ-62221
D2IQ-57756
D2IQ-14964