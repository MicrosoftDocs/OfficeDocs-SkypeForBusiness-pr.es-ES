---
title: Configurar una aplicación SNMP en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Configurar una aplicación SNMP para E9-1-1 en Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: 5c10d00e05979c2a3e0efff015da61e5ff2c6ee9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-an-snmp-application-in-skype-for-business-server-2015"></a>Configurar una aplicación SNMP en Skype Empresarial Server 2015
 
Configurar una aplicación SNMP para E9-1-1 en Skype para Telefonía IP empresarial de Business Server. 
  
Skype para Business Server incluye una interfaz de servicios web estándar que puede utilizar para conectar el servicio de información de ubicación a las aplicaciones de Simple Network Management Protocol (SNMP) que coincidan con las direcciones MAC con puerto y cambie la información. 
  
Si se instala una aplicación SNMP y se produce un error en el servicio de información de ubicación encontrar a una coincidencia en la base de datos de ubicación, el servicio de información de ubicación consulta automáticamente la aplicación mediante la dirección MAC proporcionada por el cliente. El servicio de información de ubicación, a continuación, utiliza la información de puerto y switch devuelve la aplicación SNMP para volver a consultar la base de datos de ubicación.
  
> [!NOTE]
> Las direcciones MAC no están disponibles en equipos que ejecutan Windows 8. 
  
### <a name="to-configure-the-snmp-application-url"></a>Para configurar la dirección URL de la aplicación SNMP:

1.  Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Ejecute el cmdlet siguiente para configurar la dirección URL para la aplicación SNMP. 
    
   ```
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>Vea también

#### 

[Conjunto de CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

