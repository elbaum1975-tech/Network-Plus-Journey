# Small isolated Proxmox network lab

This blueprint uses two small Linux guests to practice addressing, DNS, HTTP, packet capture, and troubleshooting. It is a learning design, not a one-click installer. Proxmox menus and guest networking vary by version and template.

## Topology

Create a virtual bridge with **no physical port, host address, gateway, or NAT**. Attach one toolbox guest and one target guest to it.

| Role | Example address | Purpose |
|---|---|---|
| Toolbox | `192.168.50.10/24` | `dig`, `curl`, `ping`, `tcpdump` or Wireshark, and authorized service checks |
| Target | `192.168.50.20/24` | A simple web server and a lab-only DNS name |

These addresses are examples only. Choose an unused private subnet in your own lab. Do not copy private hypervisor or home-network settings into a public project.

## Isolation checks before testing

- The virtual bridge has no physical uplink and no IP address on the hypervisor.
- Both guests have only their lab NIC while exercises are running.
- Neither guest has a default route to a home or public network.
- If a toolbox guest also has a management NIC, IP forwarding is disabled and firewall rules prevent it from routing between NICs.
- The web, DNS, and throughput services bind only to the target’s lab address.
- Any temporary package-download path is removed before exercises begin.

From each guest, inspect `ip -br address` and `ip route`. Verify only the intended lab network appears and there is no default route. If these checks do not match the design, stop and correct the topology before scanning or capturing traffic.

## Build the target services

On the target, install a simple HTTP service, a DNS resolver configured only for the lab zone, and optionally an `iperf3` server. Bind each service to the target lab address. Use a harmless static page and a made-up zone such as `course.test`; do not expose an open recursive DNS resolver.

Allow only the services required by the exercise from the toolbox guest: DNS TCP/UDP 53, HTTP TCP 80, and optionally `iperf3` TCP 5201. Keep all other inbound traffic blocked. Never install intentionally vulnerable software on a network connected to real devices.

## Exercises

1. **Addressing and reachability:** Compare interface and route output, then test the target address with a few ICMP echo requests if allowed.
2. **DNS:** Query the lab DNS server for its local target name. Explain the query, answer, and why the lab DNS server is used for this query.
3. **HTTP:** Fetch the target page by IP and name. Compare the application request with the TCP connection.
4. **Packet capture:** Capture only traffic between the two lab guests. Identify the DNS exchange and TCP handshake, then stop and save the capture.
5. **Troubleshooting:** Stop one target service, reproduce the failure, identify the listening-port or name-resolution evidence, restore the service, and verify recovery.
6. **Throughput (optional):** Run a brief `iperf3` test between the guests. Explain why a virtual switch result does not measure internet speed.

For each exercise, record the hypothesis, commands, observed output, conclusion, cleanup, and one follow-up question. A port scan, if used, must target only the lab target you configured.

## Reset and cleanup

Take a snapshot before changing the target. After the exercise, stop temporary services or revert the snapshot and verify the interface and routes again. Keep an independent backup of anything you need; snapshots on the same storage do not protect against storage failure. Start only the guests needed for the exercise.
