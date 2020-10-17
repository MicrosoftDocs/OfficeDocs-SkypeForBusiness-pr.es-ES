---
title: 'Lync Server 2013: información general sobre la recogida de llamadas de grupo'
description: 'Lync Server 2013: información general sobre la recogida de llamadas de grupo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Group Call Pickup
ms:assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945623(v=OCS.15)
ms:contentKeyID: 51541466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c968ac466c7242253cb5a9594e1942d86031494d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562886"
---
# <a name="overview-of-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="d9fa0-103">Información general sobre la recogida de llamadas grupales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9fa0-103">Overview of Group Call Pickup in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9fa0-104">_**Última modificación del tema:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="d9fa0-104">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="d9fa0-105">Recogida de llamadas grupales, una nueva característica de las actualizaciones acumulativas de Lync Server 2013: febrero de 2013, permite a los usuarios responder llamadas entrantes a sus colegas desde sus propios teléfonos.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-105">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="d9fa0-106">Esta nueva característica aumenta la disponibilidad de la línea de un usuario al permitir que otros usuarios respondan a una llamada entrante marcando un número de grupo de atención de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-106">This new feature increases the availability of a user's line by enabling other users to answer an incoming call by dialing a call pickup group number.</span></span> <span data-ttu-id="d9fa0-107">Cuando se implementa la recogida de llamadas de grupo, se puede reducir significativamente el número de llamadas entrantes que se redirigen a correo de voz, lo que es especialmente útil para las llamadas de clientes externos a la organización.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-107">When Group Call Pickup is deployed, the number of incoming calls that are routed to voice mail can be significantly reduced, which is particularly useful for calls from customers who are external to your organization.</span></span>

<span data-ttu-id="d9fa0-108">La característica de atención de llamadas grupales se ha diseñado en particular para las unidades de negocio en entornos de oficina abiertos.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-108">The Group Call Pickup feature is designed in particular for business units in open office environments.</span></span> <span data-ttu-id="d9fa0-109">Las llamadas entrantes no son disruptivas porque solo se redirigen al destino previsto.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-109">Incoming calls are not disruptive because they ring only at the intended destination.</span></span> <span data-ttu-id="d9fa0-110">Sin embargo, otros usuarios que escuchan el timbre pueden seguir retomando la llamada simplemente marcando el número de grupo.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-110">Other users who hear the ring, however, can still pick up the call simply by dialing the group number.</span></span>

<span data-ttu-id="d9fa0-111">En entornos en los que los usuarios no están ubicados en un diseño de oficina abierto o donde los usuarios que comparten una responsabilidad común están distribuidos geográficamente, la llamada de equipo presenta la solución más adecuada.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-111">In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution.</span></span> <span data-ttu-id="d9fa0-112">La principal diferencia entre la atención de llamadas de grupo y la llamada de equipo es que, con la atención de llamadas de grupo, una llamada entrante solo suena en el destino deseado, pero cualquiera puede decidir si marca un número de grupo para responderla.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-112">The primary difference between Group Call Pickup and team call is that, with Group Call Pickup, an incoming call rings only at the intended destination, but anyone can still choose to answer it by dialing a group number.</span></span> <span data-ttu-id="d9fa0-113">Con la llamada de equipo, la llamada suena en todos los teléfonos de los miembros del equipo, y cualquier usuario del equipo puede seleccionar el teléfono para responder a la llamada.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-113">With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call.</span></span> <span data-ttu-id="d9fa0-114">Una diferencia adicional entre la atención de llamadas de grupo y la llamada de equipo es que un administrador, a través de Lync Server, administra la recogida de llamadas de grupo.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-114">An additional difference between Group Call Pickup and team call is that Group Call Pickup is managed by an administrator, through Lync Server.</span></span> <span data-ttu-id="d9fa0-115">Con la llamada de equipo, los usuarios finales administran la característica mediante el cliente de Lync.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-115">With team call, end users manage the feature by using the Lync client.</span></span> <span data-ttu-id="d9fa0-116">Por lo tanto, con la atención de llamadas grupales, este aspecto de la administración de llamadas puede centralizarse.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-116">With Group Call Pickup, therefore, this aspect of call management can be centralized.</span></span>

<span data-ttu-id="d9fa0-117">La recogida de llamadas de grupo está integrada en la aplicación de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-117">Group Call Pickup is built on the Call Park application.</span></span> <span data-ttu-id="d9fa0-118">Cuando se implementa la atención de llamadas grupales, se configura la tabla de órbitas de estacionamiento de llamadas con intervalos separados de números de extensión que se designan como números de grupo de atención de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-118">When you deploy Group Call Pickup, you configure the call park orbit table with separate ranges of extension numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="d9fa0-119">Al igual que los números de órbitas de estacionamiento de llamadas, los números de grupo de atención de llamadas deben ser extensiones virtuales que no tengan asignado ningún usuario ni teléfono.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-119">Like call park orbit numbers, call pickup group numbers must be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="d9fa0-120">Cada grupo de servidores front-end en el que se implementa la recogida de llamadas grupales puede tener uno o más intervalos de números de grupo de atención de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-120">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="d9fa0-121">Los intervalos de números de grupo deben ser únicos en todo el mundo en la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-121">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d9fa0-122">Los intervalos de números que se designan como números de llamada de grupo en la tabla de órbitas de estacionamiento de llamadas no se pueden administrar ni ver mediante el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-122">Number ranges that are designated as Group Call Pickup numbers in the call park orbit table cannot be managed or viewed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="d9fa0-123">La única forma de ver todos los intervalos de números en la tabla de órbitas del estacionamiento de llamadas es usar el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-123">The only way to see all the number ranges in the call park orbit table is to use Lync Server Management Shell.</span></span> <span data-ttu-id="d9fa0-124">De forma similar, la única forma de agregar, modificar o quitar números de atención de llamadas de grupo es usar el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-124">Similarly, the only way to add, modify, or remove Group Call Pickup numbers is to use Lync Server Management Shell.</span></span>



</div>

<span data-ttu-id="d9fa0-125">Una vez configurados los números de grupo de atención de llamadas, los usuarios se asignan a un grupo de recogida de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-125">After you configure the call pickup group numbers, you assign users to a call pickup group.</span></span> <span data-ttu-id="d9fa0-126">Cualquier usuario que esté asignado a un grupo de recogida de llamadas puede tener respuestas a las llamadas de otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-126">Any user who is assigned to a call pickup group can have their calls answered by other users.</span></span> <span data-ttu-id="d9fa0-127">Cuando llega una llamada a un usuario asignado a un grupo de atención de llamadas, cualquier otro usuario que note la llamada puede responderla marcando manualmente el número del grupo de recogida de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-127">When a call comes in to a user who is assigned to a call pickup group, any other user who notices the call can answer it by manually dialing the call pickup group number.</span></span> <span data-ttu-id="d9fa0-128">No es necesario que el usuario que seleccione la llamada sea miembro del grupo.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-128">The user who picks up the call does not need to be a member of the group.</span></span> <span data-ttu-id="d9fa0-129">Cuando otro usuario selecciona una llamada, se envía una notificación al número al que se llamó originalmente.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-129">When a call is picked up by another user, a notification is sent to the number originally called.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d9fa0-130">Un usuario puede ser miembro de un solo grupo de recogida de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-130">A user can be a member of only one call pickup group.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="d9fa0-131">Aunque cualquier usuario de la implementación de Lync Server puede responder una llamada a un miembro del grupo de atención de llamadas, la persona que contesta la llamada debe conocer el número de grupo de atención de llamadas correcto para marcar.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-131">Although any user in the Lync Server deployment can answer a call to a call pickup group member, the person answering the call must know the correct call pickup group number to dial.</span></span>



</div>

<span data-ttu-id="d9fa0-132">Si un usuario marca un número de grupo de atención de llamadas para responder a una llamada cuando varios teléfonos del grupo están sonando, el usuario responde a la llamada que ha sonado más tiempo.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-132">If a user dials a call pickup group number to answer a call when multiple phones in the group are ringing, the user answers the call that has been ringing the longest.</span></span>

<span data-ttu-id="d9fa0-133">La configuración de llamadas simultáneas funcionará para los usuarios que tengan llamadas de llamada de grupo.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-133">Simultaneous ringing settings will work for users who have group call pickup.</span></span> <span data-ttu-id="d9fa0-134">Es decir, una llamada realizada a un usuario que tiene llamada de llamada de grupo sonará para todos los destinos configurados y otro usuario puede responder a la llamada.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-134">That is, a call made to a user who has Group Call Pickup will ring for all the configured destinations, and another user can answer the call.</span></span> <span data-ttu-id="d9fa0-135">La excepción a esta regla es cuando el usuario configura la llamada simultánea para llamar a todos los miembros del equipo.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-135">The exception to this rule is when the user configures simultaneous ringing to call all the team members.</span></span>

<span data-ttu-id="d9fa0-136">La recopilación de llamadas de grupo no se puede usar para responder a los siguientes tipos de llamadas:</span><span class="sxs-lookup"><span data-stu-id="d9fa0-136">Group Call Pickup cannot be used to answer the following types of calls:</span></span>

  - <span data-ttu-id="d9fa0-137">Llamadas a una línea privada</span><span class="sxs-lookup"><span data-stu-id="d9fa0-137">Calls to a private line</span></span>

  - <span data-ttu-id="d9fa0-138">Llamadas de un contacto al que se le ha asignado la relación de privacidad amigos y familiares</span><span class="sxs-lookup"><span data-stu-id="d9fa0-138">Calls from a contact who has been assigned the Friends and Family privacy relationship</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="d9fa0-139">Un usuario que es miembro de un grupo de recogida de llamadas puede evitar que se recuperen determinadas llamadas a través de la llamada de llamada de grupo marcando el contacto como contacto personal en el cliente de Lync.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-139">A user who is a member of a call pickup group can prevent certain calls from being retrieved through Group Call Pickup by marking the contact as a personal contact in the Lync client.</span></span> <span data-ttu-id="d9fa0-140">Para marcar un contacto como contacto personal, establezca la relación de privacidad para el contacto en amigos y familiares.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-140">To mark a contact as a personal contact, set the Privacy Relationship for the contact to Friends and Family.</span></span> <span data-ttu-id="d9fa0-141">Las llamadas entrantes de contactos con la relación de privacidad establecida en amigos y familiares no se pueden recuperar con la atención de llamadas grupales.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-141">Any incoming call from contacts with the Privacy Relationship set to Friends and Family cannot be retrieved by using Group Call Pickup.</span></span>

    
    </div>

  - <span data-ttu-id="d9fa0-142">Parte de vídeo de las llamadas de audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="d9fa0-142">Video portion of audio/video calls</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d9fa0-143">Si un usuario responde a una llamada de audio o vídeo, el usuario recibe sólo el audio.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-143">If a user answers an audio/video call, the user receives only the audio.</span></span> <span data-ttu-id="d9fa0-144">La persona que llama o la persona que responde a la llamada puede escalar la llamada para agregar vídeo.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-144">Either the person calling or the person answering the call can escalate the call to add video.</span></span>

    
    </div>

  - <span data-ttu-id="d9fa0-145">Llamadas simultáneas de llamada que se redirigen a miembros de llamada de equipo</span><span class="sxs-lookup"><span data-stu-id="d9fa0-145">Simultaneous ringing calls that are routed to team call members</span></span>

  - <span data-ttu-id="d9fa0-146">Llamadas enrutadas a un delegado</span><span class="sxs-lookup"><span data-stu-id="d9fa0-146">Calls routed to a delegate</span></span>

  - <span data-ttu-id="d9fa0-147">Llamadas enrutadas a un grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="d9fa0-147">Calls routed to a response group</span></span>

<span data-ttu-id="d9fa0-148">Los siguientes tipos de usuarios no pueden participar en la recepción de llamadas grupales.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-148">The following types of users cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="d9fa0-149">Es decir, no deben incluirse en un grupo de atención de llamadas de grupo y no pueden recoger llamadas para los usuarios que tienen habilitada la recogida de llamadas de grupo.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-149">That is, they should not be included in a Group Call Pickup group, and they cannot pick up calls for users who have Group Call Pickup enabled.</span></span>

  - <span data-ttu-id="d9fa0-150">Usuarios hospedados en línea en una implementación híbrida</span><span class="sxs-lookup"><span data-stu-id="d9fa0-150">Users who are homed online in a hybrid deployment</span></span>

  - <span data-ttu-id="d9fa0-151">Usuarios que no están hospedados en un grupo de servidores de Lync Server 2013 con actualizaciones acumulativas para Lync Server 2013: febrero de 2013 en una implementación local</span><span class="sxs-lookup"><span data-stu-id="d9fa0-151">Users who are not homed on a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013 in an on-premises deployment</span></span>

<span data-ttu-id="d9fa0-152">Si nadie responde a una llamada a un miembro de un grupo de atención de llamadas, la llamada se enruta como se especifica en la configuración del cliente.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-152">If no one answers a call to a member of a call pickup group, the call is routed as specified in the client settings.</span></span> <span data-ttu-id="d9fa0-153">Es decir, la llamada se dirige al correo de voz o se reenvía a otro destino, como se especifica en la configuración del cliente.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-153">That is, the call goes to voicemail or is forwarded to a different destination, as specified in the client settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

