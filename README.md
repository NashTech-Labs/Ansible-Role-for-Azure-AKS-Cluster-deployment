# Ansible Role for Azure AKS Cluster Deployment

This Ansible role is designed to automate the deployment of an Azure Kubernetes Service (AKS) cluster using Ansible.

## Prerequisites

Before running this role, ensure the following prerequisites are met:

- Ansible is installed on your machine.
- Azure credentials are configured properly.
- Necessary Azure collections/modules are installed (e.g., `azure.azcollection`). you can install it with the following command:
  
   $ ansible-galaxy collection install azure.azcollection

## Directory Structure
This structure organizes your Ansible role into separate directories (handlers, tasks, and vars) inside the aks_cluster role directory.
1. handlers/
   This directory contains the handler file main.yml, responsible for managing the AKS cluster creation.

2. tasks/
   The tasks/ directory holds the primary task file main.yml, encompassing tasks for creating the Resource Group and triggering the AKS Cluster creation handler.

3. vars/
   In the vars/ directory, you'll find the main.yml file, housing essential variables required for AKS login and cluster creation, ensuring secure and efficient role execution.

4. aks_cluster.yaml
   The aks_cluster.yaml playbook file orchestrates the AKS cluster creation process by referencing the aks_cluster role. This playbook initiates the role execution, guiding the creation of the AKS cluster.

5. inven.ini
   The inven.ini file acts as the inventory file, specifically defining the localhost configuration for local connections, enabling seamless execution of the AKS cluster creation tasks.

## Usage

1. Clone this repository to your local machine:

   $ git clone https://github.com/NashTech-Labs/Ansible-Role-for-Azure-AKS-Cluster-deployment/
    
2. Update the necessary variables in `vars/main.yml` according to your Azure setup.

3. Run the Ansible playbook:
   
   $ ansible-playbook -i inven.ini aks_cluster.yaml 
    
