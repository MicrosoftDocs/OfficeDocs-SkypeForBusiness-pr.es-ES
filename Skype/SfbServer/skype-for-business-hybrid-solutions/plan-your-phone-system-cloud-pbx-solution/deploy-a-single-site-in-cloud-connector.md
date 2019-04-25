---
title: Implementar un solo sitio en Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: Obtenga información sobre la implementación de un único sitio de RTC en la nube conector Edition.
ms.openlocfilehash: 667637fdf7dd42df64c4fdf9aca6b20931da188d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32227932"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a>Deploy a single site in Cloud Connector
 
Obtenga información sobre la implementación de un único sitio de RTC en la nube conector Edition.
  
Puede implementar Skype para Business Edition de conector en la nube con o sin compatibilidad con alta disponibilidad (HA). Si desea habilitar HA, tendrá que implementar dos o más dispositivos dentro de un sitio. También puede convertir un dispositivo existente para que admita HA después de su implementación.
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a>Implementar el primer dispositivo de Skype Empresarial Cloud Connector Edition

Para implementar la primera aplicación en un sitio, abra una consola de PowerShell como administrador y ejecute el siguiente cmdlet para registrar la aplicación:
  
```
Register-CcAppliance
```

Siga las instrucciones para proporcionar el nombre y la contraseña de la cuenta de administrador de inquilinos. Use la cuenta que creó para la administración en línea de Cloud Connector. Además, siga las instrucciones para proporcionar la contraseña del certificado externo, la del administrador de modo seguro, la del administrador de dominio y la del administrador de máquinas virtuales. 
 
  
En la versión 1.4.2 y versiones anteriores, también, siga las instrucciones para proporcionar la contraseña de certificado externo, contraseña de administrador de modo seguro, contraseña de administrador de dominio y contraseña de administrador de la máquina virtual. 
  
En la versión 2.0 y versiones posteriores, también, siga las instrucciones para proporcionar la contraseña de certificado externo, contraseña CceService y CABackupFile.
  
Para iniciar la instalación, abra una consola de PowerShell como administrador y ejecute el siguiente cmdlet:
  
```
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a>Agregar una aplicación a un sitio existente

Puede ampliar un sitio existente de conector en la nube para admitir alta disponibilidad mediante la adición de dispositivos adicionales para el sitio. 
  
1. Siga los pasos para preparar el dispositivo conector en la nube, tal y como se describe en [Preparar el dispositivo de conector en la nube](prepare-your-cloud-connector-appliance.md). Tenga en cuenta que algunos pasos solo se requieren para el primer dispositivo de la implementación. Confirme que exista el directorio del sitio y que esté configurado correctamente para la compatibilidad con HA.
    
2. Ejecute el siguiente cmdlet solo en un servidor host recién agregado para actualizar la información de topología en la configuración de inquilino de Office 365. Si desea agregar varios dispositivos al mismo tiempo, ejecute el cmdlet en cada uno de los hosts recién agregados, uno por uno:
    
   ```
   Register-CcAppliance
   ```

3. Actualice la topología en los dispositivos existentes ejecutando el siguiente cmdlet en cada servidor host. Solo ejecute el cmdlet en los dispositivos existentes.
    
   ```
   Publish-CcAppliance
   ```

4. Ejecute el siguiente cmdlet solo en servidores host recién agregados. No ejecute este cmdlet en el dispositivo existente. Si desea agregar varios dispositivos al mismo tiempo, ejecute el cmdlet en cada uno de los hosts recién agregados, uno por uno.
    
   ```
   Install-CcAppliance
   ```

> [!NOTE]
> Si el directorio de sitios se ha establecido en la ruta de acceso a una carpeta local, tiene que definir un recurso compartido de archivos para esta carpeta y usar una ruta de acceso UNC para el directorio de sitios en el nuevo dispositivo. Puede dejar el directorio de sitios del primer dispositivo con la ruta de acceso local o modificarla para usar la ruta de acceso UNC para el recurso compartido en la misma carpeta. Si modifica la ubicación del directorio de sitios del recurso compartido, tendrá que desinstalar y volver a instalar después los dispositivos que se hayan instalado previamente. > importante: la contraseña de la cuenta CceService y la cuenta de CABackupFile debe ser el mismo en todos los dispositivos que se implementan en el sitio, por lo que pueden tener acceso a los dispositivos el recurso compartido de directorio de sitios y el archivo de copia de seguridad cifrado de entidad emisora de certificados en el directorio de sitios. 
  
## <a name="remove-an-appliance-from-an-existing-site"></a>Quitar una aplicación de un sitio existente

Si desea quitar una aplicación de un sitio existente:
  
1. Ejecute el siguiente cmdlet solo en los servidores host que desee quitar del sitio para actualizar la información de topología en la configuración de inquilino de Office 365.
    
   ```
   Unregister-CcAppliance
   ```

2. Ejecute el siguiente cmdlet solo en los servidores host de los que desee quitar todas las máquinas virtuales del dispositivo.
    
   ```
   Uninstall-CcAppliance
   ```


