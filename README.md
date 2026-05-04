🌐 Microsense: Cisco Network Automation
This repository hosts the Microsense Ansible Role, a modular automation framework designed for Cisco IOS devices. Microsense transforms manual, CLI-based network management into a standardized, error-free, and rapid Infrastructure-as-Code (IaC) deployment process.

📋 What does this role do?
The role is structured into logical modules that execute sequentially to build a secure and fully functional switch configuration from scratch:

1. System Hardening & Monitoring
Core Configuration: Applies fundamental system settings and enterprise security baselines.

SNMP Configuration: Sets up SNMP interfaces to ensure the device is immediately discoverable by monitoring solutions.

2. Network Logic (Routing & VLANs)
Routing: Configures IP routes to define precise traffic flow and gateway connectivity.

VLAN Deployment: Automatically provisions virtual networks. By utilizing the vlans data list, the role can deploy any number of VLANs in a single execution.

3. Interface Management (LAG & Ports)
LAG Deployment (Link Aggregation): Bundles multiple physical links into a single logical channel for increased bandwidth and redundancy (LACP/EtherChannel).

Port Provisioning: Configures individual switch ports (e.g., access/trunk modes, port security) based on dynamic input variables.

4. State Persistence
Final Save: Every successful deployment concludes with a verified write memory command. This ensures that all configurations persist through power cycles or reboots.

🛠 Why Microsense?
Modularity: Each component (VLANs, Routing, Ports) is an isolated module. This makes the code easy to maintain, audit, and extend.

Scalability: Whether you need to deploy 1 or 100 VLANs—you simply update your data list. The automation handles the heavy lifting via intelligent loops.

Security-First: Designed to integrate seamlessly with ansible-vault, ensuring that sensitive credentials never exist in plain text.

🚀 Quick Start
To initiate a deployment, call the main playbook with your inventory:
ansible-playbook -i inventories/hosts.yml playbooks/sw-configuration.yml --ask-vault-pass