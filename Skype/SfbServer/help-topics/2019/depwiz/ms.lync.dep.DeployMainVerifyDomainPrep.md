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
# <a name="verify-replication-in-the-domain"></a><span data-ttu-id="a661d-105">Comprobar replicación en el dominio</span><span class="sxs-lookup"><span data-stu-id="a661d-105">Verify Replication in the Domain</span></span>
 
<span data-ttu-id="a661d-106">Para comprobar la replicación de la preparación del dominio que se ha realizado en el paso **1:** Preparar el esquema, es necesario ejecutar un cmdlet desde el Shell de administración de Lync Server de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="a661d-106">To verify replication of the domain preparation accomplished in **Step 1: Prepare Schema**, it is necessary to run a cmdlet from the Skype for Business Server Management Shell Lync Server Management Shell.</span></span> <span data-ttu-id="a661d-107">Para ejecutar el cmdlet Windows PowerShell, inicie sesión en un equipo que sea miembro del dominio que ha preparado y como miembro del grupo Administradores de dominio.</span><span class="sxs-lookup"><span data-stu-id="a661d-107">To run the Windows PowerShell cmdlet, log on to a computer that is a member of the domain that you have prepared, and as a member of the Domain Admins group.</span></span> <span data-ttu-id="a661d-108">Haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a661d-108">Do the following:</span></span>
  
1. <span data-ttu-id="a661d-109">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** en **Skype** Empresarial y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="a661d-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="a661d-110">En Windows PowerShell, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a661d-110">In Windows PowerShell, type the following:</span></span>
    
   ```PowerShell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    <span data-ttu-id="a661d-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a661d-111">For example:</span></span>
    
   ```PowerShell
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > <span data-ttu-id="a661d-112">El parámetro GlobalSettingsDomainController permite indicar dónde se guarda la configuración global.</span><span class="sxs-lookup"><span data-stu-id="a661d-112">The parameter GlobalSettingsDomainController enables you to indicate where global settings are stored.</span></span> <span data-ttu-id="a661d-113">Si la configuración se almacena en el contenedor del sistema (lo que es típico con las implementaciones de actualización que no han migrado la configuración global al contenedor de configuración), debe definir un controlador de dominio en la raíz del bosque de Servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a661d-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory Domain Services forest.</span></span> <span data-ttu-id="a661d-114">Si la configuración global se encuentra en el contenedor de configuración (habitual en implementaciones nuevas o de actualización en las que la configuración se ha migrado al contenedor de configuración), deberá definir cualquier controlador de dominio en el bosque.</span><span class="sxs-lookup"><span data-stu-id="a661d-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="a661d-115">Si no especifica este parámetro, el cmdlet asume que la configuración se almacena en el contenedor de configuración y hace referencia a cualquier controlador de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a661d-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="a661d-116">Si no especifica el parámetro de dominio, el valor se configura con el dominio local.</span><span class="sxs-lookup"><span data-stu-id="a661d-116">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> <span data-ttu-id="a661d-117">Este cmdlet devuelve un valor de **LC_DOMAIN_SETTINGS_STATE_READY** si la preparación del dominio se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="a661d-117">This cmdlet returns a value of **LC_DOMAIN_SETTINGS_STATE_READY** if domain preparation was successful.</span></span>
    

