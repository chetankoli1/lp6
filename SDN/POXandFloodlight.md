# Custom Topology Setup with Remote Controllers

This guide explains how to install and run a custom topology using remote controllers such as POX and Floodlight. It also covers how to recognize inserted flows by the controllers.

## Prerequisites

- Python installed on your system.
- Mininet installed. Refer to the earlier steps for Mininet setup.

## Installing and Running POX Controller

1. **Download POX Controller:**
   - Visit the official POX GitHub repository: [POX GitHub](https://github.com/noxrepo/pox).
   - Download the latest version of POX by clicking on the "Code" button and selecting "Download ZIP".
   - Extract the downloaded ZIP file to a desired location on your machine.

2. **Create a Custom Topology:**
   - Open a new terminal.
   - Navigate to the extracted POX directory.
   - Inside the POX directory, navigate to the "pox" folder.

3. **Start the POX Controller:**
   - In the terminal, run the following command to start the POX controller with the desired application:
     ```
     ./pox.py <desired-application>
     ```
   - Replace `<desired-application>` with the specific application you want to run. For example, if you want to run the L2 learning switch application, use `./pox.py forwarding.l2_learning`.

4. **Create a Custom Mininet Topology:**
   - Open a new terminal.
   - Start Mininet with a custom topology and the remote controller option:
     ```
     sudo mn --topo <topology> --controller remote
     ```
   - Replace `<topology>` with the desired custom topology. For example, you can use "linear", "tree", or "single".

5. **Test the Network:**
   - In the Mininet terminal, you can use various commands to test the network, such as `pingall` to test connectivity between all hosts.

## Installing and Running Floodlight Controller

1. **Download Floodlight Controller:**
   - Visit the official Floodlight website: [Floodlight Website](https://floodlightcontroller.org/) and navigate to the "Downloads" section.
   - Download the latest stable release of Floodlight.

2. **Start the Floodlight Controller:**
   - Open a new terminal.
   - Navigate to the Floodlight directory.
   - Start the Floodlight controller by running the following command:
     ```
     java -jar target/floodlight.jar
     ```

3. **Create a Custom Mininet Topology:**
   - Open a new terminal.
   - Start Mininet with a custom topology and the remote controller option:
     ```
     sudo mn --topo <topology> --controller remote --ip <controller-ip> --port <controller-port>
     ```
   - Replace `<topology>` with the desired custom topology, `<controller-ip>` with the IP address of the machine running the Floodlight controller, and `<controller-port>` with the port on which the Floodlight controller is listening (default is 6653).

4. **Test the Network:**
   - In the Mininet terminal, you can use various commands to test the network, such as `pingall` to test connectivity between all hosts.

## Recognizing Inserted Flows
- Both POX and Floodlight controllers have APIs and methods to handle and recognize inserted flows.
- Refer to the respective documentation and examples provided by the controllers to implement flow recognition based on your specific requirements.

That's it! You have installed and run a custom topology using remote controllers like POX and Floodlight. Remember to refer to the documentation of
