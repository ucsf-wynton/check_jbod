# check_jbod.py
This tool is used to monitor Xyratex JBOD, also known as:

- Seagate/Xyratex SP-2584
- Seagate/Xyratex SP-3584
- Seagate Exos E 4U106
- Dell MD1420
- Lenovo D1212
- Lenovo D3284

These JBODs are probably also supported with some slight modifications:
- Dell MD1280

Added support for Hitachi Global Storage Technologies (HGST) aka Western Digital JBODs:
- 4U60G2_STOR_ENCL
- H4060-J

## Requirements
* `sg_ses`

## Usage
This script is intended to be used with NRPE. The device ID is the number on the LCD screen or set via the CLI on the Exos 4U106.  Since HGST JBODs don't have those numbers, the device ID is the enumeration index. If --logical is given, then the device ID is the primary enclosure logical identifier.  If no device is given, then a list of the possible IDs is shown.

```
usage: check_jbod.py [-h] [-v] [--fan] [--volt] [--current] [--psu_status]
                     [--temp]
                     device

Monitor Fans, PSU and temperature in a Xyratex JBOD

positional arguments:
  device         JBOD ID to check

optional arguments:
  -h, --help     show this help message and exit
  -v, --verbose  increase output verbosity
  --logical      Use logical JBOD IDs
  --fan          Check fan
  --volt         Check voltage
  --current      Check current
  --psu_status   PSU status
  --temp         Check temperatures based on internal thresholds
```
