---
title: 'Lync Server 2013: crear una directiva de correo de voz hospedado de nivel de sitio'
description: 'Lync Server 2013: crear una directiva de correo de voz hospedado en el nivel de sitio.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a site-level hosted voice mail policy
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398216(v=OCS.15)
ms:contentKeyID: 48183481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cd578359a8d20562e8887b61b86d53332e6f8d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578376"
---
# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="56635-103">Crear una directiva de correo de voz hospedado de nivel de sitio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56635-103">Create a site-level hosted voice mail policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56635-104">_**Última modificación del tema:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="56635-104">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="56635-p101">Una directiva del *sitio* puede afectar a todos los usuarios del sitio en el que la directiva en cuestión está definida. En caso de que un usuario esté configurado para tener acceso a la mensajería unificada de Exchange hospedada y no tenga asignada una directiva específica de usuario, se aplicará la directiva del sitio y, si no hay una directiva del sitio implementada, se usará la directiva global.</span><span class="sxs-lookup"><span data-stu-id="56635-p101">A *site* policy can impact all users that are homed on the site for which the policy is defined. If a user is configured for hosted Exchange UM access and has not been assigned a Per-user policy, the site policy applies. If you have not deployed a site policy, the global policy applies.</span></span>

<span data-ttu-id="56635-108">Para obtener más información sobre cómo configurar directivas de sitio, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="56635-108">For details about configuring site policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="56635-109">New-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="56635-109">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="56635-110">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="56635-110">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="56635-111">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="56635-111">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a><span data-ttu-id="56635-112">Para crear una directiva de correo de voz hospedado del sitio</span><span class="sxs-lookup"><span data-stu-id="56635-112">To create a site hosted voice mail policy</span></span>

1.  <span data-ttu-id="56635-113">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="56635-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="56635-p102">Ejecute el cmdlet New-CsHostedVoicemailPolicy para crear la directiva. Por ejemplo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="56635-p102">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy. For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="56635-116">Con este ejemplo se crea una directiva de correo de voz hospedado con ámbito de sitio y se establecen los parámetros descritos a continuación:</span><span class="sxs-lookup"><span data-stu-id="56635-116">This example creates a hosted voice mail policy with site scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="56635-117">**Identity** hace referencia a un identificador único de la directiva, en el que se incluye el ámbito.</span><span class="sxs-lookup"><span data-stu-id="56635-117">**Identity** specifies a unique identifier for the policy, which includes the scope.</span></span> <span data-ttu-id="56635-118">Para una directiva con ámbito de sitio, el valor del parámetro Identity debe especificarse en el formato `site:` *\<name\>* , por ejemplo, `site:Redmond` .</span><span class="sxs-lookup"><span data-stu-id="56635-118">For a policy with site scope, the Identity parameter value must be specified in the format `site:`*\<name\>*, for example, `site:Redmond`.</span></span>
    
      - <span data-ttu-id="56635-p104">**Destination** especifica el nombre de dominio completo (FQDN) del servicio de mensajería unificada de Exchange hospedado. Este parámetro es opcional pero, si trata de habilitar a un usuario para el correo de voz hospedado y la directiva asignada al usuario no tiene ningún valor de Destination, no podrá habilitarlo.</span><span class="sxs-lookup"><span data-stu-id="56635-p104">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service. This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="56635-121">**Description** ofrece información descriptiva opcional acerca de la directiva.</span><span class="sxs-lookup"><span data-stu-id="56635-121">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="56635-122">**Organization** especifica una lista separada por comas de los inquilinos de Exchange que alojan a los usuarios de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="56635-122">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="56635-123">Cada arrendatario se debe especificar como el FQDN del arrendatario en cuestión en el servicio de mensajería unificada de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="56635-123">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

