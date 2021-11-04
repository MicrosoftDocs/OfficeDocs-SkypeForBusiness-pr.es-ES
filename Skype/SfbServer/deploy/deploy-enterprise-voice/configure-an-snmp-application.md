---
title: Configurar una aplicación SNMP en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Configure una aplicación SNMP para que funcione con E9-1-1 en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: b033a25d16e5f9ffae47111dbd0929441a735796
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741456"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>Configurar una aplicación SNMP en Skype Empresarial Server
 
Configure una aplicación SNMP para que funcione con E9-1-1 en Skype Empresarial Server Telefonía IP empresarial. 
  
Skype Empresarial Server incluye una interfaz de servicio web estándar que puede usar para conectar el servicio de información de ubicación a aplicaciones del Protocolo simple de administración de red (SNMP) que coinciden con las direcciones MAC con la información de puerto y cambio. 
  
Si se instala una aplicación SNMP y el servicio de información de ubicación no encuentra una coincidencia en la base de datos de ubicación, el servicio de información de ubicación consulta automáticamente la aplicación mediante la dirección MAC proporcionada por el cliente. A continuación, el servicio de información de ubicación usa el puerto y la información de cambio devuelta por la aplicación SNMP para consultar de nuevo la base de datos de ubicación.
  
> [!NOTE]
> Las direcciones MAC no están disponibles en equipos que ejecutan Windows 8. 
  
### <a name="to-configure-the-snmp-application-url"></a>Para configurar la dirección URL de la aplicación SNMP:

1.  Inicie el Shell Skype Empresarial Server administración: haga clic en Inicio **,** todos los programas **,** haga clic en **Skype Empresarial 2015** y, a continuación, haga clic **Skype Empresarial Server Shell de administración**.
    
2. Ejecute el cmdlet siguiente para configurar la dirección URL para la aplicación SNMP. 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>Consulte también

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)