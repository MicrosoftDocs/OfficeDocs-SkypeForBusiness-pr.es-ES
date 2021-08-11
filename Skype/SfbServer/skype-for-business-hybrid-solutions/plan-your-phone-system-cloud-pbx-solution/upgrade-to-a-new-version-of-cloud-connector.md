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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Obtenga información sobre cómo actualizar la implementación de Cloud Connector Edition.
ms.openlocfilehash: 2670557f3f5ab44545c511b759971a457bd37e333d01b323ad6cc35d82526858
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279976"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>Actualizar a una versión nueva de Cloud Connector

> [!Important]
> Cloud Connector Edition se retirará el 31 de julio de 2021 junto con Skype Empresarial Online. Una vez que la organización haya actualizado a Teams, obtenga información sobre cómo conectar la red de telefonía local a Teams enrutamiento [directo](/MicrosoftTeams/direct-routing-landing-page).
 
Obtenga información sobre cómo actualizar la implementación de Cloud Connector Edition.
  
Si ha configurado una cuenta de inquilino de administración en línea y ha habilitado actualizaciones automáticas, la implementación existente de Skype for Business Edición de conector de nube se actualizará a la versión más reciente automáticamente, según la configuración de la ventana de tiempo de actualización automática. También puede realizar una actualización manual. 
  
Cloud Connector Edition versiones 1.4.1 y posteriores realizan actualizaciones automáticas de forma predeterminada. Si desea actualizar manualmente a la versión más reciente (2.1), consulte [Upgrade a single site to a new version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) later in this topic.
  
La actualización automática requiere que se esté ejecutando el servicio de Cloud Connector. En los pasos siguientes se describe el proceso de actualizaciones automáticas:
  
- El proceso de actualización automática se ejecutará según la programación que haya configurado para las actualizaciones automáticas.
    
- Tareas de actualización del sistema operativo
    
  - Compruebe y descargue las actualizaciones del sistema operativo en todas las máquinas virtuales de Cloud Connector. 
    
  - Instale y actualice todas las máquinas virtuales de Cloud Connector una por una y reinicie.
    
  - Después de reiniciar las máquinas virtuales de Cloud Connector, compruebe si se necesita otro reinicio.
    
  - Una vez que las máquinas virtuales de Cloud Connector se hayan parcheado correctamente, repita el proceso para el equipo host de Cloud Connector.
    
  - Después de que la máquina host de Cloud Connector se inicie correctamente, se completan las tareas pendientes de actualización del sistema operativo.
    
- Tareas de actualización de Cloud Connector
    
  - Descargue y compruebe el archivo de versión desde el sitio de descarga.
    
  - Descargue la nueva versión .msi archivo. 
    
  - Desinstale el archivo msi antiguo; instalar el nuevo archivo msi.
    
  - Descargue la nueva versión de Skype Empresarial bits.
    
  - Registre el dispositivo llamando a Register-CcAppliance.
    
  - Instale la nueva versión de Cloud Connector.
    
  - Drene el dispositivo antiguo y cambie la conexión de red al nuevo dispositivo.
    
> [!NOTE]
>  Cuando Cloud Connector se actualiza en una nueva compilación, es posible que los cmdlets de Cloud Connector no se actualicen. Esto puede suceder, por ejemplo, si una ventana de PowerShell se deja abierta mientras se produce la actualización automática. Para cargar los cmdlets actualizados, puede realizar uno de los siguientes pasos:> Cerrar PowerShell en el dispositivo de Cloud Connector y, a continuación, volver a abrir PowerShell.> O bien, puede ejecutar Import-Module CloudConnector -Force.
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>Actualizar un solo sitio a una nueva versión
<a name="BKMK_Upgrade"> </a>

Si solo hay un dispositivo en el sitio que desea actualizar, haga lo siguiente:
  
1. Desinstale la versión existente de Cloud Connector en **Programas y características del Panel de \> \> control.**
    
2. Instale la nueva versión de CloudConnector.msi desde [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .
    
3. Confirme que tiene el archivo CloudConnector.ini para la versión que va a instalar y que ha actualizado todos los valores necesarios para su entorno. No puede usar el archivo .ini de una versión anterior. Si va a actualizar Cloud Connector, consulte el tema Prepare [your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) y asegúrese de que SiteName y EnableReferSupport están establecidos en el valor correcto en el archivo CloudConnector.ini.
    
4. Inicie una consola de PowerShell como administrador y ejecute el siguiente cmdlet para registrar el dispositivo actual:
    
   ```powershell
   Register-CcAppliance
   ```

5. Ejecute el siguiente cmdlet para descargar la versión más reciente:
    
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

Si hay más de un dispositivo en el sitio, siga los pasos anteriores para actualizar cada dispositivo uno por uno.
  
Si desea actualizar las credenciales de administrador de dominio, de máquina virtual, de modo Caja fuerte y de administrador de inquilinos, puede ejecutar el cmdlet con el parámetro _UpdateAllCredentials_ para restablecer todas las credenciales:
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

A continuación, cuando empiece a actualizar a una nueva versión, se le promoverá para que introduzca las nuevas credenciales. 
  
Si solo desea restablecer las credenciales de administrador de inquilinos, ejecute el siguiente cmdlet:
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a>Actualizar varios sitios a una nueva versión
<a name="BKMK_Upgrade"> </a>

Siga los pasos para actualizar un solo sitio y actualizar un sitio a la vez para cada sitio de la implementación. Asegúrese de validar [la implementación de Cloud Connector después](validate-your-cloud-connector-deployment.md) de actualizar cada sitio.
