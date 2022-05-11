---
layout: post
author: Edouard Tisserant
title: "OSIE, OPC-UA"
excerpt_separator: <!--more-->
---

Beremiz project is used in [OSIE project](https://www.osie-project.eu/) and gains support for OPC-UA client.

| --- | --- |
| ![OSIE](/assets/img/2022-03-05-osie-OPC-UA/NXD-Media.Logo.Osie.png) | [OSIE](https://www.osie-project.eu/) aims to transforms industrial automation into a branch of the open source software and hardware ecosystems. |

| --- | --- |
| ![OPC UA](/assets/img/2022-03-05-osie-OPC-UA/opcua.png) | OPC UA is a cross-platform, open-source, IEC62541 standard for data exchange from sensors to cloud applications developed by the [OPC Foundation](https://opcfoundation.org/). |

<!--more-->
## Beremiz and OSIE

OSIE will cut prices by an order of magnitude, eliminate interoperability blockers, accelerate data-driven business and provide flexibility for Industry 4.0. It will support real-time orchestration and deterministic, end-to-end communication at the edge using generic hardware.

Beremiz is the IEC-61131 IDE and toolchain selected by the [OSIE project](https://www.osie-project.eu/).

OSIE demonstrated a [Proof Of Concept with Beremiz and Modbus](https://www.osie-project.eu/P-OSIE.HowTo.Control.A.Coupler.Over.Modbus.With.Beremiz).

## OPC-UA Client for Beremiz

OPC-UA Client Beremiz extension let programmer browse OPC-UA server directly in Bermiz IDE, thanks to [FreeOpcUa’s python-opcua](https://github.com/FreeOpcUa/python-opcua) implementation.
According to configured servers and selected variables, C code is generated so that runtime can interact with [open62541](https://github.com/open62541/open62541) stack to collect and change values of selected server’s variables.

![OPC-UA client extension](/assets/img/2022-03-05-osie-OPC-UA/OPC-UA-extension.jpg)

Extension was developed with re-use and testing in mind. First was developed a simple standalone wxPython app allowing selection of OPC-UA server variables, saving and loading selection, and generate C code of a standalone process that read and write selected variables in a loop. Standalone app is available in source code and can be launched with `python opc_ua/opcua_client_maker.py`.

![OPC-UA Standalone client generator app](/assets/img/2022-03-05-osie-OPC-UA/OPC-UA-standalone.jpg)

