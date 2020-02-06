---
title: Comprobar replicación en el dominio
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Para comprobar la replicación de la preparación del dominio que se realizó en el paso 1: preparar el esquema, es necesario ejecutar un cmdlet desde el shell de administración de Lync Server de Shell de administración de Skype empresarial. Para ejecutar el cmdlet de Windows PowerShell, inicie sesión en un equipo que sea miembro del dominio que ha preparado y como miembro del grupo administradores de dominio. Siga este procedimiento:'
ms.openlocfilehash: fffe6a227ad8a0dd0214080b21d743382845478b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794769"
---
# <a name="verify-replication-in-the-domain"></a>Comprobar replicación en el dominio
 
Para comprobar la replicación de la preparación del dominio que se realizó en el **paso 1: preparar el esquema**, es necesario ejecutar un cmdlet desde el shell de administración de Lync Server de Shell de administración de Skype empresarial. Para ejecutar el cmdlet de Windows PowerShell, inicie sesión en un equipo que sea miembro del dominio que ha preparado y como miembro del grupo administradores de dominio. Siga este procedimiento:
  
1. Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, haga clic en **todos los programas**, en **Skype empresarial**y, a continuación, haga clic en **consola de administración de Skype empresarial**.
    
2. En Windows PowerShell, escriba lo siguiente:
    
   ```PowerShell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    Por ejemplo:
    
   ```PowerShell
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > El parámetro GlobalSettingsDomainController permite indicar dónde se guarda la configuración global. Si la configuración se almacena en el contenedor del sistema (que es habitual en las implementaciones de actualización que no han tenido la configuración global migrada al contenedor de configuración), se define un controlador de dominio en la raíz del bosque de los servicios de dominio de Active Directory. Si la configuración global se encuentra en el contenedor de configuración (habitual en implementaciones nuevas o de actualización en las que la configuración se ha migrado al contenedor de configuración), necesitará definir cualquier controlador de dominio en el bosque. Si no especifica este parámetro, el cmdlet da por sentado que la configuración se guarda en el contenedor de configuración y hace referencia a cualquier controlador de dominio de Active Directory. 
  
    Si no especifica el parámetro de dominio, el valor se configura con el dominio local. Este cmdlet devuelve un valor de **LC_DOMAIN_SETTINGS_STATE_READY** si la preparación del dominio se ha realizado correctamente.
    

