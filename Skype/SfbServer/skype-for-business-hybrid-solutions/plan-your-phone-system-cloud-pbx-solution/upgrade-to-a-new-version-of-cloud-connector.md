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
> Cloud Connector Edition se retirará del 31 de julio de 2021 junto con Skype empresarial online. Una vez que la organización haya actualizado a Teams, obtenga información sobre cómo conectar la red de telefonía local a Microsoft Teams mediante el [enrutamiento directo](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).
 
Obtenga información sobre cómo actualizar la implementación de Cloud Connector Edition.
  
Si ha configurado una cuenta de inquilino de administración en línea y ha habilitado las actualizaciones automáticas, la implementación existente de Skype empresarial Cloud Connector Edition se actualizará automáticamente a la versión más reciente, de acuerdo con la configuración de la ventana de tiempo de actualización automática. También puede realizar una actualización manual. 
  
Cloud Connector Edition versiones 1.4.1 y posteriores realizan actualizaciones automáticas de forma predeterminada. Si desea actualizar a la versión más reciente (2,1) manualmente, vea [actualizar un único sitio a una nueva versión](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) , más adelante en este tema.
  
La actualización automática requiere que se esté ejecutando el servicio de Cloud Connector. En los pasos siguientes se describe el proceso para las actualizaciones automáticas:
  
- El proceso de actualización automática se ejecutará de acuerdo con la programación que haya configurado para las actualizaciones automáticas.
    
- Tareas de actualización del sistema operativo
    
  - Compruebe y descargue las actualizaciones del sistema operativo en todas las máquinas virtuales de Cloud Connector. 
    
  - Instale y actualice todas las máquinas virtuales de Cloud Connector una por una y reinicie.
    
  - Una vez reiniciados las máquinas virtuales de Cloud Connector, compruebe si es necesario reiniciar otro.
    
  - Una vez que se hayan revisado correctamente las máquinas virtuales de Cloud Connector, repita el proceso para el equipo host de Cloud Connector.
    
  - Una vez que el equipo host de Cloud Connector se inicie correctamente, se completan todas las tareas pendientes de actualización del sistema operativo.
    
- Tareas de actualización de Cloud Connector
    
  - Descargue y compruebe el archivo de la versión desde el sitio de descarga.
    
  - Descargue el nuevo archivo. msi de la versión. 
    
  - Desinstalar el antiguo archivo MSI; Instale el nuevo archivo MSI.
    
  - Descargue la nueva versión de bits de Skype empresarial.
    
  - Registre el dispositivo mediante una llamada a Register-CcAppliance.
    
  - Instale la nueva versión de Cloud Connector.
    
  - Vacíe el dispositivo antiguo y cambie la conexión de red al nuevo dispositivo.
    
> [!NOTE]
>  Cuando Cloud Connector se actualiza a una nueva compilación, es posible que los cmdlets de Cloud Connector no se actualicen. Esto puede ocurrir, por ejemplo, si se deja abierta una ventana de PowerShell mientras se produce la actualización automática. Para cargar los cmdlets actualizados, puede realizar cualquiera de los siguientes pasos: > cerrar PowerShell en el dispositivo de Cloud Connector y volver a abrir PowerShell. > o bien, puede ejecutar Import-Module CloudConnector-Force.
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>Actualizar un sitio único a una versión nueva
<a name="BKMK_Upgrade"> </a>

Si solo hay un dispositivo en el sitio que desea actualizar, haga lo siguiente:
  
1. Desinstalar la versión existente de Cloud Connector en el **Panel de control \> programas \> y características**.
    
2. Instale la nueva versión de CloudConnector.msi desde [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .
    
3. Confirme que tiene el archivo de CloudConnector.ini para la versión que va a instalar y que ha actualizado todos los valores necesarios para su entorno. No puede usar el archivo. ini de una versión anterior. Si va a actualizar Cloud Connector, consulte el tema [Prepare Your Cloud Connector Appliance](prepare-your-cloud-connector-appliance.md) y asegúrese de que NombreDeSitio y EnableReferSupport están configurados con el valor correcto en el archivo de CloudConnector.ini.
    
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

Si hay más de un dispositivo en el sitio, siga los pasos anteriores para actualizar cada dispositivo de uno en uno.
  
Si desea actualizar las credenciales de administrador de dominio, administrador de máquina virtual, administrador de modo seguro y administrador de inquilinos, puede ejecutar el cmdlet con el parámetro  _UpdateAllCredentials_ para restablecer todas las credenciales:
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

A continuación, cuando empiece la actualización a una nueva versión, se le promoverá para especificar las nuevas credenciales. 
  
Si solo desea restablecer las credenciales de administrador de inquilinos, ejecute el siguiente cmdlet:
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a>Actualización de varios sitios a una nueva versión
<a name="BKMK_Upgrade"> </a>

Siga los pasos para actualizar un sitio único, actualizando un sitio cada vez para cada sitio de la implementación. Asegúrese de que [valida la implementación de Cloud Connector](validate-your-cloud-connector-deployment.md) después de actualizar cada sitio.
  

