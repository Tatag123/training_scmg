# GE.station.xml

## Overview

`GE.station.xml` is a **station metadata configuration file** used in seismic data processing systems, particularly within the **SeisComP** environment.

This file defines seismic stations that belong to a specific network and provides metadata required by the system to identify, process, and monitor seismic data streams.

The configuration follows the **SeisComP XML schema** for station inventory metadata.

---

## File Information

| Parameter | Description                           |
| --------- | ------------------------------------- |
| File Name | `GE.station.xml`                      |
| Format    | XML                                   |
| Schema    | SeisComP Station Metadata             |
| Purpose   | Define seismic station configurations |

---

## Defined Stations

This file contains definitions for several seismic stations in the network, such as:

| Station Code |
| ------------ |
| BBJI         |
| BKB          |
| BKNI         |
| BNDI         |

Each station definition typically includes information such as:

* Station code
* Description
* Geographic location
* Sensor configuration
* Operational parameters

---

## Directory Structure Example

In a typical **SeisComP installation**, this file is located in the inventory configuration directory:

```
/etc/seiscomp3/inventory/
    ├── network.xml
    ├── station.xml
    └── GE.station.xml
```

Or within a configuration repository:

```
inventory/
 └── GE.station.xml
```

---

## Usage

This configuration file is used by SeisComP modules to:

* Register seismic stations in the network
* Link sensors and channels with station metadata
* Support earthquake detection and location processing
* Provide metadata for monitoring systems

After modifying the file, reload the configuration:

```
seiscomp update-config
seiscomp restart
```

---

## Validation

To check whether the XML file is valid:

```
xmllint --noout GE.station.xml
```

You can also verify configuration integrity using SeisComP:

```
seiscomp check
```

---

## Example XML Structure

Example of a station definition inside the file:

```xml
<station code="BBJI">
    <description>Seismic Station</description>
</station>
```

---

## Example: Reading the File with ObsPy

This file can be read using **ObsPy** in Python:

```python
from obspy import read_inventory

inventory = read_inventory("GE.station.xml")
print(inventory)
```

---

## Maintenance

If you need to add a new seismic station:

1. Edit `GE.station.xml`
2. Add the new station definition
3. Validate the XML file
4. Reload SeisComP configuration

---

## Related Tools

Common tools used with this configuration:

* SeisComP
* ObsPy
* xmllint

---

## License

This repository contains configuration files intended for seismic network deployment and monitoring.
