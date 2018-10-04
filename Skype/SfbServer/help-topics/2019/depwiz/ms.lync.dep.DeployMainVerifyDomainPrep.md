---
title: Comprobar replicación en el dominio
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para comprobar la replicación de la preparación del dominio lleva a cabo en el paso 1: preparar el esquema, es necesario ejecutar un cmdlet desde el Skype para Business Server Management Shell de Lync Server Management Shell. Para ejecutar el cmdlet de Windows PowerShell, inicie sesión en un equipo que sea miembro del dominio que ha preparado y como un miembro del grupo Administradores del dominio. Siga este procedimiento:'
ms.openlocfilehash: f5cf028cfb0957d339a2ac2a40a239f0c145a2c0
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373516"
---
# <a name="verify-replication-in-the-domain"></a>Comprobar replicación en el dominio
 
Para comprobar la replicación de la preparación del dominio lleva a cabo en **paso 1: preparar el esquema**, es necesario ejecutar un cmdlet desde el Skype para Business Server Management Shell de Lync Server Management Shell. Para ejecutar el cmdlet de Windows PowerShell, inicie sesión en un equipo que sea miembro del dominio que ha preparado y como un miembro del grupo Administradores del dominio. Siga este procedimiento:
  
1. Iniciar el Skype para Shell de administración de negocio Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para la empresa**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**.
    
2. En Windows PowerShell, escriba lo siguiente:
    
   ```
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    Por ejemplo:
    
   ```
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > El parámetro GlobalSettingsDomainController permite indicar dónde se guarda la configuración global. Si la configuración se almacena en el contenedor del sistema (que es típico con las implementaciones de actualización que no tengan la configuración global migrado al contenedor de configuración), se define un controlador de dominio en la raíz de su bosque de los servicios de dominio de Active Directory. Si la configuración global se encuentra en el contenedor de configuración (habitual en implementaciones nuevas o de actualización en las que la configuración se ha migrado al contenedor de configuración), necesitará definir cualquier controlador de dominio en el bosque. Si no especifica este parámetro, el cmdlet da por sentado que la configuración se guarda en el contenedor de configuración y hace referencia a cualquier controlador de dominio de Active Directory. 
  
    Si no especifica el parámetro de dominio, el valor se configura con el dominio local. Este cmdlet devuelve un valor de **LC_DOMAIN_SETTINGS_STATE_READY** si la preparación del dominio se realizó correctamente.
    

