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
localization_priority: Normal
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: 'El cmdlet Install-CcAppliance instala el dispositivo de Skype Empresarial Cloud Connector Edition, incluidas las máquinas virtuales de AD, del almacén de administración central, del servidor de mediación y del servidor perimetral en el servidor host. '
ms.openlocfilehash: cccf500c6506c8ba3459631d5c823940907ad213
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003330"
---
# <a name="install-ccappliance"></a>Install-CcAppliance
 
El cmdlet Install-CcAppliance instala el dispositivo de Skype Empresarial Cloud Connector Edition, incluidas las máquinas virtuales de AD, del almacén de administración central, del servidor de mediación y del servidor perimetral en el servidor host.  
  
```powershell
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

El siguiente ejemplo instala un nuevo dispositivo de conector de nube en el servidor host:
  
```powershell
Install-CcAppliance
```

### <a name="example-2"></a>Ejemplo 2

En el ejemplo siguiente se actualiza la versión más reciente del conector de nube:
  
```powershell
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a>Ejemplo 3

En el ejemplo siguiente se quitan todas las credenciales del conector de nube en caché en el servidor host, se pide al usuario que especifique nuevamente toda la información de credenciales y, a continuación, se instala el conector de nube:
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a>Ejemplo 4

En el siguiente ejemplo se muestran todos los pasos de implementación en la consola de PowerShell:
  
```powershell
Install-CcAppliance -ShowStepsOnly
```

El parámetro -ShowStepsOnly solo se usa para solucionar problemas.
  
### <a name="example-5"></a>Ejemplo 5

En el siguiente ejemplo se generan los archivos de configuración de cada paso de implementación en el servidor host. Los archivos de configuración se guardan\>en\\ la \<ApplianceRoot\>\Instances<default\ExportedConfig en el servidor host:
  
```powershell
Install-CcAppliance -PrepareOnly
```

Para determinar la raíz del dispositivo, ejecute el cmdlet Get-CcApplianceDirectory.  
  
### <a name="example-6"></a>Ejemplo 6

En el siguiente ejemplo, Cloud Connector ejecuta los pasos 1, 2 y 3 de la implementación para crear conmutadores virtuales, crear una máquina virtual de AD e instalar el servicio de dominio en el servidor de AD. Se omite el paso si este ya se ha ejecutado:
  
```powershell
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

El parámetro SkipExistingObjects debe usarse junto con el parámetro Steps.
  
> [!NOTE]
> El parámetro Steps solo se usa con fines de resolución de problemas. No use el parámetro para implementar un dispositivo o para actualizar un dispositivo que esté en el servicio. 
  
Para determinar los pasos de la implementación, ejecute el comando siguiente:
  
Install-CcAppliance -ShowStepsOnly
  
## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

El cmdlet install-CcAppliance se usa para implementar el conector de nube en un nuevo equipo o para actualizar un dispositivo existente a la versión más reciente.
  
Si tiene un dispositivo nuevo, asegúrese antes de leer Preparar el entorno para Cloud Connector, ejecute el cmdlet Register-CcAppliance para registrar el dispositivo y después ejecute el cmdlet Install-CcAppliance. Para obtener más información, consulte [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) y [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md). 
  
Si tiene una implementación existente del conector de nube y quiere actualizar, siga las instrucciones de [actualizar a una nueva versión de Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Requerida.**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|PrepareOnly  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |  Se generan archivos de configuración para cada paso de implementación. Este parámetro solo se usa para solucionar problemas.  <br/> |
|ShowStepsOnly  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Solo se muestran los nombres de los pasos de la implementación. Este parámetro solo se usa para solucionar problemas.  <br/> |
|SkipExistingObjects  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Este parámetro se debe usar junto con el parámetro Steps. Este parámetro solo se usa para solucionar problemas.  <br/> |
|Steps  <br/> |Opcional  <br/> |System.Array  <br/> |Se ejecutan los pasos de la implementación. Este parámetro solo se usa para solucionar problemas.  <br/> |
|Upgrade  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Cloud Connector se actualiza a la última versión.  <br/> |
|UpdateAllCredentials  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Quite todas las credenciales de conector de nube en la memoria caché. Se solicita al usuario que especifique toda la información de las credenciales nuevas para la instalación.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Install-CcAppliance no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

