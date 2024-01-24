
# Despligue de plantillas ARM Azure (Máquinas Virtuales Linux y Windows, y Bases de datos MySQL  v8.0)

Pasos para el despliegue de la plantilla ARM - Virtual Machine:

## 1. Conectar con Azure

Connect-AzAccount

## 2. Codigo para realizar la implementación de la VM linux (Red HAT 7.7):

az deployment group create --resource-group {nombre del grupo} --template-file azuredeploy.json --parameters "{'vmName':{'value':'nombredelaVM'}}" "{'adminUsername':{'value':'nombreUserAdmin'}}" "{'adminPassword':{'value':'passwordUserAdmin'}}"  --output json --debug

## 2.1 Codigo para realizar la implementación de la VM Windows Server (Datacenter-2019):

az deployment group create --resource-group {nombre del grupo} --template-file azuredeployWindows.json --parameters "{'vmName':{'value':'nombredelaVM'}}" "{'adminUsername':{'value':'nombreUserAdmin'}}" "{'adminPassword':{'value':'passwordUserAdmin'}}"  --output json --debug

Si se quiere definir la localización del recurso, se debera definir entre los parámetros al momento de realizar el despligue por la PowerShell:

"{'location':{'value':'{localización}'}}"

# Pasos para el despligue de la plantilla ARM - Virtual Machine:

## 1. Conectar con Azure

Connect-AzAccount

## 2. Despligue 
az deployment group create --resource-group {nombre del grupo} --template-file mySQL.json --parameters "{'sqlName':{'value':'nombredelaSQL'}}"  "{'adminUsername':{'value':'nombreUserAdmin'}}" "{'adminPassword':{'value':'passwordUserAdmin'}}"  --output json --debug

### Notas:

{nombre del grupo} ->  Indica que se debe remplazar este campo por el nombre del grupo que ya se encuentra creado en azure (se deben eliminar los corchetes).
{nombredelaVM} -> Indica que se debe remplazar este campo por el nombre que se le asignara a la Máquina Virtual o la Base de Datos.
{passwordUserAdmin} -> Indica que se debe remplazar este campo por la contraseña que se le asignara a la Máquina virtual o la Base de Datos

## Comandos: 

--debug -> Permite visualizar los procesos detallados que se estan llevando a cabo al momento del desplegar la plantilla ARM.
--verbose -> Permite visualizar el resultado de la operación. En caso de presentarse un error, este arrojara solo el tipo de error y una breve descripción.
az group create --location {localización} --name  {nombre del grupo} -> Comando para la creación de un nuevo grupo de recursos por cosola.

# Pasos para el despligue de la plantilla ARM - Virtual Machine - Red Hat 9.3 (rhel):

## 1. Conectar con Azure

Connect-AzAccount

## 2. Despligue 

az deployment group create --resource-group rg-mercadeo-001 --template-file azuredeployvm.json --parameters "{'vmName':{'value':'vm-clubgenland-prd'}}" "{'adminUsername':{'value':'usuario'}}" "{'adminPassword':{'value':'password'}}" --output json --debug 

## Despligue VM de pruebas
az deployment group create --resource-group rg-mercadeo-001 --template-file azuredeployvmtest.json --parameters "{'vmName':{'value':'vm-clubgenland-test'}}" "{'adminUsername':{'value':'usuario'}}" "{'adminPassword':{'value':'password'}}" --output json --debug


## Parámetros

Para ejecutar las siguientes plantillas debera emplear los siguientes parámetros al desplegar por la bash:

`--resource-group`

`--template-file`

`resourceName`

`adminUsername`

`adminPassword`


## Autores

- [@Carlos Cortés](https://github.com/CarlosCortesV)
- [@Carlos Cardozo]()

