---
title: Comprobar replicación en el dominio
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para comprobar la replicación de la preparación del dominio que se ha realizado en el paso 1: Preparar el esquema, es necesario ejecutar un cmdlet desde el Shell de administración de Lync Server de Skype Empresarial Server. Para ejecutar el cmdlet Windows PowerShell, inicie sesión en un equipo que sea miembro del dominio que ha preparado y como miembro del grupo Administradores de dominio. Haga lo siguiente:'
ms.openlocfilehash: 9ec39551702e0f3480671787536929863cb61f6b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801660"
---
# <a name="verify-replication-in-the-domain"></a>Comprobar replicación en el dominio
 
Para comprobar la replicación de la preparación del dominio que se ha realizado en el paso **1:** Preparar el esquema, es necesario ejecutar un cmdlet desde el Shell de administración de Lync Server de Skype Empresarial Server. Para ejecutar el cmdlet Windows PowerShell, inicie sesión en un equipo que sea miembro del dominio que ha preparado y como miembro del grupo Administradores de dominio. Haga lo siguiente:
  
1. Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** en **Skype** Empresarial y, a continuación, en Shell de administración de Skype Empresarial **Server.**
    
2. En Windows PowerShell, escriba lo siguiente:
    
   ```PowerShell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    Por ejemplo:
    
   ```PowerShell
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > El parámetro GlobalSettingsDomainController permite indicar dónde se guarda la configuración global. Si la configuración se almacena en el contenedor del sistema (lo que es típico con las implementaciones de actualización que no han migrado la configuración global al contenedor de configuración), debe definir un controlador de dominio en la raíz del bosque de Servicios de dominio de Active Directory. Si la configuración global se encuentra en el contenedor de configuración (habitual en implementaciones nuevas o de actualización en las que la configuración se ha migrado al contenedor de configuración), deberá definir cualquier controlador de dominio en el bosque. Si no especifica este parámetro, el cmdlet asume que la configuración se almacena en el contenedor de configuración y hace referencia a cualquier controlador de dominio de Active Directory. 
  
    Si no especifica el parámetro de dominio, el valor se configura con el dominio local. Este cmdlet devuelve un valor de **LC_DOMAIN_SETTINGS_STATE_READY** si la preparación del dominio se ha realizado correctamente.
    

