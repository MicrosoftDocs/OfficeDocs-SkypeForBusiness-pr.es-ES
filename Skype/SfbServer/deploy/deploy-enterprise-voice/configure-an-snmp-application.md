---
title: Configuración de una aplicación SNMP en Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Configurar una aplicación SNMP para que funcione con E9-1-1 en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: f45666708b2f5bb3065631bbb4ab38ee88082517
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898602"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>Configuración de una aplicación SNMP en Skype para Business Server
 
Configurar una aplicación SNMP para que funcione con E9-1-1 en Skype para Business Server Enterprise Voice. 
  
Skype para Business Server incluye una interfaz de servicio web estándar que puede usar para conectar el servicio de información de ubicación para las aplicaciones de Protocolo Simple de administración de redes (SNMP) que coincidan con las direcciones MAC con puerto e información de conmutadores. 
  
Si se instala una aplicación SNMP y se produce un error en el servicio de información de ubicación buscar a una coincidencia en la base de datos de ubicación, el servicio de información de ubicación consulta automáticamente la aplicación mediante el uso de la dirección MAC proporcionada por el cliente. El servicio de información de ubicación, a continuación, utiliza la información de puerto y el modificador devuelta por la aplicación SNMP para volver a consultar la base de datos de ubicación.
  
> [!NOTE]
> Las direcciones MAC no están disponibles en equipos que ejecutan Windows 8. 
  
### <a name="to-configure-the-snmp-application-url"></a>Para configurar la dirección URL de la aplicación SNMP:

1.  Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Ejecute el cmdlet siguiente para configurar la dirección URL para la aplicación SNMP. 
    
   ```
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>Consulte también

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

