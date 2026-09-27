Network Configuration and Connectivity Validation
Objective

Verify the Ubuntu virtual machine's network interface, IPv4 connectivity, DNS resolution, routing table, and DNS configuration.

Environment
Virtualization: UTM on Apple Silicon
Operating system: Ubuntu
Network interface: enp0s1
Tests Performed
1. Network Interface

Command: ip -br addr

Result:

Interface enp0s1 was UP.
IPv4 address: 192.168.64.2/24
2. External IP Connectivity

Command: ping -c 4 8.8.8.8

Result:

Packet loss: 0%
Interpretation: Successful connectivity to the tested external IP address.
3. DNS Resolution

Command: ping -c 4 google.com

Result:

Packet loss: 0%
Interpretation: The hostname resolved and responded to ping requests.
4. Routing Table

Command: ip route

Result:

Default gateway: 192.168.64.1
Network interface: enp0s1
Local subnet: 192.168.64.0/24
5. DNS Configuration

Command: resolvectl status

Result:

Current DNS server: 192.168.64.1
DNS configuration was available on enp0s1.
Conclusion

The Ubuntu virtual machine successfully reached the tested external IP address and resolved and reached the tested hostname. The routing table contained a default route through 192.168.64.1.

These results establish baseline network connectivity. They do not independently establish that the network is secure or that all network services are functioning correctly.
