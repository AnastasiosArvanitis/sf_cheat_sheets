<style>
    r { color: #c4454b }
    o { color: #f27d29 }
    g { color: #409945 }
    bl { color: #4378d9 }
</style>

# <r>SF Cheat Sheet

##  <bl>SF CLI
### <o>Project
#### <g>Retrieve
- sf project retrieve start --metadata ApexClass
- sf project retrieve start --metadata ApexClass:MyApexClass
- sf project retrieve start --metadata 'ApexClass:MyApex*'
- sf project retrieve start --metadata CustomObject ApexClass
- sf project retrieve start --metadata CustomObject --metadata ApexClass
- sf project retrieve start --manifest package.xml
- sf project retrieve start --manifest C:\\Users\\AnastasiosARVANITIS\\work\\_DEV\\sncf_dev\\scripts\\packages\\package.xml

#### <g>Deploy
- sf project deploy start --metadata ApexClass
- sf project deploy start --metadata ApexClass:MyApexClass
- sf project deploy start --manifest C:\\Users\\AnastasiosARVANITIS\\work\\_DEV\\sncf_dev\\scripts\\packages\\package.xml

### <o>Crud

#### <g>Create Record
- sf data create record --sobject Account --values "Name=Acme"
- sf data create record --sobject Account --values "Name='Universal Containers' Website=www.example.com" --target-org my-scratch

#### <g>Update Record
- sf update --object <object_name> --id <record_id> --fields <field_names> --values <field_values>

#### <g>Discibe Object
- sf describe --object <object_name>

#### <g>Discibe Custom fields
- sf describe --customizable --object <object_name>

#### <g>Retrive records
- sf query --q <soql_query>

### <o>Relationships

#### <g> Structure of specified relationship
- sf describe --relationship <relationship_name>

#### <g> Retrieve records from related object types
- sf query --lookup_relationship <relationship_name>

#### <g> Describes the custom relationships for the specified object type.
- sf describe --customizable --relationship <relationship_name>

## <bl>REST API
### <o> Connect
#### <g>Get access token
- sf org display --target-org ext.anastasios.arvanitis@gares.sncf.fr.devrlc

### <o> Get
#### <g>List Accounts
- curl https://gare--devrlc.sandbox.my.salesforce.com//services/data/v59.0/sobjects/Account/ -H "Authorization: 00D4E000000E2lM!AQ4AQJU84QVP4hE_4huvPMjoIznhPXU6ZoL7H9OxbQ_3bak5SAZyNQQGOiYmZSuWoux2y3cFG._ZZXJKvnHchYDKuR2XetMy"

## <bl>Tolling API
### <o> Create
#### <g>Create Trace Flag
- sf data create record --use-tooling-api --sobject TraceFlag --values "DebugLevelId=7dl170000008U36AAE StartDate=2022-12-15T00:26:04.000+0000 ExpirationDate=2022-12-15T00:56:04.000+0000 LogType=CLASS_TRACING TracedEntityId=01p17000000R6bLAAS"

## <bl>Metadata API
### <o> Create

| Endpoint | Method | Description |
| ------- | ------- | ------- |
| /services/data/v59.0/sobjects/{objectName}/describe | GET | retrieve information about a specified object type |
| Paragraph | Text | Text |