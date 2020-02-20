---
title: 'Lync Server 2013: crear una directiva de correo de voz hospedado por usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a per-user hosted voice mail policy
ms:assetid: 39018a7c-e0c3-46a2-be4e-05604ec67a50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425867(v=OCS.15)
ms:contentKeyID: 48183902
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e13002fa83215c5c1aade627cb6e7ea86cf0a04
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150699"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="5ce2d-102">Crear una directiva de correo de voz hospedado por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ce2d-102">Create a per-user hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ce2d-103">_**Última modificación del tema:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="5ce2d-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="5ce2d-104">Una directiva *por usuario* solo puede afectar a usuarios individuales, grupos y objetos de contacto.</span><span class="sxs-lookup"><span data-stu-id="5ce2d-104">A *per-user* policy can only impact individual users, groups, and contact objects.</span></span> <span data-ttu-id="5ce2d-105">Para implementar una directiva por usuario, debe asignar explícitamente la directiva a uno o varios usuarios, grupos u objetos de contacto.</span><span class="sxs-lookup"><span data-stu-id="5ce2d-105">To deploy a per-user policy, you must explicitly assign the policy to one or more users, groups, or contact objects.</span></span> <span data-ttu-id="5ce2d-106">Para obtener más información, consulte [asignar una directiva de correo de voz hospedado por usuario en Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span><span class="sxs-lookup"><span data-stu-id="5ce2d-106">For details, see [Assign a per-user hosted voice mail policy in Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span></span>

<span data-ttu-id="5ce2d-107">Para obtener información detallada sobre cómo trabajar con directivas de correo de voz hospedado por usuario, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="5ce2d-107">For details about working with per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="5ce2d-108">New-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="5ce2d-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="5ce2d-109">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="5ce2d-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="5ce2d-110">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="5ce2d-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="5ce2d-111">Para crear una directiva de correo de voz hospedado por usuario</span><span class="sxs-lookup"><span data-stu-id="5ce2d-111">To create a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="5ce2d-112">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="5ce2d-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="5ce2d-p102">Ejecute el cmdlet New-CsHostedVoicemailPolicy para crear la directiva. Por ejemplo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5ce2d-p102">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy. For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="5ce2d-115">En el ejemplo anterior se crea una directiva de correo de voz hospedado con un ámbito por usuario y se establecen los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="5ce2d-115">The previous example creates a hosted voice mail policy with per-user scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="5ce2d-p103">**Identity** hace referencia a un identificador único de la directiva, en el que se incluye el ámbito. En una directiva con ámbito por usuario, este valor de parámetro se especifica como una cadena sencilla, como por ejemplo, ExRedmond.</span><span class="sxs-lookup"><span data-stu-id="5ce2d-p103">**Identity** specifies a unique identifier for the policy, which includes the scope. For a policy with per-user scope, this parameter value is specified as a simple string, for example, ExRedmond.</span></span>
    
      - <span data-ttu-id="5ce2d-p104">**Destination** especifica el nombre de dominio completo (FQDN) del servicio de mensajería unificada de Exchange hospedado. Este parámetro es opcional pero, si trata de habilitar a un usuario para el correo de voz hospedado y la directiva asignada al usuario no tiene ningún valor de Destination, no podrá habilitarlo.</span><span class="sxs-lookup"><span data-stu-id="5ce2d-p104">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service. This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="5ce2d-120">**Description** ofrece información descriptiva opcional acerca de la directiva.</span><span class="sxs-lookup"><span data-stu-id="5ce2d-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="5ce2d-121">**Organization** especifica una lista separada por comas de los inquilinos de Exchange que alojan a los usuarios de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5ce2d-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="5ce2d-122">Cada arrendatario se debe especificar como el FQDN del arrendatario en cuestión en el servicio de mensajería unificada de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="5ce2d-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5ce2d-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ce2d-123">See Also</span></span>


[<span data-ttu-id="5ce2d-124">Asignar una directiva de correo de voz hospedado por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ce2d-124">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

