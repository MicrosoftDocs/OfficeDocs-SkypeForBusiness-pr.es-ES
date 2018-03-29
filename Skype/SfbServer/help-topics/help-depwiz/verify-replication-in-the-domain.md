---
title: Comprobar replicación en el dominio
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
description: 'Para comprobar la replicación de la preparación del dominio lleva a cabo en el paso 1: preparar un esquema, es necesario ejecutar un cmdlet desde el Skype para Business Server Shell Lync Server Management el Shell de administración. Para ejecutar el cmdlet de Windows PowerShell, inicie sesión en un equipo que es miembro del dominio que ha preparado y como miembro del grupo Administradores de dominio. Siga este procedimiento:'
ms.openlocfilehash: e3dca892ccb4937bcd84148a954270b4bd1362f5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="verify-replication-in-the-domain"></a><span data-ttu-id="c6737-105">Comprobar replicación en el dominio</span><span class="sxs-lookup"><span data-stu-id="c6737-105">Verify Replication in the Domain</span></span>
 
<span data-ttu-id="c6737-106">Para comprobar la replicación de la preparación del dominio lleva a cabo en **paso 1: preparar el esquema**, es necesario ejecutar un cmdlet desde el Skype para Business Server Shell Lync Server Management el Shell de administración.</span><span class="sxs-lookup"><span data-stu-id="c6737-106">To verify replication of the domain preparation accomplished in **Step 1: Prepare Schema**, it is necessary to run a cmdlet from the Skype for Business Server Management Shell Lync Server Management Shell.</span></span> <span data-ttu-id="c6737-107">Para ejecutar el cmdlet de Windows PowerShell, inicie sesión en un equipo que es miembro del dominio que ha preparado y como miembro del grupo Administradores de dominio.</span><span class="sxs-lookup"><span data-stu-id="c6737-107">To run the Windows PowerShell cmdlet, log on to a computer that is a member of the domain that you have prepared, and as a member of the Domain Admins group.</span></span> <span data-ttu-id="c6737-108">Siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="c6737-108">Do the following:</span></span>
  
1. <span data-ttu-id="c6737-109">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="c6737-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="c6737-110">En Windows PowerShell, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c6737-110">In Windows PowerShell, type the following:</span></span>
    
  ```
  Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
  ```

    <span data-ttu-id="c6737-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c6737-111">For example:</span></span>
    
  ```
  Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
  ```

    > [!NOTE]
    > <span data-ttu-id="c6737-112">El parámetro GlobalSettingsDomainController permite indicar dónde se guarda la configuración global.</span><span class="sxs-lookup"><span data-stu-id="c6737-112">The parameter GlobalSettingsDomainController enables you to indicate where global settings are stored.</span></span> <span data-ttu-id="c6737-113">Si la configuración se almacena en el contenedor del sistema (que suele hacerse con la implementación de actualizaciones que no tengan la configuración global migrado al contenedor de configuración), se define un controlador de dominio en la raíz del bosque de servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c6737-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory Domain Services forest.</span></span> <span data-ttu-id="c6737-114">Si la configuración global se encuentra en el contenedor de configuración (habitual en implementaciones nuevas o de actualización en las que la configuración se ha migrado al contenedor de configuración), necesitará definir cualquier controlador de dominio en el bosque.</span><span class="sxs-lookup"><span data-stu-id="c6737-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="c6737-115">Si no especifica este parámetro, el cmdlet da por sentado que la configuración se guarda en el contenedor de configuración y hace referencia a cualquier controlador de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c6737-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="c6737-116">Si no especifica el parámetro de dominio, el valor se configura con el dominio local.</span><span class="sxs-lookup"><span data-stu-id="c6737-116">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> <span data-ttu-id="c6737-117">Este cmdlet devuelve un valor de **LC_DOMAIN_SETTINGS_STATE_READY** si la preparación del dominio se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="c6737-117">This cmdlet returns a value of **LC_DOMAIN_SETTINGS_STATE_READY** if domain preparation was successful.</span></span>
    

