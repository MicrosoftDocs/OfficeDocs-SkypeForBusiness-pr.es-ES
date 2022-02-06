---
title: Comprobar replicación en el dominio
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
  - ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
f1.keywords:
  - CSH
ms.localizationpriority: medium
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
ROBOTS: 'NOINDEX, NOFOLLOW'
description: 'Para comprobar la replicación de la preparación del dominio que se ha realizado en step 1: Prepare Schema, es necesario ejecutar un cmdlet desde el Shell de administración de Skype Empresarial Server Shell de administración de Lync Server. Para ejecutar el cmdlet Windows PowerShell, inicie sesión en un equipo que sea miembro del dominio que haya preparado y como miembro del grupo Administradores de dominio. Haga lo siguiente:'
---

# <a name="verify-replication-in-the-domain"></a>Comprobar replicación en el dominio
 
Para comprobar la replicación de la preparación del dominio que se ha realizado en **step 1: Prepare Schema**, es necesario ejecutar un cmdlet desde el Shell de administración de Skype Empresarial Server Shell de administración de Lync Server. Para ejecutar el cmdlet Windows PowerShell, inicie sesión en un equipo que sea miembro del dominio que haya preparado y como miembro del grupo Administradores de dominio. Haga lo siguiente:
  
1. Inicie el Shell Skype Empresarial Server administración: haga clic en **Inicio, todos** los **programas,** haga clic en **Skype Empresarial** y, a continuación, haga clic **Skype Empresarial Server Shell de administración**.
    
2. En Windows PowerShell, escriba lo siguiente:
    
   ```PowerShell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    Por ejemplo:
    
   ```PowerShell
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > El parámetro GlobalSettingsDomainController permite indicar dónde se guarda la configuración global. Si la configuración se almacena en el contenedor del sistema (lo que es típico con las implementaciones de actualización que no han migrado la configuración global al contenedor de configuración), se define un controlador de dominio en la raíz del bosque de servicios de dominio de Active Directory. Si la configuración global se encuentra en el contenedor de configuración (habitual en implementaciones nuevas o de actualización en las que la configuración se ha migrado al contenedor de configuración), deberá definir cualquier controlador de dominio en el bosque. Si no especifica este parámetro, el cmdlet asume que la configuración se almacena en el contenedor de configuración y hace referencia a cualquier controlador de dominio de Active Directory. 
  
    Si no especifica el parámetro de dominio, el valor se configura con el dominio local. Este cmdlet devuelve un valor de **LC_DOMAIN_SETTINGS_STATE_READY** si la preparación del dominio se ha realizado correctamente.
    

