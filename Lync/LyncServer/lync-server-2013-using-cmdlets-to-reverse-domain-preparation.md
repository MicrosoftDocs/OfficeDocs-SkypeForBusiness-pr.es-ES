---
title: 'Lync Server 2013: Uso de cmdlets para revertir la preparación del dominio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using cmdlets to reverse domain preparation
ms:assetid: 014dba5d-fcb3-44c9-9d63-ae0755276dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398071(v=OCS.15)
ms:contentKeyID: 48183227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b03ab3218a1568613731efe60eaa95b05a91ebc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-domain-preparation-for-lync-server-2013"></a><span data-ttu-id="38e9f-102">Uso de cmdlets para revertir la preparación del dominio para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38e9f-102">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38e9f-103">_**Última modificación del tema:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="38e9f-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="38e9f-104">Use el cmdlet **Disable-CsAdDomain** para invertir el paso de preparación del dominio.</span><span class="sxs-lookup"><span data-stu-id="38e9f-104">Use the **Disable-CsAdDomain** cmdlet to reverse the domain preparation step.</span></span>

<div>

## <a name="to-use-cmdlets-to-reverse-domain-preparation"></a><span data-ttu-id="38e9f-105">Para usar los cmdlets para invertir la preparación del dominio</span><span class="sxs-lookup"><span data-stu-id="38e9f-105">To use cmdlets to reverse domain preparation</span></span>

1.  <span data-ttu-id="38e9f-106">Inicie sesión en cualquier servidor del dominio como miembro del grupo administradores de dominio.</span><span class="sxs-lookup"><span data-stu-id="38e9f-106">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="38e9f-107">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="38e9f-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="38e9f-108">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="38e9f-108">Run:</span></span>
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    <span data-ttu-id="38e9f-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="38e9f-109">For example:</span></span>
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    <span data-ttu-id="38e9f-110">Si el parámetro Force está presente, la preparación de dominio se revierte, incluso si se activan uno o varios servidores front-end o servidores de conferencia A/V en el dominio.</span><span class="sxs-lookup"><span data-stu-id="38e9f-110">If the Force parameter is present, domain preparation is rolled back, even if one or more Front End Servers or A/V Conferencing Servers in the domain are activated.</span></span> <span data-ttu-id="38e9f-111">Si el parámetro Force no está presente, la reversión de la preparación de dominios se finaliza si se activan los servidores front-end o los servidores de conferencia A/V del dominio.</span><span class="sxs-lookup"><span data-stu-id="38e9f-111">If the Force parameter is not present, domain preparation rollback is terminated if any Front End Servers or A/V Conferencing Servers in the domain are activated.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38e9f-112">El parámetro GlobalSettingsDomainController le permite indicar dónde se almacena la configuración global.</span><span class="sxs-lookup"><span data-stu-id="38e9f-112">The parameter GlobalSettingsDomainController allows you to indicate where global settings are stored.</span></span> <span data-ttu-id="38e9f-113">Si la configuración se almacena en el contenedor del sistema (que es habitual en las implementaciones de actualización en las que no se ha migrado la configuración global al contenedor de configuración), se define un controlador de dominio en la raíz del bosque de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="38e9f-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory forest.</span></span> <span data-ttu-id="38e9f-114">Si la configuración global se encuentra en el contenedor de configuración (habitual en implementaciones nuevas o de actualización en las que la configuración se ha migrado al contenedor de configuración), necesitará definir cualquier controlador de dominio en el bosque.</span><span class="sxs-lookup"><span data-stu-id="38e9f-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="38e9f-115">Si no especifica este parámetro, el cmdlet supone que la configuración se almacena en el contenedor de configuración y se refiere a cualquier controlador de dominio&nbsp;de AD DS.</span><span class="sxs-lookup"><span data-stu-id="38e9f-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in AD&nbsp;DS.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="38e9f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="38e9f-116">See Also</span></span>


[<span data-ttu-id="38e9f-117">Ejecutar la preparación del dominio para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38e9f-117">Running domain preparation for Lync Server 2013</span></span>](lync-server-2013-running-domain-preparation.md)  


[<span data-ttu-id="38e9f-118">Preparar dominios para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38e9f-118">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

