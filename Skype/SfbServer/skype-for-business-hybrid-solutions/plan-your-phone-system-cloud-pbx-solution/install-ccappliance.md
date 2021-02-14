---
title: Install-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: El cmdlet Install-CcAppliance instala el dispositivo de Skype Empresarial Cloud Connector Edition(incluidas las máquinas virtuales de AD, Almacén de administración central, Servidor de mediación y Servidor perimetral) en el servidor host.
ms.openlocfilehash: fe1fab785e2681614f27035714b6ddead22b8707
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799880"
---
# <a name="install-ccappliance"></a>Install-CcAppliance
 
El cmdlet Install-CcAppliance instala el dispositivo de Skype Empresarial Cloud Connector Edition(incluidas las máquinas virtuales de AD, Almacén de administración central, Servidor de mediación y Servidor perimetral) en el servidor host. 
  
```powershell
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se instala un nuevo dispositivo de Cloud Connector en el servidor host:
  
```powershell
Install-CcAppliance
```

### <a name="example-2"></a>Ejemplo 2

En el siguiente ejemplo se actualiza Cloud Connector a la versión más reciente:
  
```powershell
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a>Ejemplo 3

En el siguiente ejemplo se quitan todas las credenciales de Cloud Connector almacenadas en caché en el servidor host, se solicita al usuario que vuelva a especificar toda la información de credenciales y, a continuación, se instala Cloud Connector:
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a>Ejemplo 4

En el siguiente ejemplo se muestran todos los pasos de implementación en la consola de PowerShell:
  
```powershell
Install-CcAppliance -ShowStepsOnly
```

El parámetro -ShowStepsOnly es solo para solucionar problemas.
  
### <a name="example-5"></a>Ejemplo 5

En el siguiente ejemplo se generan archivos de configuración para cada paso de implementación en el servidor host. Los archivos de configuración se guardan en \< la carpeta ApplianceRoot \> \Instances \\<Version \> -default\ExportedConfig en el servidor host:
  
```powershell
Install-CcAppliance -PrepareOnly
```

Para determinar la raíz del dispositivo, ejecute el cmdlet Get-CcApplianceDirectory aplicación. 
  
### <a name="example-6"></a>Ejemplo 6

En el siguiente ejemplo, Cloud Connector ejecuta los pasos de implementación 1, 2 y 3 para crear conmutadores virtuales, crear una máquina virtual de AD e instalar el servicio de dominio en el servidor de AD. Omite el paso si el paso ya se ha ejecutado:
  
```powershell
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

El parámetro SkipExistingObjects debe usarse junto con el parámetro Steps.
  
> [!NOTE]
> El parámetro Steps es solo para solucionar problemas. No use este parámetro para implementar un dispositivo o para actualizar un dispositivo que esté en servicio. 
  
Para determinar los pasos de la implementación, ejecute el siguiente comando:
  
Install-CcAppliance -ShowStepsOnly
  
## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

El cmdlet Install-CcAppliance se usa para implementar Cloud Connector en un nuevo dispositivo o para actualizar un dispositivo existente a la versión más reciente.
  
Si tiene un nuevo dispositivo, asegúrese de leer primero Prepare your environment for Cloud Connector, ejecute el cmdlet Register-CcAppliance para registrar el dispositivo y, a continuación, ejecute el cmdlet Install-CcAppliance. Para obtener más información, vea [Implementar un único sitio en Cloud Connector](deploy-a-single-site-in-cloud-connector.md) e implementar varios sitios en Cloud [Connector.](deploy-multiple-sites-in-cloud-connector.md) 
  
Si ya tiene una implementación de Cloud Connector y desea actualizar, siga las instrucciones de Actualización a una nueva versión [de Cloud Connector.](upgrade-to-a-new-version-of-cloud-connector.md)
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Required**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|PrepareOnly  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> | Generar archivos de configuración para cada paso de implementación. Este parámetro es solo para solucionar problemas. <br/> |
|ShowStepsOnly  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Mostrar solo nombres de pasos de implementación. Este parámetro es solo para solucionar problemas.  <br/> |
|SkipExistingObjects  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Este parámetro debe usarse junto con el parámetro Steps. Este parámetro es solo para solucionar problemas.  <br/> |
|Pasos  <br/> |Opcional  <br/> |System.Array  <br/> |Ejecute los pasos de implementación. Este parámetro es solo para solucionar problemas.  <br/> |
|Actualización  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Actualice Cloud Connector existente a la versión más reciente.  <br/> |
|UpdateAllCredentials  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Quite todas las credenciales de Cloud Connector en la memoria caché. Pida al usuario que especifique la nueva información de credenciales para la instalación.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El Install-CcAppliance no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Vea también
<a name="ReturnTypes"> </a>

[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

