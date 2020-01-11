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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: Obtenga información sobre cómo implementar un único sitio de RTC en Cloud Connector Edition.
ms.openlocfilehash: a2cc8933276bc85b19ee79559ca4bcf9e88a079f
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001030"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a>Deploy a single site in Cloud Connector
 
Obtenga información sobre cómo implementar un único sitio de RTC en Cloud Connector Edition.
  
Puede implementar Skype empresarial Cloud Connector Edition con compatibilidad o sin disponibilidad alta (HA). Si desea habilitar HA, tendrá que implementar dos o más dispositivos dentro de un sitio. También puede convertir un dispositivo existente para que admita HA después de su implementación.
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a>Implementar el primer dispositivo de Skype Empresarial Cloud Connector Edition

Para implementar la primera aplicación en un sitio, abra una consola de PowerShell como administrador y ejecute el siguiente cmdlet para registrar la aplicación:
  
```powershell
Register-CcAppliance
```

Siga las instrucciones para proporcionar el nombre y la contraseña de la cuenta de administrador de inquilinos. Use la cuenta que creó para la administración en línea de Cloud Connector. Además, siga las instrucciones para proporcionar la contraseña del certificado externo, la del administrador de modo seguro, la del administrador de dominio y la del administrador de máquinas virtuales. 
 
  
En la versión 1.4.2 y anterior, también puede seguir las instrucciones para proporcionar la contraseña del certificado externo, la contraseña del administrador en el modo seguro, la contraseña del administrador del dominio y la contraseña de administrador de la VM. 
  
En la versión 2,0 y posteriores, también puede seguir las instrucciones para proporcionar la contraseña del certificado externo, CceService contraseña y CABackupFile contraseña.
  
Para iniciar la instalación, abra una consola de PowerShell como administrador y ejecute el siguiente cmdlet:
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a>Agregar una aplicación a un sitio existente

Puede extender un sitio de conector de nube existente para que sea compatible con HA agregando dispositivos adicionales al sitio. 
  
1. Siga los pasos para preparar el dispositivo de conector de nube como se describe en [preparar el dispositivo de conector de nube](prepare-your-cloud-connector-appliance.md). Tenga en cuenta que algunos pasos solo se requieren para el primer dispositivo de la implementación. Confirme que exista el directorio del sitio y que esté configurado correctamente para la compatibilidad con HA.
    
2. Ejecute el siguiente cmdlet solo en un servidor host recién agregado para actualizar la información de topología en la configuración de inquilino de Office 365. Si desea agregar varios dispositivos al mismo tiempo, ejecute el cmdlet en cada uno de los hosts recién agregados, uno por uno:
    
   ```powershell
   Register-CcAppliance
   ```

3. Actualice la topología en los dispositivos existentes ejecutando el siguiente cmdlet en cada servidor host. Solo ejecute el cmdlet en los dispositivos existentes.
    
   ```powershell
   Publish-CcAppliance
   ```

4. Ejecute el siguiente cmdlet solo en servidores host recién agregados. No ejecute este cmdlet en el dispositivo existente. Si desea agregar varios dispositivos al mismo tiempo, ejecute el cmdlet en cada uno de los hosts recién agregados, uno por uno.
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> Si el directorio de sitios se ha establecido en la ruta de acceso a una carpeta local, tiene que definir un recurso compartido de archivos para esta carpeta y usar una ruta de acceso UNC para el directorio de sitios en el nuevo dispositivo. Puede dejar el directorio de sitios del primer dispositivo con la ruta de acceso local o modificarla para usar la ruta de acceso UNC para el recurso compartido en la misma carpeta. Si modifica la ubicación del directorio de sitios del recurso compartido, tendrá que desinstalar y volver a instalar después los dispositivos que se hayan instalado previamente. > importante: la contraseña de la cuenta de CceService y de la cuenta de CABackupFile debe ser la misma en todos los dispositivos instalados dentro del sitio, de modo que los dispositivos puedan acceder al recurso compartido de directorio de sitios y al archivo de copia de seguridad de la entidad emisora cifrada en el directorio de sitios. 
  
## <a name="remove-an-appliance-from-an-existing-site"></a>Quitar una aplicación de un sitio existente

Si desea quitar una aplicación de un sitio existente:
  
1. Ejecute el siguiente cmdlet solo en los servidores host que desee quitar del sitio para actualizar la información de topología en la configuración de inquilino de Office 365.
    
   ```powershell
   Unregister-CcAppliance
   ```

2. Ejecute el siguiente cmdlet solo en los servidores host de los que desee quitar todas las máquinas virtuales del dispositivo.
    
   ```powershell
   Uninstall-CcAppliance
   ```


