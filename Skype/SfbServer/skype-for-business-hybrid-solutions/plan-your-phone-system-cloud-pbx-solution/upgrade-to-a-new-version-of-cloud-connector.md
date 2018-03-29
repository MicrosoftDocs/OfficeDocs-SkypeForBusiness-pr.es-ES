---
title: Actualizar a una versión nueva de Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Obtenga información sobre cómo actualizar su implementación de nube conector Edition.
ms.openlocfilehash: 0538b5d43c6e11aa11f7d265e43eb5f283e2b74e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>Actualizar a una versión nueva de Cloud Connector
 
Obtenga información sobre cómo actualizar su implementación de nube conector Edition.
  
Si ha configurado una cuenta de inquilino de administración en línea y ha habilitado las actualizaciones automáticas, la implementación existente de Skype Empresarial Cloud Connector Edition se actualizará a la versión más reciente automáticamente de acuerdo con la configuración de tiempo de la actualización automática. También puede realizar una actualización manual.  
  
Versiones de conector Edition 1.4.1 en nube y posteriormente realicen actualizaciones automáticas de forma predeterminada. Si desea actualizar a la versión más reciente (2.1) manualmente, vea [actualizar un único sitio a una nueva versión](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) más adelante en este tema.
  
Actualización automática requiere que se está ejecutando el servicio del conector de la nube. Los siguientes pasos describen el proceso de las actualizaciones automáticas:
  
- El proceso de actualización automática se ejecutará de acuerdo con el programa que haya configurado para las actualizaciones automáticas.
    
- Tareas de actualización del sistema operativo
    
  - Comprobar y descargar actualizaciones del sistema operativo en todas las máquinas virtuales de conector de nube. 
    
  - Instalar y actualizar todas las máquinas virtuales de nube conector uno por uno y reiniciar.
    
  - Después de reiniciar las máquinas virtuales de conector de nube, compruebe si es necesario volver a reiniciar.
    
  - Después de las VMs de nube conector haya correctamente revisado, repita el proceso con el equipo host de conector de nube.
    
  - Después de que el equipo host de nube conector correctamente inicia, se completan las tareas de actualización excelente sistema operativo.
    
- Las tareas de actualización del conector de la nube
    
  - Descargue y compruebe el archivo de la versión desde el sitio de descargas.
    
  - Descargue el nuevo archivo .msi.  
    
  - Desinstalar el antiguo archivo msi; instalar el nuevo archivo msi.
    
  - Descargue la nueva versión de Skype para los bits de negocios.
    
  - Registre el dispositivo llamando a Register-CcAppliance.
    
  - Instale la nueva versión del conector de la nube.
    
  - Depure el antiguo dispositivo y cambie la conexión de red al nuevo dispositivo.
    
> [!NOTE]
>  Cuando el conector de nube se actualiza a una nueva compilación, cmdlets de conector de nube podría no actualizarse. Esto puede suceder, por ejemplo, si se deja abierta una ventana de PowerShell mientras se produce la actualización automática. Para cargar los cmdlets actualizados, puede hacer cualquiera de los siguientes pasos: > Cerrar PowerShell en el dispositivo conector de nube y volver a abrirla PowerShell. > o bien, puede ejecutar Import-Module CloudConnector-Force.
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>Actualizar un sitio único a una versión nueva
<a name="BKMK_Upgrade"> </a>

Si solo hay una aplicación en el sitio que desea actualizar, realice lo siguiente:
  
1. Desinstale la versión existente de la nube de conector de **Panel de Control \> programas \> programas y características**.
    
2. Instalar la nueva versión de CloudConnector.msi de [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).
    
3. Confirme que tiene el archivo CloudConnector.ini para la versión que va a instalar y que ha actualizado todos los valores requeridos para su entorno. No puede usar el archivo .ini de una versión anterior. Si va a actualizar el conector de nube, por favor, consulte el tema de [Preparar el dispositivo conector de nube](prepare-your-cloud-connector-appliance.md) y asegúrese de nombreDeSitio y EnableReferSupport se establecen en el valor correcto en el archivo CloudConnector.ini.
    
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
  
Si desea actualizar el Administrador de dominio, Administrador de Virtual machine, Administrador de modo seguro y credenciales de administrador de inquilinos, puede ejecutar el cmdlet con el parámetro _UpdateAllCredentials_ para restablecer todas las credenciales:
  
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

Siga los pasos para actualizar un sitio único, para actualizar un sitio cada vez para cada sitio de la implementación. Asegúrese de que y [validar la implementación de nube conector](validate-your-cloud-connector-deployment.md) después de la actualización de cada sitio.
  

