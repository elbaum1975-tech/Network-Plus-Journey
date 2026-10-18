# Routed VLAN lab: from virtual guests to a physical server

Recorded October 18, 2026. This is the next stage after the
[disconnected two-guest blueprint](isolated-proxmox-network-lab.md), which remains
an alternative exercise. Actual private addresses and configuration exports are
omitted; use your own verified address plan.

## What changed

- A managed switch separates home VLAN 1 from lab VLAN 77.
- The hypervisor uplink carries untagged home traffic and tagged lab traffic.
- A lab access port connects a physical Windows Server without requiring VLAN
  configuration on the server's NIC.
- OPNsense provides the lab gateway, DHCP, DNS and outbound internet access.
- The toolbox's direct home interface was removed; it now uses only the lab path.
- Windows Server provides Active Directory and domain DNS. The Windows client VM
  has booted to login, but edition verification and domain joining are still pending.

## Evidence and Network+ concepts

| Observation | Concept practiced | Limit |
| --- | --- | --- |
| Tagged uplink plus untagged access port | 802.1Q, VLAN membership, PVID | Membership must be checked on both switch and hypervisor |
| Static server address outside the DHCP pool | Addressing and DHCP | A stable IP alone does not validate DNS |
| Lab internet/DNS works | Gateway, DNS and NAT | Does not prove all firewall paths are correct |
| Home-router probe blocked with firewall log evidence | Rule ordering and segmentation | One probe is not a complete IPv4/IPv6 isolation audit |
| AD LDAP SRV records resolve through server DNS | DNS service discovery | Does not prove a client is joined |

The lab bridge now has a physical uplink and the guests have a default gateway.
It is no longer the disconnected topology; use it for benign owned-system
exercises and capture only selected lab traffic. Keep the home-router block before
the general outbound allow. AD clients need domain-controller DNS, while the Linux
tools currently use the firewall resolver.

## Next exercise

Verify the Windows client's edition and DNS configuration, resolve the domain's
LDAP SRV record against the DC, join the domain, restart and verify a domain sign-in.
Record each result before marking the step complete. Then practice one controlled
DNS failure and restoration. Store actual domain names, addresses and output privately.
