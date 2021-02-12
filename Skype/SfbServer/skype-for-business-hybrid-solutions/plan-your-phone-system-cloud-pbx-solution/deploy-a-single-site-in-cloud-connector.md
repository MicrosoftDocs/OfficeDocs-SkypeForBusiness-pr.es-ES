---
title: Implementar un solo sitio en Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: Obtenga información sobre cómo implementar un único sitio RTC en Cloud Connector Edition.
ms.openlocfilehash: 327fc4e687377f5f1338bea2f623b526511a2992
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358936"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a>Implementar un solo sitio en Cloud Connector
 
> [!Important]
> Cloud Connector Edition se retirará el 31 de julio de 2021 junto con Skype Empresarial Online. Una vez que su organización haya actualizado a Teams, obtenga información sobre cómo conectar su red de telefonía local a Teams mediante [el enrutamiento directo.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

Obtenga información sobre cómo implementar un único sitio RTC en Cloud Connector Edition.
  
Puede implementar Skype Empresarial Cloud Connector Edition con o sin compatibilidad con alta disponibilidad (HA). Si desea habilitar HA, deberá implementar dos o más dispositivos dentro de un sitio. También puede convertir un dispositivo existente para que admita HA después de implementarlo.
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a>Implementar el primer dispositivo de Skype Empresarial Cloud Connector Edition

Para implementar el primer dispositivo en un sitio, abra una consola de PowerShell como administrador y ejecute el siguiente cmdlet para registrar el dispositivo:
  
```powershell
Register-CcAppliance
```

Siga las instrucciones para proporcionar el nombre y la contraseña de la cuenta de administrador de inquilinos. Use la cuenta que ha creado para la administración en línea de Cloud Connector. Además, siga las instrucciones para proporcionar la contraseña del certificado externo, la contraseña de administrador de modo seguro, la contraseña de administrador de dominio y la contraseña de administrador de máquina virtual. 
  
En la versión 1.4.2 y versiones anteriores, también sigue las instrucciones para proporcionar la contraseña del certificado externo, la contraseña de administrador de modo seguro, la contraseña de administrador de dominio y la contraseña de administrador de máquina virtual. 
  
En la versión 2.0 y posteriores, siga también las instrucciones para proporcionar la contraseña del certificado externo, la contraseña de CceService y la contraseña caBackupFile.
  
Para iniciar la instalación, abra una consola de PowerShell como administrador y ejecute el siguiente cmdlet:
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a>Agregar un dispositivo a un sitio existente

Puede ampliar un sitio de Cloud Connector existente para admitir HA agregando dispositivos adicionales al sitio. 
  
1. Siga los pasos para preparar el dispositivo de Cloud Connector tal como se describe en [Preparar el dispositivo de Cloud Connector.](prepare-your-cloud-connector-appliance.md) Tenga en cuenta que solo es necesario realizar algunos pasos para el primer dispositivo de la implementación. Confirme que el directorio de sitios existe y está configurado correctamente para la compatibilidad con HA.
    
2. Ejecute el siguiente cmdlet solo en el servidor host recién agregado para actualizar la información de topología en la configuración de la organización de Microsoft 365 u Office 365. Si desea agregar varios dispositivos al mismo tiempo, ejecute el cmdlet en cada servidor host recién agregado uno por uno:
    
   ```powershell
   Register-CcAppliance
   ```

3. Actualice la topología en dispositivos existentes ejecutando el siguiente cmdlet en cada servidor host. Ejecute solo el cmdlet en los dispositivos existentes.
    
   ```powershell
   Publish-CcAppliance
   ```

4. Ejecute el siguiente cmdlet solo en servidores host recién agregados. No ejecute este cmdlet en el dispositivo existente. Si desea agregar varios dispositivos al mismo tiempo, ejecute el cmdlet en cada servidor host recién agregado uno por uno.
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> Si el directorio de sitios se estableció en una ruta de acceso de carpeta local, debe definir un recurso compartido de archivos para esta carpeta y usar una ruta de acceso UNC para el directorio de sitios en el nuevo dispositivo. Puede dejar el primer directorio de sitios del dispositivo con la ruta de acceso local o modificarlo para usar la ruta de acceso UNC para el recurso compartido en la misma carpeta. Si cambia la ubicación del directorio de sitios compartidos, todos los dispositivos instalados anteriormente deben desinstalarse y volver a instalarse. > Importante: La contraseña para la cuenta CceService y la cuenta CABackupFile debe ser la misma en todos los dispositivos implementados en el sitio, para que los dispositivos puedan tener acceso al recurso compartido del directorio de sitios y al archivo de copia de seguridad de ca cifrada en el directorio de sitios. 
  
## <a name="remove-an-appliance-from-an-existing-site"></a>Quitar un dispositivo de un sitio existente

Si desea quitar un dispositivo de un sitio existente:
  
1. Ejecute el siguiente cmdlet solo en los servidores host que desee quitar del sitio para actualizar la información de topología en la configuración de la organización de Microsoft 365 u Office 365.
    
   ```powershell
   Unregister-CcAppliance
   ```

2. Ejecute el siguiente cmdlet solo en los servidores host de los que desea quitar todas las máquinas virtuales del dispositivo.
    
   ```powershell
   Uninstall-CcAppliance
   ```


