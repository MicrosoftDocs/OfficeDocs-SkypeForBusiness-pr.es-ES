---
title: 'Lync Server 2013: crear una directiva de correo de voz hospedado en el nivel de sitio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a site-level hosted voice mail policy
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398216(v=OCS.15)
ms:contentKeyID: 48183481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9df91e28eeba8bc9769e4fcbeff6ebba2b3746d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="86268-102">Crear una directiva de correo de voz hospedado en el nivel de sitio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86268-102">Create a site-level hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86268-103">_**Última modificación del tema:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="86268-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="86268-104">Una directiva de *sitio* puede afectar a todos los usuarios alojados en el sitio para el que se define la Directiva.</span><span class="sxs-lookup"><span data-stu-id="86268-104">A *site* policy can impact all users that are homed on the site for which the policy is defined.</span></span> <span data-ttu-id="86268-105">Si un usuario está configurado para el acceso a mensajería unificada de Exchange hospedado y no se le ha asignado una directiva por usuario, se aplicará la Directiva de sitio.</span><span class="sxs-lookup"><span data-stu-id="86268-105">If a user is configured for hosted Exchange UM access and has not been assigned a Per-user policy, the site policy applies.</span></span> <span data-ttu-id="86268-106">Si no ha implementado una directiva de sitio, se aplica la directiva global.</span><span class="sxs-lookup"><span data-stu-id="86268-106">If you have not deployed a site policy, the global policy applies.</span></span>

<span data-ttu-id="86268-107">Para obtener más información sobre cómo configurar directivas de sitio, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="86268-107">For details about configuring site policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="86268-108">Nuevo: CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="86268-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="86268-109">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="86268-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="86268-110">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="86268-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a><span data-ttu-id="86268-111">Para crear una directiva de correo de voz hospedada en un sitio</span><span class="sxs-lookup"><span data-stu-id="86268-111">To create a site hosted voice mail policy</span></span>

1.  <span data-ttu-id="86268-112">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="86268-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="86268-113">Ejecute el cmdlet New-CsHostedVoicemailPolicy para crear la Directiva.</span><span class="sxs-lookup"><span data-stu-id="86268-113">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy.</span></span> <span data-ttu-id="86268-114">Por ejemplo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="86268-114">For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="86268-115">En este ejemplo se crea una directiva de correo de voz hospedada con ámbito de sitio y se establecen los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="86268-115">This example creates a hosted voice mail policy with site scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="86268-116">**Identity** especifica un identificador único para la Directiva, que incluye el ámbito.</span><span class="sxs-lookup"><span data-stu-id="86268-116">**Identity** specifies a unique identifier for the policy, which includes the scope.</span></span> <span data-ttu-id="86268-117">Para una directiva con ámbito de sitio, el valor del parámetro Identity debe especificarse en `site:` \* \<el\>nombre\*de formato, `site:Redmond`por ejemplo,.</span><span class="sxs-lookup"><span data-stu-id="86268-117">For a policy with site scope, the Identity parameter value must be specified in the format `site:`*\<name\>*, for example, `site:Redmond`.</span></span>
    
      - <span data-ttu-id="86268-118">**Destino** especifica el nombre de dominio completo (FQDN) del servicio de mensajería unificada de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="86268-118">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="86268-119">Este parámetro es opcional, pero si intenta habilitar un usuario para el correo de voz hospedado y la directiva asignada al usuario no tiene un valor de destino, se producirá un error de habilitar.</span><span class="sxs-lookup"><span data-stu-id="86268-119">This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="86268-120">**Descripción** proporciona información descriptiva opcional sobre la Directiva.</span><span class="sxs-lookup"><span data-stu-id="86268-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="86268-121">**Organización** especifica una lista separada por comas de los inquilinos de Exchange que alojan los usuarios de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="86268-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="86268-122">Cada inquilino debe especificarse como el FQDN de ese inquilino en el servicio de mensajería unificada de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="86268-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

