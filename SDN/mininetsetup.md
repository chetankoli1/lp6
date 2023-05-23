# SETUP FOR MININET NETWORK EMULATION ENVIRONMENT

This guide explains how to set up the Mininet network emulation environment using VirtualBox. It also demonstrates basic commands, emulates different custom network topologies, and explains how to view flow tables.

## Setup Steps

1. **Install VirtualBox:**
   - Download and install VirtualBox from the official website (https://www.virtualbox.org/wiki/Downloads) based on your operating system.

2. **Download Mininet VM:**
   - Visit the Mininet website (http://mininet.org/) and navigate to the "Download" section.
   - Download the Mininet virtual machine (Mininet VM) in the OVA format.

3. **Import Mininet VM into VirtualBox:**
   - Open VirtualBox and go to "File" > "Import Appliance."
   - Choose the Mininet VM OVA file you downloaded and click "Next."
   - Adjust the settings if needed and click "Import."
   - Once the import is complete, you should see the Mininet VM listed in the VirtualBox Manager.

4. **Start Mininet VM:**
   - Select the Mininet VM and click "Start" in the VirtualBox Manager.
   - The Mininet VM will boot up and present you with a login prompt.

5. **Log in to the Mininet VM:**
   - Enter the username "mininet" and password "mininet" to log in to the Mininet VM.

6. **Start Mininet:**
   - In the Mininet VM terminal, type the command `sudo mn` and press Enter.
   - This will start the Mininet network emulation environment.

7. **Basic Mininet Commands:**
   - Once Mininet is started, you can use various commands to create and interact with network topologies. Here are some basic commands:
     - `nodes`: List available nodes in the network.
     - `net`: Display network information.
     - `pingall`: Test connectivity between all hosts.
     - `xterm <host>`: Open an xterm terminal for a specific host.
     - `exit`: Exit Mininet.

8. **Emulate Custom Network Topologies:**
   - You can emulate different custom network topologies using Mininet. Here are examples of three common topologies:

   - Simple topology:
     ```
     sudo mn --topo single,3 --mac --controller remote
     ```

   - Linear topology:
     ```
     sudo mn --topo linear,5 --mac --controller remote
     ```

   - Tree topology:
     ```
     sudo mn --topo tree,3 --mac --controller remote
     ```

   - These commands will create the respective network topologies with the specified number of hosts and switches.

9. **View Flow Tables:**
   - To view the flow tables in Mininet, you can use the `ovs-ofctl` command. For example, to view the flow table of a switch, use the following command:
     ```
     sudo ovs-ofctl dump-flows <switch>
     ```
     Replace `<switch>` with the name of the switch you want to inspect.

That's it! You have set up the Mininet network emulation environment using VirtualBox, demonstrated basic Mininet commands, and emulated different custom network topologies. You can explore more advanced Mininet features and commands to further enhance your network emulation experiments.
