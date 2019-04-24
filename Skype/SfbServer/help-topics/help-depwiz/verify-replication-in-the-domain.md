---
title: Comprobar replicación en el dominio
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
description: 'Para comprobar la replicación de la preparación del dominio lleva a cabo en el paso 1: preparar el esquema, es necesario ejecutar un cmdlet desde el Skype para Business Server Management Shell de Lync Server Management Shell. Para ejecutar el cmdlet de Windows PowerShell, inicie sesión en un equipo que sea miembro del dominio que ha preparado y como un miembro del grupo Administradores del dominio. Siga este procedimiento:'
ms.openlocfilehash: 32a5a315566fcee07f7214c980843829ef8e229f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234876"
---
# <a name="verify-replication-in-the-domain"></a><span data-ttu-id="199f2-105">Comprobar replicación en el dominio</span><span class="sxs-lookup"><span data-stu-id="199f2-105">Verify Replication in the Domain</span></span>
 
<span data-ttu-id="199f2-106">Para comprobar la replicación de la preparación del dominio lleva a cabo en **paso 1: preparar el esquema**, es necesario ejecutar un cmdlet desde el Skype para Business Server Management Shell de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="199f2-106">To verify replication of the domain preparation accomplished in **Step 1: Prepare Schema**, it is necessary to run a cmdlet from the Skype for Business Server Management Shell Lync Server Management Shell.</span></span> <span data-ttu-id="199f2-107">Para ejecutar el cmdlet de Windows PowerShell, inicie sesión en un equipo que sea miembro del dominio que ha preparado y como un miembro del grupo Administradores del dominio.</span><span class="sxs-lookup"><span data-stu-id="199f2-107">To run the Windows PowerShell cmdlet, log on to a computer that is a member of the domain that you have prepared, and as a member of the Domain Admins group.</span></span> <span data-ttu-id="199f2-108">Siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="199f2-108">Do the following:</span></span>
  
1. <span data-ttu-id="199f2-109">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="199f2-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="199f2-110">En Windows PowerShell, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="199f2-110">In Windows PowerShell, type the following:</span></span>
    
   ```
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    <span data-ttu-id="199f2-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="199f2-111">For example:</span></span>
    
   ```
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > <span data-ttu-id="199f2-112">El parámetro GlobalSettingsDomainController permite indicar dónde se guarda la configuración global.</span><span class="sxs-lookup"><span data-stu-id="199f2-112">The parameter GlobalSettingsDomainController enables you to indicate where global settings are stored.</span></span> <span data-ttu-id="199f2-113">Si la configuración se almacena en el contenedor del sistema (que es típico con las implementaciones de actualización que no tengan la configuración global migrado al contenedor de configuración), se define un controlador de dominio en la raíz de su bosque de los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="199f2-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory Domain Services forest.</span></span> <span data-ttu-id="199f2-114">Si la configuración global se encuentra en el contenedor de configuración (habitual en implementaciones nuevas o de actualización en las que la configuración se ha migrado al contenedor de configuración), necesitará definir cualquier controlador de dominio en el bosque.</span><span class="sxs-lookup"><span data-stu-id="199f2-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="199f2-115">Si no especifica este parámetro, el cmdlet da por sentado que la configuración se guarda en el contenedor de configuración y hace referencia a cualquier controlador de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="199f2-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="199f2-116">Si no especifica el parámetro de dominio, el valor se configura con el dominio local.</span><span class="sxs-lookup"><span data-stu-id="199f2-116">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> <span data-ttu-id="199f2-117">Este cmdlet devuelve un valor de **LC_DOMAIN_SETTINGS_STATE_READY** si la preparación del dominio se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="199f2-117">This cmdlet returns a value of **LC_DOMAIN_SETTINGS_STATE_READY** if domain preparation was successful.</span></span>
    

