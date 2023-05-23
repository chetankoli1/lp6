# Building Your Own Internet Router using Mininet and POX Controller

This guide explains how to build your own internet router using Mininet as an emulator and the POX controller. The router will receive raw Ethernet frames and process the packets, forwarding them to the correct outgoing interface based on a static routing table.

## Prerequisites

- Mininet installed. Refer to the earlier steps for Mininet setup.
- POX controller installed. Follow the steps in the earlier section to download and set up the POX controller.

## Steps to Build the Router

1. **Create a Custom Topology:**
   - Open a new terminal.
   - Start Mininet with a custom topology and the remote controller option:
     ```
     sudo mn --topo single,3 --controller remote
     ```
   - This command creates a single switch with three hosts connected to it. Adjust the topology and the number of hosts as needed.

2. **Start the POX Controller:**
   - In a separate terminal, navigate to the POX directory.
   - Start the POX controller with the `openflow.of_01 --port=<port>` module:
     ```
     ./pox.py openflow.of_01 --port=<port>
     ```
   - Replace `<port>` with the desired port number for the controller (default is 6633).

3. **Build and Run the Router Script:**
   - Open a new terminal.
   - Navigate to the Mininet directory.
   - Run the following command to build and run the router script:
     ```
     sudo python examples/simple_router.py
     ```

4. **Configure the Routing Table:**
   - In the Mininet terminal, use the following command to configure the routing table for the router:
     ```
     r0 route add -net <destination-network> gw <gateway-ip>
     ```
   - Replace `<destination-network>` with the desired destination network and `<gateway-ip>` with the IP address of the gateway.

5. **Test Packet Forwarding:**
   - In the Mininet terminal, test the packet forwarding by sending ping requests from one host to another:
     ```
     h1 ping -c 3 h2
     ```
   - Ensure that the packets are correctly forwarded to the appropriate outgoing interface based on the routing table.

That's it! You have built your own internet router using Mininet as an emulator and the POX controller. Customize the routing table and test the packet forwarding logic according to your requirements.

Refer to the documentation and examples provided by Mininet and POX for further customization and advanced features.
