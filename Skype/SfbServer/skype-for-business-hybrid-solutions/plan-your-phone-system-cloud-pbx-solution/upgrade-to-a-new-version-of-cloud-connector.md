---
title: Actualizar a una versión nueva de Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Obtenga más información sobre cómo actualizar la implementación de Cloud Connector Edition.
ms.openlocfilehash: c340b7325c95d25212c9c1f77f9379a25708cea8
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002050"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>Upgrade to a new version of Cloud Connector
 
Obtenga más información sobre cómo actualizar la implementación de Cloud Connector Edition.
  
Si ha configurado una cuenta de inquilino de administración en línea y ha habilitado las actualizaciones automáticas, la implementación existente de Skype Empresarial Cloud Connector Edition se actualizará a la versión más reciente automáticamente de acuerdo con la configuración de tiempo de la actualización automática. También puede realizar una actualización manual.  
  
En la versión 1.4.1 y en la versión del conector en la nube se realizan actualizaciones automáticas de forma predeterminada. Si desea actualizar de forma manual la versión más reciente (2,1), vea [actualizar un único sitio a una nueva versión](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) más adelante en este tema.
  
La actualización automática requiere que el servicio de conector de nube se esté ejecutando. Los siguientes pasos describen el proceso de las actualizaciones automáticas:
  
- El proceso de actualización automática se ejecutará de acuerdo con el programa que haya configurado para las actualizaciones automáticas.
    
- Tareas de actualización del sistema operativo
    
  - Comprobar y descargar actualizaciones del sistema operativo para todas las máquinas virtuales de Cloud Connector. 
    
  - Instale y actualice todas las máquinas virtuales de conector de nube una por una y reinicie.
    
  - Después de reiniciar la MV del conector de nube, compruebe si es necesario otro reinicio.
    
  - Después de que se hayan revisado correctamente las máquinas virtuales del conector de nube, repita el proceso para el equipo host del conector de nube.
    
  - Una vez que el host del conector de nube se inicia correctamente, se completan las tareas pendientes de actualización del sistema operativo.
    
- Tareas de actualización del conector en la nube
    
  - Descargue y compruebe el archivo de la versión desde el sitio de descargas.
    
  - Descargue el nuevo archivo .msi.  
    
  - Desinstale el archivo MSI antiguo; Instale el nuevo archivo MSI.
    
  - Descargue la nueva versión de Skype for Business bits.
    
  - Registre el dispositivo llamando a Register-CcAppliance.
    
  - Instale la nueva versión de conector de nube.
    
  - Depure el antiguo dispositivo y cambie la conexión de red al nuevo dispositivo.
    
> [!NOTE]
>  Cuando el conector de nube se actualiza a una nueva compilación, es posible que los cmdlets de conector de nube no se actualicen. Esto puede suceder, por ejemplo, si se deja abierta una ventana de PowerShell mientras se produce la actualización automática. Para cargar los cmdlets actualizados, puede realizar cualquiera de los pasos siguientes: > cerrar PowerShell en el dispositivo de conector de nube y, a continuación, vuelva a abrir PowerShell. > o bien, puede ejecutar Import-Module CloudConnector-Force.
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>Actualizar un sitio único a una versión nueva
<a name="BKMK_Upgrade"> </a>

Si solo hay un dispositivo en el sitio que desea actualizar, realice lo siguiente:
  
1. Desinstalar la versión del conector de nube existente en el **panel \> de control \> programas programas y características**.
    
2. Instale la nueva versión de CloudConnector. msi de [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).
    
3. Confirme que tiene el archivo CloudConnector.ini para la versión que va a instalar y que ha actualizado todos los valores requeridos para su entorno. No puede usar el archivo .ini de una versión anterior. Si está actualizando Cloud Connector, consulte el tema [preparar el dispositivo de conexión en la nube](prepare-your-cloud-connector-appliance.md) y asegúrese de que el valor de NombreDeSitio y EnableReferSupport está establecido en el valor correcto en el archivo CloudConnector. ini.
    
4. Inicie una consola de PowerShell como administrador y ejecute el siguiente cmdlet para registrar el dispositivo actual:
    
   ```powershell
   Register-CcAppliance
   ```

5. Ejecute el siguiente cmdlet para registrar la última versión:
    
   ```powershell
   Start-CcDownload
   ```

6. Ejecute el siguiente cmdlet para iniciar la instalación:  
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. Ejecute el siguiente cmdlet para activar la nueva implementación y desactivar la versión anterior:
    
   ```powershell
   Switch-CcVersion
   ```

Si hay más de un dispositivo en el sitio, siga los pasos anteriores para actualizar cada dispositivo de uno en uno.
  
Si desea actualizar el administrador de dominio, administrador de máquina virtual, credenciales de administrador de modo seguro y administrador de inquilinos, puede ejecutar el cmdlet con el parámetro _UpdateAllCredentials_ para restablecer todas las credenciales:
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

Después, cuando comience a actualizar a una nueva versión, podrá introducir las nuevas credenciales.  
  
Si solo desea restablecer las credenciales de administrador de inquilinos, ejecute el siguiente cmdlet:
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a>Actualizar varios sitios a una versión nueva
<a name="BKMK_Upgrade"> </a>

Siga los pasos para actualizar un sitio único, para actualizar un sitio cada vez para cada sitio de la implementación. Asegúrese de realizar la [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) después de actualizar cada sitio.
  

