---
title: 'Lync Server 2013: información general sobre la recogida de llamadas grupales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Group Call Pickup
ms:assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945623(v=OCS.15)
ms:contentKeyID: 51541466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 132d987b7d8007873a27cd74aacfc11e0c882c39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825481"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="bf7a5-102">Descripción general de la recogida de llamadas grupales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf7a5-102">Overview of Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf7a5-103">_**Última modificación del tema:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="bf7a5-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="bf7a5-104">Recogida de la llamada grupal, una nueva característica de las actualizaciones acumulativas para Lync Server 2013: el 2013 de febrero, permite a los usuarios contestar las llamadas entrantes a sus colegas desde sus propios teléfonos.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-104">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="bf7a5-105">Esta nueva característica aumenta la disponibilidad de la línea de un usuario al permitir que otros usuarios respondan a una llamada entrante marcando un número de grupo de recogida de llamadas.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-105">This new feature increases the availability of a user's line by enabling other users to answer an incoming call by dialing a call pickup group number.</span></span> <span data-ttu-id="bf7a5-106">Cuando se implementa la recogida de llamadas grupales, el número de llamadas entrantes que se dirigen al correo de voz se puede reducir significativamente, lo cual es especialmente útil para llamadas de clientes externos a su organización.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-106">When Group Call Pickup is deployed, the number of incoming calls that are routed to voice mail can be significantly reduced, which is particularly useful for calls from customers who are external to your organization.</span></span>

<span data-ttu-id="bf7a5-107">La característica de recogida de llamadas grupales está diseñada especialmente para las unidades de negocio en entornos de Office abiertos.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-107">The Group Call Pickup feature is designed in particular for business units in open office environments.</span></span> <span data-ttu-id="bf7a5-108">Las llamadas entrantes no resultan molestas porque solo suenan en el destino previsto.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-108">Incoming calls are not disruptive because they ring only at the intended destination.</span></span> <span data-ttu-id="bf7a5-109">Pero los otros usuarios que escuchan el timbre pueden atender la llamada muy fácilmente al marcar el número del grupo.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-109">Other users who hear the ring, however, can still pick up the call simply by dialing the group number.</span></span>

<span data-ttu-id="bf7a5-110">In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-110">In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution.</span></span> <span data-ttu-id="bf7a5-111">La principal diferencia entre la recogida de llamadas Grupals y la llamada de equipo es que, con la recogida de llamadas grupales, las llamadas entrantes solo suenan en el destino previsto, pero cualquier persona puede responderla marcando un número de grupo.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-111">The primary difference between Group Call Pickup and team call is that, with Group Call Pickup, an incoming call rings only at the intended destination, but anyone can still choose to answer it by dialing a group number.</span></span> <span data-ttu-id="bf7a5-112">With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-112">With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call.</span></span> <span data-ttu-id="bf7a5-113">Una diferencia adicional entre la recogida de llamadas Grupals y la llamada de equipo es que un administrador administra a través de Lync Server la recogida de llamadas grupales.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-113">An additional difference between Group Call Pickup and team call is that Group Call Pickup is managed by an administrator, through Lync Server.</span></span> <span data-ttu-id="bf7a5-114">Con la llamada de equipo, los usuarios finales administran la característica con el cliente de Lync.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-114">With team call, end users manage the feature by using the Lync client.</span></span> <span data-ttu-id="bf7a5-115">Con la recogida de llamadas grupales, este aspecto de la administración de llamadas puede centralizarse.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-115">With Group Call Pickup, therefore, this aspect of call management can be centralized.</span></span>

<span data-ttu-id="bf7a5-116">La recogida de llamadas grupales está integrada en la aplicación de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-116">Group Call Pickup is built on the Call Park application.</span></span> <span data-ttu-id="bf7a5-117">Cuando se implementa la recogida de llamadas grupales, se configura la tabla de llamadas en órbita con distintos intervalos de números de extensión que se designan como números de grupo de recogida de llamadas.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-117">When you deploy Group Call Pickup, you configure the call park orbit table with separate ranges of extension numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="bf7a5-118">Al igual que los números de órbita del estacionamiento de llamadas, los números de grupo de atención de llamadas necesitan ser extensiones virtuales que no tengan asignado ningún usuario o teléfono.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-118">Like call park orbit numbers, call pickup group numbers must be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="bf7a5-119">Cada grupo de servidores front-end en el que se implementa la recogida de llamadas grupales puede tener uno o más intervalos de números de grupo de recogida de llamadas.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-119">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="bf7a5-120">Los intervalos de números de grupo deben ser únicos globalmente en la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-120">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bf7a5-121">Los intervalos de números que se designan como números de recogida de llamadas grupales en la tabla llamada en órbita de la llamada no se pueden administrar ni ver mediante el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-121">Number ranges that are designated as Group Call Pickup numbers in the call park orbit table cannot be managed or viewed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="bf7a5-122">La única forma de ver todos los intervalos de números en la tabla llamada de la órbita de la tabla de la órbita es usar el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-122">The only way to see all the number ranges in the call park orbit table is to use Lync Server Management Shell.</span></span> <span data-ttu-id="bf7a5-123">De forma similar, la única forma de agregar, modificar o quitar números de recogida de llamadas de grupo es usar el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-123">Similarly, the only way to add, modify, or remove Group Call Pickup numbers is to use Lync Server Management Shell.</span></span>



</div>

<span data-ttu-id="bf7a5-p106">Una vez configurados los números de grupo de atención de llamadas, necesitas asignar los usuarios a un grupo de atención de llamadas. Las llamadas de un usuario asignado a un grupo de atención de llamadas pueden responderlas otros usuarios. Cuando entra una llamada para un usuario asignado a un grupo de atención de llamadas, cualquier otro usuario que escuche la llamada puede atenderla marcando de forma manual el número del grupo de atención de llamadas. No es necesario que el usuario que atiende la llamada sea miembro del grupo. Cuando otro usuario atiende una llamada, se envía una notificación al número al que se llamó originalmente.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-p106">After you configure the call pickup group numbers, you assign users to a call pickup group. Any user who is assigned to a call pickup group can have their calls answered by other users. When a call comes in to a user who is assigned to a call pickup group, any other user who notices the call can answer it by manually dialing the call pickup group number. The user who picks up the call does not need to be a member of the group. When a call is picked up by another user, a notification is sent to the number originally called.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bf7a5-129">Un usuario solo puede pertenecer a un grupo de atención de llamadas.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-129">A user can be a member of only one call pickup group.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="bf7a5-130">Aunque cualquier usuario de la implementación de Lync Server puede contestar una llamada a un miembro del grupo de recogida de llamadas, la persona que contesta la llamada debe conocer el número de grupo de recogida de llamadas correcto para marcar.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-130">Although any user in the Lync Server deployment can answer a call to a call pickup group member, the person answering the call must know the correct call pickup group number to dial.</span></span>



</div>

<span data-ttu-id="bf7a5-131">Si un usuario marca el número de un grupo de atención de llamadas para responder una llamada cuando suenan varios teléfonos del grupo, atenderá la llamada que ha sonado por más tiempo.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-131">If a user dials a call pickup group number to answer a call when multiple phones in the group are ringing, the user answers the call that has been ringing the longest.</span></span>

<span data-ttu-id="bf7a5-132">La configuración de llamadas simultáneas resulta útil para los usuarios que disponen de la atención de llamadas grupales.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-132">Simultaneous ringing settings will work for users who have group call pickup.</span></span> <span data-ttu-id="bf7a5-133">Es decir, una llamada realizada a un usuario que tiene la característica de recogida de llamadas de grupo sonará para todos los destinos configurados y otro usuario podrá contestar la llamada.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-133">That is, a call made to a user who has Group Call Pickup will ring for all the configured destinations, and another user can answer the call.</span></span> <span data-ttu-id="bf7a5-134">La excepción a esta regla es cuando un usuario configura las llamadas simultáneas para llamar a todos los miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-134">The exception to this rule is when the user configures simultaneous ringing to call all the team members.</span></span>

<span data-ttu-id="bf7a5-135">La recogida de llamada grupal no se puede usar para responder a los siguientes tipos de llamadas:</span><span class="sxs-lookup"><span data-stu-id="bf7a5-135">Group Call Pickup cannot be used to answer the following types of calls:</span></span>

  - <span data-ttu-id="bf7a5-136">Llamadas a una línea privada</span><span class="sxs-lookup"><span data-stu-id="bf7a5-136">Calls to a private line</span></span>

  - <span data-ttu-id="bf7a5-137">Llamadas de un contacto al que se ha asignado la relación de privacidad Amigos y familiares</span><span class="sxs-lookup"><span data-stu-id="bf7a5-137">Calls from a contact who has been assigned the Friends and Family privacy relationship</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="bf7a5-138">Un usuario que sea miembro de un grupo de recogida de llamadas puede impedir que se recuperen determinadas llamadas a través de la recogida de llamadas grupales marcando el contacto como contacto personal en el cliente de Lync.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-138">A user who is a member of a call pickup group can prevent certain calls from being retrieved through Group Call Pickup by marking the contact as a personal contact in the Lync client.</span></span> <span data-ttu-id="bf7a5-139">Para marcar un contacto como contacto personal, establece la relación de privacidad del contacto en Amigos y familiares.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-139">To mark a contact as a personal contact, set the Privacy Relationship for the contact to Friends and Family.</span></span> <span data-ttu-id="bf7a5-140">Las llamadas entrantes de contactos con la relación de privacidad establecida a amigos y familiares no se pueden recuperar mediante la recogida de llamadas grupales.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-140">Any incoming call from contacts with the Privacy Relationship set to Friends and Family cannot be retrieved by using Group Call Pickup.</span></span>

    
    </div>

  - <span data-ttu-id="bf7a5-141">Parte de vídeo de llamadas de audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="bf7a5-141">Video portion of audio/video calls</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bf7a5-p109">Si un usuario responde una llamada de audio y vídeo, solo recibe el audio. La persona que llama o la persona que responde la llamada puede escalarla para agregar vídeo.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-p109">If a user answers an audio/video call, the user receives only the audio. Either the person calling or the person answering the call can escalate the call to add video.</span></span>

    
    </div>

  - <span data-ttu-id="bf7a5-144">Llamadas simultáneas redirigidas a miembros de llamada de equipo</span><span class="sxs-lookup"><span data-stu-id="bf7a5-144">Simultaneous ringing calls that are routed to team call members</span></span>

  - <span data-ttu-id="bf7a5-145">Llamadas redirigidas a un delegado</span><span class="sxs-lookup"><span data-stu-id="bf7a5-145">Calls routed to a delegate</span></span>

  - <span data-ttu-id="bf7a5-146">Llamadas redirigidas a un grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="bf7a5-146">Calls routed to a response group</span></span>

<span data-ttu-id="bf7a5-147">Los siguientes tipos de usuarios no pueden participar en la recogida de llamadas grupales.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-147">The following types of users cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="bf7a5-148">Es decir, no deben incluirse en un grupo de recogida de llamadas Grupals y no pueden atender llamadas de usuarios que tienen habilitada la recogida de llamadas grupales.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-148">That is, they should not be included in a Group Call Pickup group, and they cannot pick up calls for users who have Group Call Pickup enabled.</span></span>

  - <span data-ttu-id="bf7a5-149">Usuarios alojados en línea en una implementación híbrida</span><span class="sxs-lookup"><span data-stu-id="bf7a5-149">Users who are homed online in a hybrid deployment</span></span>

  - <span data-ttu-id="bf7a5-150">Usuarios que no están alojados en un grupo de servidores de Lync Server 2013 con actualizaciones acumulativas para Lync Server 2013:2013 de febrero en una implementación local</span><span class="sxs-lookup"><span data-stu-id="bf7a5-150">Users who are not homed on a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013 in an on-premises deployment</span></span>

<span data-ttu-id="bf7a5-p111">Si nadie atiende una llamada realizada a un miembro de un grupo de atención de llamadas, la llamada se redirige según lo especificado en la configuración del cliente. Es decir, la llamada se desvía al correo de voz o se reenvía a otro destino, tal como se especifique en la configuración del cliente.</span><span class="sxs-lookup"><span data-stu-id="bf7a5-p111">If no one answers a call to a member of a call pickup group, the call is routed as specified in the client settings. That is, the call goes to voicemail or is forwarded to a different destination, as specified in the client settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

