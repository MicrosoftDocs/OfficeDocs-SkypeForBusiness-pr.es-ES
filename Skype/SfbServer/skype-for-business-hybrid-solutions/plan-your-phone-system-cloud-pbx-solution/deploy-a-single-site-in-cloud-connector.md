---
title: Implementar un solo sitio en Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom:
- Strat_SB_Hybrid
- Strat_SB_Hybrid
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: Obtenga información acerca de la implementación de un único sitio PSTN en nube conector Edition.
ms.openlocfilehash: 6268a9207d36e89faf391ac77a7dd832ba65704f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-a-single-site-in-cloud-connector"></a>Implementar un solo sitio en Cloud Connector
 
Obtenga información acerca de la implementación de un único sitio PSTN en nube conector Edition.
  
Puede implementar Skype para conector de nube Business Edition con o sin soporte de alta disponibilidad (HA). Si desea habilitar HA, tendrá que implementar dos o más dispositivos dentro de un sitio. También puede convertir un dispositivo existente para que admita HA después de su implementación.
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a>Implementar el primer dispositivo de Skype Empresarial Cloud Connector Edition

Para implementar la primera aplicación en un sitio, abra una consola de PowerShell como administrador y ejecute el siguiente cmdlet para registrar la aplicación:
  
```
Register-CcAppliance
```

Siga las instrucciones para proporcionar el nombre y la contraseña de la cuenta de administrador de inquilinos. Use la cuenta que creó para la administración en línea de Cloud Connector. Además, siga las instrucciones para proporcionar la contraseña del certificado externo, la del administrador de modo seguro, la del administrador de dominio y la del administrador de máquinas virtuales. 
 
  
En versión 1.4.2 y versiones anteriores, también, siga las instrucciones para proporcionar la contraseña de certificado externo, contraseña de admin de modo seguro, contraseña de administrador de dominio y contraseña de administrador de la máquina virtual. 
  
En la versión 2.0 y las versiones posteriores, siga también las instrucciones para proporcionar la contraseña del certificado externo, la contraseña de CceService y la contraseña de CABackupFile.
  
Para iniciar la instalación, abra una consola de PowerShell como administrador y ejecute el siguiente cmdlet:
  
```
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a>Agregar una aplicación a un sitio existente

Puede extender un sitio existente de conector de nube para admitir alta disponibilidad agregando dispositivos adicionales para el sitio. 
  
1. Siga los pasos para preparar el dispositivo conector de nube como se describe en [Preparar el dispositivo conector de nube](prepare-your-cloud-connector-appliance.md). Tenga en cuenta que algunos pasos solo se requieren para el primer dispositivo de la implementación. Confirme que exista el directorio del sitio y que esté configurado correctamente para la compatibilidad con HA.
    
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
> Si el directorio de sitios se ha establecido en la ruta de acceso a una carpeta local, tiene que definir un recurso compartido de archivos para esta carpeta y usar una ruta de acceso UNC para el directorio de sitios en el nuevo dispositivo. Puede dejar el directorio de sitios del primer dispositivo con la ruta de acceso local o modificarla para usar la ruta de acceso UNC para el recurso compartido en la misma carpeta. Si modifica la ubicación del directorio de sitios del recurso compartido, tendrá que desinstalar y volver a instalar después los dispositivos que se hayan instalado previamente. > Importante: La contraseña de la cuenta CceService y la cuenta de CABackupFile debe ser el mismo en todos los equipos implementados en el sitio, para que los dispositivos pueden acceder a la cuota de directorio de sitio y el archivo de copia de seguridad de entidad emisora de certificados cifrado en el directorio de sitios. 
  
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


