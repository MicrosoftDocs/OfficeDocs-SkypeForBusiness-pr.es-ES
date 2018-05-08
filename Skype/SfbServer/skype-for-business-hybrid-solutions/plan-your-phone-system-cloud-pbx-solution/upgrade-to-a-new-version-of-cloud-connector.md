---
title: Actualizar a una versión nueva de Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Obtenga información acerca de cómo actualizar su implementación de edición de conector en la nube.
ms.openlocfilehash: 925b19360115e74a147f8b32c6faa42b84971f60
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>Actualizar a una versión nueva de Cloud Connector
 
Obtenga información acerca de cómo actualizar su implementación de edición de conector en la nube.
  
Si ha configurado una cuenta de inquilino de administración en línea y ha habilitado las actualizaciones automáticas, la implementación existente de Skype Empresarial Cloud Connector Edition se actualizará a la versión más reciente automáticamente de acuerdo con la configuración de tiempo de la actualización automática. También puede realizar una actualización manual.  
  
En la nube de versiones de conector Edition 1.4.1 y posteriormente realicen actualizaciones automáticas de forma predeterminada. Si desea actualizar a la versión más reciente (2.1) manualmente, vea [actualizar un solo sitio a una nueva versión](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) más adelante en este tema.
  
Actualización automática requiere que se está ejecutando el servicio de conector en la nube. Los siguientes pasos describen el proceso de las actualizaciones automáticas:
  
- El proceso de actualización automática se ejecutará de acuerdo con el programa que haya configurado para las actualizaciones automáticas.
    
- Tareas de actualización del sistema operativo
    
  - Comprobar y descargar actualizaciones del sistema operativo en todas las máquinas virtuales de conector en la nube. 
    
  - Instalar y actualizar todas las máquinas virtuales de conector en la nube uno por uno y reiniciar.
    
  - Después de reiniciar el conector en la nube, las máquinas virtuales, compruebe si es necesario reiniciar otra.
    
  - Después de las máquinas virtuales de conector de nube haya correctamente revisado, repita el proceso para el equipo host de conector en la nube.
    
  - Después de que el equipo host de conector en la nube se inicia correctamente copia de seguridad, se completan las tareas de actualización de sistema operativo pendientes.
    
- Las tareas de actualización del conector de nube
    
  - Descargue y compruebe el archivo de la versión desde el sitio de descargas.
    
  - Descargue el nuevo archivo .msi.  
    
  - Desinstalar el archivo msi antiguo; Instale el nuevo archivo msi.
    
  - Descargue la versión nueva de Skype para bits de negocio.
    
  - Registre el dispositivo llamando a Register-CcAppliance.
    
  - Instalar la nueva versión de conector en la nube.
    
  - Depure el antiguo dispositivo y cambie la conexión de red al nuevo dispositivo.
    
> [!NOTE]
>  Cuando se actualiza el conector en la nube para una nueva compilación, no es posible que actualizarse cmdlets de conector en la nube. Esto puede suceder, por ejemplo, si se queda abierta una ventana de PowerShell mientras se produce la actualización automática. Para cargar los cmdlets actualizados, puede realizar cualquiera de los siguientes pasos: > Cerrar PowerShell en el dispositivo de conector en la nube y volver a abrirla PowerShell. > o bien, puede ejecutar Import-Module CloudConnector-Force.
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>Actualizar un sitio único a una versión nueva
<a name="BKMK_Upgrade"> </a>

Si solo hay una aplicación en el sitio que desea actualizar, realice lo siguiente:
  
1. Desinstale la versión existente de conector en la nube en **el Panel de Control \> programas \> programas y características**.
    
2. Instalar la nueva versión de CloudConnector.msi de [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).
    
3. Confirme que tiene el archivo CloudConnector.ini para la versión que va a instalar y que ha actualizado todos los valores requeridos para su entorno. No puede usar el archivo .ini de una versión anterior. Si va a actualizar el conector de la nube, por favor, consulte el tema [Prepare su dispositivo conector en la nube](prepare-your-cloud-connector-appliance.md) y asegúrese de que SiteName y EnableReferSupport se establecen en el valor correcto en el archivo CloudConnector.ini.
    
4. Inicie una consola de PowerShell como administrador y ejecute el siguiente cmdlet para registrar el dispositivo actual:
    
  ```
  Register-CcAppliance
  ```

5. Ejecute el siguiente cmdlet para registrar la última versión:
    
  ```
  Start-CcDownload
  ```

6. Ejecute el siguiente cmdlet para iniciar la instalación:  
    
  ```
  Install-CcAppliance -Upgrade
  ```

7. Ejecute el siguiente cmdlet para activar la nueva implementación y desactivar la versión anterior:
    
  ```
  Switch-CcVersion
  ```

Si hay más de un dispositivo en el sitio, siga los pasos anteriores para actualizar cada dispositivo de uno en uno.
  
Si desea actualizar el Administrador de dominio, el Administrador de la máquina Virtual, el Administrador de modo seguro y credenciales de administrador de inquilinos, puede ejecutar el cmdlet con el parámetro _UpdateAllCredentials_ para restablecer todas las credenciales:
  
```
Install-CcAppliance -UpdateAllCredentials
```

Después, cuando comience a actualizar a una nueva versión, podrá introducir las nuevas credenciales.  
  
Si solo desea restablecer las credenciales de administrador de inquilinos, ejecute el siguiente cmdlet:
  
```
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a>Actualizar varios sitios a una versión nueva
<a name="BKMK_Upgrade"> </a>

Siga los pasos para actualizar un sitio único, para actualizar un sitio cada vez para cada sitio de la implementación. Asegúrese de que y [validar la implementación del conector de nube](validate-your-cloud-connector-deployment.md) después de actualizar cada sitio.
  

