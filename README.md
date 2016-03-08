# udhcpcd advanced filters
Patch for Busybox `udhcpcd` to add config options for restricting what types of clients can connect.

### chaddr_filter
MAC filter, allows specifying a MAC address Mask with wildcards `**`, which will cause the DHCP server to ignore requests coming from any other devices. Wildcards must be in pairs, can't wildcard partial-bytes.

### client_id_filter
Client ID is DHCP Option #61, this filter allows specifying a string that Client ID must start with in order for the server to offer an address.

Example `udhcpd.conf`:
```
chaddr_filter	a1b2c3******
client_id_filter	my_device_
```
