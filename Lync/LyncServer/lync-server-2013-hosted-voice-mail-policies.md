---
title: 'Lync Server 2013: Directivas de correo de voz hospedado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted voice mail policies
ms:assetid: d62a35ed-cbe2-4f06-86b4-e192c18435c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398932(v=OCS.15)
ms:contentKeyID: 48185506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a23f5fa67a34d479bbc5b9d5c9bf55071b187c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a><span data-ttu-id="08a75-102">Directivas de correo de voz hospedado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08a75-102">Hosted voice mail policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08a75-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="08a75-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="08a75-104">Una *Directiva de correo de voz hospedada* proporciona información a la aplicación de enrutamiento de 2013 ExUM de Lync Server acerca de dónde enrutar las llamadas de los usuarios cuyos buzones se encuentran en un servicio de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="08a75-104">A *hosted voice mail policy* provides information to the Lync Server 2013 ExUM Routing application about where to route calls for users whose mailboxes are located on a hosted Exchange service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="08a75-105">Las directivas de correo de voz hospedado solo son necesarias para la integración de Lync Server 2013 con mensajería unificada de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="08a75-105">Hosted voice mail policies are required only for Lync Server 2013 integration with hosted Exchange UM.</span></span> <span data-ttu-id="08a75-106">No son necesarios para la integración con la mensajería unificada de Exchange local.</span><span class="sxs-lookup"><span data-stu-id="08a75-106">They are not needed for integration with on-premises Exchange UM.</span></span>



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a><span data-ttu-id="08a75-107">Ámbito de directiva de correo de voz hospedado</span><span class="sxs-lookup"><span data-stu-id="08a75-107">Hosted Voice Mail Policy Scope</span></span>

<span data-ttu-id="08a75-108">El ámbito de la Directiva de correo de voz hospedado determina el nivel jerárquico al que se aplica la Directiva.</span><span class="sxs-lookup"><span data-stu-id="08a75-108">Hosted voice mail policy scope determines the hierarchical level at which the policy applies.</span></span> <span data-ttu-id="08a75-109">Puede configurar directivas de correo de voz hospedado con los siguientes niveles de ámbito:</span><span class="sxs-lookup"><span data-stu-id="08a75-109">You can configure hosted voice mail policies with the following scope levels:</span></span>

  - <span data-ttu-id="08a75-110">La directiva *global* puede afectar potencialmente a todos los usuarios de la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="08a75-110">The *global* policy can potentially affect all users in the Lync Server 2013 deployment.</span></span> <span data-ttu-id="08a75-111">Si un usuario está habilitado para el acceso a la mensajería unificada de Exchange hospedado y no se le ha asignado una directiva por usuario, y si no se ha asignado una directiva de sitio al sitio del usuario, se aplicará la directiva global.</span><span class="sxs-lookup"><span data-stu-id="08a75-111">If a user is enabled for hosted Exchange UM access and has not been assigned a per-user policy, and if a site policy has not been assigned to the user’s site, the global policy applies.</span></span> <span data-ttu-id="08a75-112">La directiva global se instala con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="08a75-112">The global policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="08a75-113">Puede modificarla para satisfacer sus necesidades, pero no puede cambiarle el nombre ni eliminarla.</span><span class="sxs-lookup"><span data-stu-id="08a75-113">You can modify it to meet your needs, but you cannot rename or delete it.</span></span>

  - <span data-ttu-id="08a75-114">Una directiva de *sitio* puede afectar a todos los usuarios alojados en el sitio para el que se define la Directiva.</span><span class="sxs-lookup"><span data-stu-id="08a75-114">A *site* policy can affect all users that are homed on the site for which the policy is defined.</span></span> <span data-ttu-id="08a75-115">Si un usuario está configurado para el acceso a mensajería unificada de Exchange hospedado y no se le ha asignado una directiva por usuario, se aplicará la Directiva de sitio.</span><span class="sxs-lookup"><span data-stu-id="08a75-115">If a user is configured for hosted Exchange UM access and has not been assigned a per-user policy, the site policy applies.</span></span>

  - <span data-ttu-id="08a75-116">Una directiva *por usuario* solo puede afectar a usuarios individuales o grupos.</span><span class="sxs-lookup"><span data-stu-id="08a75-116">A *per-user* policy can affect only individual users or groups.</span></span> <span data-ttu-id="08a75-117">Para exigir una directiva por usuario, debe asignarla explícitamente a usuarios individuales, grupos y objetos de contacto.</span><span class="sxs-lookup"><span data-stu-id="08a75-117">To enforce a per-user policy, you must explicitly assign the policy to individual users, groups, and contact objects.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="08a75-118">En la mayoría de los casos, solo se necesita una directiva de correo de voz hospedado.</span><span class="sxs-lookup"><span data-stu-id="08a75-118">In most cases, only one hosted voice mail policy is required.</span></span> <span data-ttu-id="08a75-119">A menudo puede modificar la directiva global para satisfacer todas sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="08a75-119">You can often modify the global policy to meet all your needs.</span></span> <span data-ttu-id="08a75-120">Si implementa varias directivas de correo de voz hospedado, todas las directivas tienen ámbito por usuario.</span><span class="sxs-lookup"><span data-stu-id="08a75-120">If you deploy multiple hosted voice mail policies, all such policies have per-user scope.</span></span>



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a><span data-ttu-id="08a75-121">Atributos de directiva de correo de voz hospedado</span><span class="sxs-lookup"><span data-stu-id="08a75-121">Hosted Voice Mail Policy Attributes</span></span>

<span data-ttu-id="08a75-122">Una directiva de correo de voz define dos atributos que la aplicación de enrutamiento ExUM de Lync Server 2013 inserta en el URI de la solicitud de un mensaje de invitación que se envía a la implementación de mensajería unificada de Exchange hospedada:</span><span class="sxs-lookup"><span data-stu-id="08a75-122">A voice mail policy defines two attributes that the Lync Server 2013 ExUM Routing application inserts in the request URI of an INVITE message that is sent to the hosted Exchange UM implementation:</span></span>

  - <span data-ttu-id="08a75-123">**Destino:** El nombre de dominio completo (FQDN) del servicio de mensajería unificada de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="08a75-123">**Destination:** The fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="08a75-124">Este valor lo usa el servidor perimetral local de Lync Server para fines de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="08a75-124">This value is used by the on-premises Lync Server Edge Server for routing purposes.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="08a75-125">El FQDN de Exchange Online es exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="08a75-125">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

    
    </div>

  - <span data-ttu-id="08a75-126">**Organización:** El FQDN del inquilino en el servicio hospedado de mensajería unificada de Exchange que aloja los buzones de los usuarios de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="08a75-126">**Organization:** The FQDN of the tenant on the hosted Exchange UM service that homes your Lync Server 2013 users’ mailboxes.</span></span> <span data-ttu-id="08a75-127">Una directiva de correo de voz puede contener varias organizaciones.</span><span class="sxs-lookup"><span data-stu-id="08a75-127">A voice mail policy can contain multiple organizations.</span></span> <span data-ttu-id="08a75-128">Si se incluye más de una organización en la Directiva, este atributo debe ser una lista separada por comas de los inquilinos de Exchange Server que alojan los buzones de usuario de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="08a75-128">If more than one organization is included in the policy, this attribute must be a comma-separated list of the Exchange Server tenants that home your Lync Server 2013 user mailboxes.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="08a75-129">El administrador de inquilinos del servicio de mensajería unificada de Exchange hospedado proporcionará los valores necesarios para la configuración de los atributos de destino y organización.</span><span class="sxs-lookup"><span data-stu-id="08a75-129">The tenant administrator of your hosted Exchange UM service will provide the necessary values for your Destination and Organization attribute settings.</span></span> <span data-ttu-id="08a75-130">Para configurar la Directiva, debe ejecutar el cmdlet New-CsHostedVoicemailPolicy o usar el cmdlet Set-CsHostedVoicemailPolicy para modificar una que exista (por ejemplo, la directiva global).</span><span class="sxs-lookup"><span data-stu-id="08a75-130">To configure your policy, you must run the New-CsHostedVoicemailPolicy cmdlet or use the Set-CsHostedVoicemailPolicy cmdlet to modify one that exists (for example, the global policy).</span></span>



</div>

<span data-ttu-id="08a75-131">Para obtener detalles sobre la administración de directivas de correo de voz hospedado, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="08a75-131">For details about managing hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="08a75-132">New-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="08a75-132">New-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="08a75-133">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="08a75-133">Set-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="08a75-134">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="08a75-134">Get-CsHostedVoicemailPolicy</span></span>

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a><span data-ttu-id="08a75-135">Asignación de directiva de correo de voz por usuario</span><span class="sxs-lookup"><span data-stu-id="08a75-135">Per-User Voice Mail Policy Assignment</span></span>

<span data-ttu-id="08a75-136">Si su Directiva de correo de voz hospedada se define con ámbito por usuario, debe asignarla de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="08a75-136">If your hosted voice mail policy is defined with per-user scope, you must explicitly assign it.</span></span> <span data-ttu-id="08a75-137">Puede ejecutar el cmdlet Grant-CsHostedVoicemailPolicy para asignar la Directiva a usuarios individuales o a grupos.</span><span class="sxs-lookup"><span data-stu-id="08a75-137">You can run the Grant-CsHostedVoicemailPolicy cmdlet to assign the policy to individual users or groups.</span></span>

<span data-ttu-id="08a75-138">Para obtener información detallada sobre cómo asignar o quitar una directiva de correo de voz hospedado por usuario, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="08a75-138">For details about assigning or removing a per-user hosted voice mail policy, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="08a75-139">Grant-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="08a75-139">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="08a75-140">Remove-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="08a75-140">Remove-CsHostedVoicemailPolicy</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

