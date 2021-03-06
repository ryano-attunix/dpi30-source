# ARM Templates

This folder contains [ARM linked templates](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-linked-templates)
that can be used to stand up a specific resource and can be used in the same way as nested templated.
A master template should call each template as a separate resource passing in parameters as necessary.

Sample master template snippet

```json
"variables": {
  "deploymentUrlBase": "https://dev.azure.com/QDnA/ADAP/_git/core-building-blocks/templates/"
},
"resources": [
  {
    "apiVersion": "2017-05-10",
    "name": "myresource",
    "type": "Microsoft.Resources/deployments",
    "properties": {
      "mode": "Incremental",
      "templateLink": {
        "uri": "[concat(variables('deploymentUrlBase'),'template.json')]",
        "contentVersion": "1.0.0.0"
      },
      "parameters": {
      }
    }
  }
]
```

Templates for root resources (ie resources that appear at the root of the Microsoft ARM reference documentation) are stored in the root folder.  Any templates for child resources are stored in subfolders named after the root resource.

The following templates are available

* [Azure Search](azure-search.md)
* [CDN Profile](cdn-profile.md)
* [CDN Endpoint](CDN/cdn-endpoint.md)
* [Certificate](certificate.md)
* [Cognitive Services](cognitive-services.md)
* [Cosmos DB](cosmos-db.md)
* [DataFactory](data-factory.md)
* [DataFactory Linked Service Azure SQL](data-Factory/datafactory-linkedservice-azuresql.md)
* [DataFactory Linked Service CosmosDb](data-Factory/datafactory-linkedservice-cosmosdb.md)
* [Keyvault](key-vault.md)
* [Keyvault Access Policy](Key-Vault/keyvault-access-policy.md)
* [Keyvault Certificates](Key-Vault/keyvault-certificates.md)
* [Keyvault Secrets](Key-Vault/keyvault-secrets.md)
* [Network](network.md)
* [Public IP Address](public-ip.md)
* [Redis Cache](redis.md)
* [Service Bus](ServiceBus/service-bus.md)
* [Service Bus Firewall vNet Rule](ServiceBus/servicebus-firewall-vnetrule.md)
* [Service Bus Queue Auth Rule](ServiceBus/servicebus-queue-authrule.md)
* [SQL Server Managed Instance](sql-managed-instance.md)
* [SQL Server](sql-server.md)
* [Storage Account](storage-account.md)
* [Storage Account Container](Storage/storage-account-arm-container.md)
