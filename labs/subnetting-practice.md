# Subnetting practice

Subnetting becomes easier when you work through the same steps every time. Use a calculator only after you have tried the binary or block-size method yourself.

## A repeatable method

For a given IPv4 address and prefix:

1. Convert the prefix to a subnet mask.
2. Find the interesting octet and the block size (`256 - mask value`).
3. Find the network boundary containing the address.
4. Identify the broadcast address and usable host range for ordinary subnets.
5. Check that the result fits the requested number of networks and hosts.

## Worked example

Find the network for `192.168.10.77/26`.

- `/26` is `255.255.255.192`.
- The last octet has a block size of `256 - 192 = 64`.
- The ranges begin at 0, 64, 128, and 192. Address 77 falls in the 64–127 range.
- Network: `192.168.10.64`; broadcast: `192.168.10.127`.
- Usable host range: `192.168.10.65–192.168.10.126`.

## Practice set

For each item, find the mask, network, broadcast, usable range, and number of usable host addresses. Show your work before checking with a tool.

1. `10.20.30.41/27`
2. `172.16.5.199/28`
3. `192.168.4.130/25`
4. Divide `192.168.50.0/24` into at least six equal-size subnets. State the prefix and usable hosts per subnet.

Keep a log of any boundary or host-count mistakes and redo a similar problem the next day.
