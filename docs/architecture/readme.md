# Application Architecture

This lab creates the test infrastructure in azure to demo how federal logging requirements are met, these requirements are derived from the [Secure Cloud Computing Architecture](https://rmf.org/wp-content/uploads/2018/05/SCCA_FRD_v2-9.pdf) and [Guide to Computer Security Log Management](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-92.pdf). The derived requirements and detailed examples, evidence, and justification documentation are provided in the Information Assurance folder.

## Resources

This demo will create the following resources in your azure subscription, all resources will be tagged with "env: logging-lab" for easy access and cost management. It is recommended to delete these resources after completing the lab.

- A resource group called Logging-Lab
- A Log Analytics Workspace called LAB-LAW
- A Windows Machine called LAB-WM
- A Linux Machine Called LAB-LM
- A Cosmos Dababase called LAB-CDB
- An AKS cluster called LAB-AKS
- A Postgresql database called LAB-PG
- A Virtual Networked called LAB-VNET
- A Network Security Group called LAB-NSG
- A Key Vault called LAB-KV
- A Azure Storage Account called labsa

## Applications

This lab will also deploy several applications that serve to generate logs to be viewed by the lab user. Their functions are listed below

- Write data to cosmos db every 1 minute
- Read data from cosmos db every 1 minute
- Create traffic that will be denied by the deployed network security group
- Access key vault successfully every 1 minute
- Fail to access key vault every 1 minute
- Access azure storage and download a blob every 1 minute

## Grafana

This lab will also deploy Grafana to AKS and walk you though how to connect to log analytics and create custom dashboards. This application can be used to avoid portal access and restrict what information is available to defined groups.