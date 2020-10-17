---
title: 'Lync Server 2013: directivas de correo de voz hospedado'
description: 'Lync Server 2013: directivas de correo de voz hospedado.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted voice mail policies
ms:assetid: d62a35ed-cbe2-4f06-86b4-e192c18435c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398932(v=OCS.15)
ms:contentKeyID: 48185506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57461f4ffd2c6f2cd733dd7ec2c945c9e7b801c2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550106"
---
# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a><span data-ttu-id="418cc-103">Directivas de correo de voz hospedado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="418cc-103">Hosted voice mail policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="418cc-104">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="418cc-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="418cc-105">Una *Directiva de correo de voz hospedada* proporciona información a la aplicación de enrutamiento ExUM de Lync Server 2013 sobre dónde enrutar las llamadas de los usuarios cuyos buzones se encuentran en un servicio de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="418cc-105">A *hosted voice mail policy* provides information to the Lync Server 2013 ExUM Routing application about where to route calls for users whose mailboxes are located on a hosted Exchange service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="418cc-106">Las directivas de correo de voz hospedado solo son necesarias para la integración de Lync Server 2013 con mensajería unificada de Exchange hospedada.</span><span class="sxs-lookup"><span data-stu-id="418cc-106">Hosted voice mail policies are required only for Lync Server 2013 integration with hosted Exchange UM.</span></span> <span data-ttu-id="418cc-107">No son necesarias para la integración con la mensajería unificada local de Exchange.</span><span class="sxs-lookup"><span data-stu-id="418cc-107">They are not needed for integration with on-premises Exchange UM.</span></span>



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a><span data-ttu-id="418cc-108">Ámbito de directiva de correo de voz hospedado</span><span class="sxs-lookup"><span data-stu-id="418cc-108">Hosted Voice Mail Policy Scope</span></span>

<span data-ttu-id="418cc-p102">El ámbito de directiva de correo de voz hospedado determina el nivel jerárquico en que se aplica la directiva. Configure directivas de correo de voz hospedado con los niveles de ámbito siguientes:</span><span class="sxs-lookup"><span data-stu-id="418cc-p102">Hosted voice mail policy scope determines the hierarchical level at which the policy applies. You can configure hosted voice mail policies with the following scope levels:</span></span>

  - <span data-ttu-id="418cc-111">La directiva *global* puede afectar potencialmente a todos los usuarios de la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="418cc-111">The *global* policy can potentially affect all users in the Lync Server 2013 deployment.</span></span> <span data-ttu-id="418cc-112">Si un usuario está habilitado para el acceso a la mensajería unificada hospedada de Exchange y no se le ha asignado una directiva por usuario, y si no se ha asignado una directiva de sitio al sitio del usuario, se aplicará la directiva global.</span><span class="sxs-lookup"><span data-stu-id="418cc-112">If a user is enabled for hosted Exchange UM access and has not been assigned a per-user policy, and if a site policy has not been assigned to the user’s site, the global policy applies.</span></span> <span data-ttu-id="418cc-113">La directiva global se instala con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="418cc-113">The global policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="418cc-114">Modifíquela para adaptarla a sus necesidades, aunque no puede cambiarle el nombre ni eliminarla.</span><span class="sxs-lookup"><span data-stu-id="418cc-114">You can modify it to meet your needs, but you cannot rename or delete it.</span></span>

  - <span data-ttu-id="418cc-p104">Una directiva de *sitio* puede afectar a todos los usuarios que están hospedados en el sitio para el que se ha definido la directiva. Si un usuario está configurado para el acceso a la mensajería unificada hospedada de Exchange y no se le ha asignado una directiva por usuario, se aplicará la directiva de sitio.</span><span class="sxs-lookup"><span data-stu-id="418cc-p104">A *site* policy can affect all users that are homed on the site for which the policy is defined. If a user is configured for hosted Exchange UM access and has not been assigned a per-user policy, the site policy applies.</span></span>

  - <span data-ttu-id="418cc-p105">Una directiva *por usuario* solo afecta a grupos o usuarios individuales. Para aplicar una directiva por usuario, debe asignar de forma explícita la directiva a objetos de contacto, usuarios y grupos.</span><span class="sxs-lookup"><span data-stu-id="418cc-p105">A *per-user* policy can affect only individual users or groups. To enforce a per-user policy, you must explicitly assign the policy to individual users, groups, and contact objects.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="418cc-p106">En la mayoría de los casos, solo es necesaria una directiva de correo de voz hospedado. Por lo general, es posible modificar la directiva global para adaptarla a nuestras necesidades específicas. Si implementa varias directivas de correo de voz hospedado, todas estas directivas serán de ámbito por usuario.</span><span class="sxs-lookup"><span data-stu-id="418cc-p106">In most cases, only one hosted voice mail policy is required. You can often modify the global policy to meet all your needs. If you deploy multiple hosted voice mail policies, all such policies have per-user scope.</span></span>



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a><span data-ttu-id="418cc-122">Atributos de directiva de correo de voz hospedado</span><span class="sxs-lookup"><span data-stu-id="418cc-122">Hosted Voice Mail Policy Attributes</span></span>

<span data-ttu-id="418cc-123">Una directiva de correo de voz define dos atributos que la aplicación de enrutamiento ExUM de Lync Server 2013 inserta en el URI de solicitud de un mensaje INVITE que se envía a la implementación de la mensajería unificada de Exchange hospedada:</span><span class="sxs-lookup"><span data-stu-id="418cc-123">A voice mail policy defines two attributes that the Lync Server 2013 ExUM Routing application inserts in the request URI of an INVITE message that is sent to the hosted Exchange UM implementation:</span></span>

  - <span data-ttu-id="418cc-124">**Destino:** El nombre de dominio completo (FQDN) del servicio de mensajería unificada de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="418cc-124">**Destination:** The fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="418cc-125">Este valor se usa en el servidor perimetral de Lync Server local para fines de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="418cc-125">This value is used by the on-premises Lync Server Edge Server for routing purposes.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="418cc-126">El FQDN para Exchange Online es exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="418cc-126">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

    
    </div>

  - <span data-ttu-id="418cc-127">**Organización:** El FQDN del inquilino en el servicio de mensajería unificada de Exchange hospedado que aloja los buzones de correo de los usuarios de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="418cc-127">**Organization:** The FQDN of the tenant on the hosted Exchange UM service that homes your Lync Server 2013 users’ mailboxes.</span></span> <span data-ttu-id="418cc-128">Una directiva de correo de voz puede contener varias organizaciones.</span><span class="sxs-lookup"><span data-stu-id="418cc-128">A voice mail policy can contain multiple organizations.</span></span> <span data-ttu-id="418cc-129">Si se incluye más de una organización en la Directiva, este atributo debe ser una lista separada por comas de los inquilinos de Exchange Server que hospedan los buzones de usuario de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="418cc-129">If more than one organization is included in the policy, this attribute must be a comma-separated list of the Exchange Server tenants that home your Lync Server 2013 user mailboxes.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="418cc-p109">El administrador de arrendatarios del servicio de mensajería unificada hospedada de Exchange proporcionará los valores necesarios para la configuración de los atributos Destination y Organization. Para configurar su directiva, ejecute el cmdlet New-CsHostedVoicemailPolicy o use el cmdlet Set-CsHostedVoicemailPolicy para modificar una que ya exista (por ejemplo, la directiva global).</span><span class="sxs-lookup"><span data-stu-id="418cc-p109">The tenant administrator of your hosted Exchange UM service will provide the necessary values for your Destination and Organization attribute settings. To configure your policy, you must run the New-CsHostedVoicemailPolicy cmdlet or use the Set-CsHostedVoicemailPolicy cmdlet to modify one that exists (for example, the global policy).</span></span>



</div>

<span data-ttu-id="418cc-132">Para obtener información detallada sobre la administración de directivas de correo de voz hospedado, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="418cc-132">For details about managing hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="418cc-133">New-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="418cc-133">New-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="418cc-134">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="418cc-134">Set-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="418cc-135">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="418cc-135">Get-CsHostedVoicemailPolicy</span></span>

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a><span data-ttu-id="418cc-136">Asignación de directivas de correo de voz por usuario</span><span class="sxs-lookup"><span data-stu-id="418cc-136">Per-User Voice Mail Policy Assignment</span></span>

<span data-ttu-id="418cc-p110">Si su directiva de correo de voz hospedado se ha definido con el ámbito por usuario, asígnela de forma explícita. Puede ejecutar el cmdlet Grant-CsHostedVoicemailPolicy para asignar la directiva a grupos o usuarios individuales.</span><span class="sxs-lookup"><span data-stu-id="418cc-p110">If your hosted voice mail policy is defined with per-user scope, you must explicitly assign it. You can run the Grant-CsHostedVoicemailPolicy cmdlet to assign the policy to individual users or groups.</span></span>

<span data-ttu-id="418cc-139">Para obtener más información sobre cómo asignar o quitar una directiva de correo de voz hospedado por usuario, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="418cc-139">For details about assigning or removing a per-user hosted voice mail policy, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="418cc-140">Grant-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="418cc-140">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="418cc-141">Remove-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="418cc-141">Remove-CsHostedVoicemailPolicy</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

