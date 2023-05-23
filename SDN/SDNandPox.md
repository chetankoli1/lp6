# SDN Environment with Firewall Functionality using POX Controller

This guide explains how to create an SDN (Software-Defined Networking) environment on Mininet and configure a switch to provide firewall functionality using the POX controller.

## Prerequisites

- Mininet installed. Refer to the earlier steps for Mininet setup.
- POX controller installed. Follow the steps in the earlier section to download and set up the POX controller.

## Steps to Create Firewall Functionality

1. **Create Custom Topology:**
   - Open a new terminal.
   - Start Mininet with a custom topology and the remote controller option:
     ```
     sudo mn --topo <topology> --controller remote
     ```
   - Replace `<topology>` with the desired custom topology. For example, you can use "linear", "tree", or "single".

2. **Configure Firewall Functionality:**
   - In the Mininet terminal, create a new xterm terminal for the switch:
     ```
     xterm <switch>
     ```
   - Replace `<switch>` with the name of the switch where you want to configure the firewall.

3. **Start POX Controller:**
   - In a separate terminal, navigate to the POX directory.
   - Start the POX controller with the `firewall.py` module:
     ```
     ./pox.py log.level --DEBUG forwarding.l2_learning firewall
     ```

4. **Configure Firewall Rules:**
   - In the xterm terminal for the switch, enter the following command to configure the firewall rules:
     ```
     iptables -I FORWARD -s <source-ip> -d <destination-ip> -j DROP
     ```
   - Replace `<source-ip>` and `<destination-ip>` with the appropriate IP addresses for the desired firewall rule.

5. **Test Firewall Functionality:**
   - In the Mininet terminal, test the network connectivity by pinging between hosts that are affected by the firewall rules.

That's it! You have created an SDN environment on Mininet and configured a switch to provide firewall functionality using the POX controller. Customize the firewall rules according to your requirements.

Remember to refer to the documentation and examples provided by Mininet and POX for further customization and advanced features.
