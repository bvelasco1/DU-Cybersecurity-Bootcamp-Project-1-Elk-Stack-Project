# DU-Cybersecurity-Bootcamp-Project-1-Elk-Stack-Project
A configuration of an ELK stack server in order to set up a cloud monitoring system.
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

The network diagram is in the repository.

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the YAML file may be used to install only certain pieces of it, such as Filebeat.

  Filebeat Playbook File (YAML)

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly redundant, in addition to restricting traffic to the network.
Load balancers protect against DDos attacks. The jump-box VM's advantage is it can be remotely accessed with SSH.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the traffic and system logs.
Filebeat is used to ship log files.
Metricbeat records metrics and statistics to the VMs.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.1   | Linux            |
| Web-1    | VM       | 10.1.0.5   | Linux            |
| Web-2    | VM       | 10.1.0.6   | Linux            |
| DVWA-VM3 | VM       | 10.1.0.9   | Linux            |
| ELK-VM   | VM       | 10.2.0.4   | Linux            |
### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump-Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
10.1.0.4

Machines within the network can only be accessed by SSH.
The jump-box VM is allowed access to the ELK VM.

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | No                  | 10.1.0.4             |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
It's very simple to set up and use. Ansible is powerful and flexible. You can also reuse playbooks.

The playbook implements the following tasks:
-Install Docker
-Download Ansible
-Run the playbook against the selected VMs

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
Web-1, Web-2, DVWA-VM3

We have installed the following Beats on these machines:
Beats 7.6.1

These Beats allow us to collect the following information from each machine:
Beats collects log files, network data, or server metrics. Beats can collect Window system log files.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the filebeat/metricbeat playbook YAML file to /etc/hosts/roles.
- Update the filebeat configuration file to include the correct stanzas.
- Run the playbook, and navigate to Kibana to check that the installation worked as expected.
