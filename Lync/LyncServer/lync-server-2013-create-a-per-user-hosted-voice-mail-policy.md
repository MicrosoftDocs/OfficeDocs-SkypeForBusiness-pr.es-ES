---
title: 'Lync Server 2013: crear una directiva de correo de voz hospedado por usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a per-user hosted voice mail policy
ms:assetid: 39018a7c-e0c3-46a2-be4e-05604ec67a50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425867(v=OCS.15)
ms:contentKeyID: 48183902
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d09638c28c1cbd2b068972aff169376508325885
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="7fa0f-102">Crear una directiva de correo de voz hospedada por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fa0f-102">Create a per-user hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7fa0f-103">_**Última modificación del tema:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="7fa0f-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="7fa0f-104">Una directiva *por usuario* solo puede afectar a usuarios individuales, grupos y objetos de contacto.</span><span class="sxs-lookup"><span data-stu-id="7fa0f-104">A *per-user* policy can only impact individual users, groups, and contact objects.</span></span> <span data-ttu-id="7fa0f-105">Para implementar una directiva por usuario, debe asignarla explícitamente a uno o más usuarios, grupos o objetos de contacto.</span><span class="sxs-lookup"><span data-stu-id="7fa0f-105">To deploy a per-user policy, you must explicitly assign the policy to one or more users, groups, or contact objects.</span></span> <span data-ttu-id="7fa0f-106">Para obtener más información, vea [asignar una directiva de correo de voz hospedado por usuario en Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span><span class="sxs-lookup"><span data-stu-id="7fa0f-106">For details, see [Assign a per-user hosted voice mail policy in Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span></span>

<span data-ttu-id="7fa0f-107">Para obtener más información sobre cómo trabajar con directivas de correo de voz hospedado por usuario, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="7fa0f-107">For details about working with per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="7fa0f-108">Nuevo: CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="7fa0f-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="7fa0f-109">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="7fa0f-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="7fa0f-110">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="7fa0f-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="7fa0f-111">Para crear una directiva de correo de voz hospedado por usuario</span><span class="sxs-lookup"><span data-stu-id="7fa0f-111">To create a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="7fa0f-112">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="7fa0f-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="7fa0f-113">Ejecute el cmdlet New-CsHostedVoicemailPolicy para crear la Directiva.</span><span class="sxs-lookup"><span data-stu-id="7fa0f-113">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy.</span></span> <span data-ttu-id="7fa0f-114">Por ejemplo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7fa0f-114">For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="7fa0f-115">En el ejemplo anterior se crea una directiva de correo de voz hospedada con ámbito por usuario y se establecen los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="7fa0f-115">The previous example creates a hosted voice mail policy with per-user scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="7fa0f-116">**Identity** especifica un identificador único para la Directiva, que incluye el ámbito.</span><span class="sxs-lookup"><span data-stu-id="7fa0f-116">**Identity** specifies a unique identifier for the policy, which includes the scope.</span></span> <span data-ttu-id="7fa0f-117">Para una directiva con ámbito por usuario, este valor de parámetro se especifica como una cadena simple, por ejemplo, en mi Redmond.</span><span class="sxs-lookup"><span data-stu-id="7fa0f-117">For a policy with per-user scope, this parameter value is specified as a simple string, for example, ExRedmond.</span></span>
    
      - <span data-ttu-id="7fa0f-118">**Destino** especifica el nombre de dominio completo (FQDN) del servicio de mensajería unificada de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="7fa0f-118">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="7fa0f-119">Este parámetro es opcional, pero si intenta habilitar un usuario para el correo de voz hospedado y la directiva asignada al usuario no tiene un valor de destino, se producirá un error de habilitar.</span><span class="sxs-lookup"><span data-stu-id="7fa0f-119">This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="7fa0f-120">**Descripción** proporciona información descriptiva opcional sobre la Directiva.</span><span class="sxs-lookup"><span data-stu-id="7fa0f-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="7fa0f-121">**Organización** especifica una lista separada por comas de los inquilinos de Exchange que alojan los usuarios de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7fa0f-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="7fa0f-122">Cada inquilino debe especificarse como el FQDN de ese inquilino en el servicio de mensajería unificada de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="7fa0f-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7fa0f-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="7fa0f-123">See Also</span></span>


[<span data-ttu-id="7fa0f-124">Asignar una directiva de correo de voz hospedado por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fa0f-124">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

