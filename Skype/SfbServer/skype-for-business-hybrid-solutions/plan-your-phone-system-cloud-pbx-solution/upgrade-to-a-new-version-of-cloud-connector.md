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
ms.openlocfilehash: dc9473dbf605f00df76daa1a88a29c7d5ed65fd8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359296"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>Actualizar a una versión nueva de Cloud Connector

> [!Important]
> Cloud Connector Edition se retirará el 31 de julio de 2021 junto con Skype Empresarial Online. Una vez que su organización haya actualizado a Teams, obtenga información sobre cómo conectar su red de telefonía local a Teams mediante [el enrutamiento directo.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)
 
Obtenga información sobre cómo actualizar la implementación de Cloud Connector Edition.
  
Si ha configurado una cuenta de inquilino de administración en línea y ha habilitado las actualizaciones automáticas, la implementación existente de Skype Empresarial Cloud Connector Edition se actualizará automáticamente a la versión más reciente, según la configuración de la ventana de tiempo de actualización automática. También puede realizar una actualización manual. 
  
Las versiones 1.4.1 y posteriores de Cloud Connector Edition realizan actualizaciones automáticas de forma predeterminada. Si desea actualizar manualmente a la última versión (2.1), consulte Actualizar un único sitio [a](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) una nueva versión más adelante en este tema.
  
La actualización automática requiere que se ejecute el servicio de Cloud Connector. Los siguientes pasos describen el proceso de actualizaciones automáticas:
  
- El proceso de actualización automática se ejecutará según la programación que haya configurado para las actualizaciones automáticas.
    
- Tareas de actualización del sistema operativo
    
  - Compruebe y descargue las actualizaciones del sistema operativo en todas las máquinas virtuales de Cloud Connector. 
    
  - Instale y actualice todas las máquinas virtuales de Cloud Connector una por una y reinicie.
    
  - Después de reiniciar las máquinas virtuales de Cloud Connector, compruebe si se necesita otro reinicio.
    
  - Una vez que las máquinas virtuales de Cloud Connector se hayan parcheado correctamente, repita el proceso para el equipo host de Cloud Connector.
    
  - Después de que el equipo host de Cloud Connector se inicie correctamente, se completan las tareas pendientes de actualización del sistema operativo.
    
- Tareas de actualización de Cloud Connector
    
  - Descargue y compruebe el archivo de versión del sitio de descarga.
    
  - Descargue el archivo .msi de la nueva versión. 
    
  - Desinstale el archivo msi antiguo; instalar el nuevo archivo msi.
    
  - Descargue la nueva versión de los bits de Skype Empresarial.
    
  - Registre el dispositivo llamando a Register-CcAppliance.
    
  - Instale la nueva versión de Cloud Connector.
    
  - Purga el dispositivo antiguo y cambia la conexión de red al nuevo dispositivo.
    
> [!NOTE]
>  Cuando Cloud Connector se actualiza a una nueva compilación, es posible que los cmdlets de Cloud Connector no se actualicen. Esto puede suceder, por ejemplo, si se deja abierta una ventana de PowerShell mientras se produce la actualización automática. Para cargar los cmdlets actualizados, puede realizar uno de los siguientes pasos: > Cerrar PowerShell en el dispositivo de Cloud Connector y, a continuación, volver a abrir PowerShell.> O bien, puede ejecutar Import-Module CloudConnector -Force.
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>Actualizar un único sitio a una nueva versión
<a name="BKMK_Upgrade"> </a>

Si solo hay un dispositivo en el sitio que desea actualizar, haga lo siguiente:
  
1. Desinstale la versión existente de Cloud Connector en Programas y características del Panel de **\> \> control.**
    
2. Instale la nueva versión de CloudConnector.msi [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) desde .
    
3. Confirme que tiene el archivo CloudConnector.ini para la versión que va a instalar y que ha actualizado todos los valores necesarios para su entorno. No puede usar el archivo .ini de una versión anterior. Si va a actualizar Cloud Connector, consulte el tema Prepare [your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) and make sure SiteName and EnableReferSupport are set to the correct value in the CloudConnector.ini file.
    
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
  
Si desea actualizar las credenciales de administrador de dominio, administrador de máquina virtual, administrador de modo seguro y administrador de inquilinos, puede ejecutar el cmdlet con el parámetro  _UpdateAllCredentials_ para restablecer todas las credenciales:
  
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

Siga los pasos para actualizar un solo sitio y actualizar un sitio cada vez para cada sitio de la implementación. Asegúrese de validar [la implementación de Cloud Connector después](validate-your-cloud-connector-deployment.md) de actualizar cada sitio.
  

