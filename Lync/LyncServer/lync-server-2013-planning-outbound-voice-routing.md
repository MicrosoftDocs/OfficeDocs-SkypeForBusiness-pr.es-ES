---
title: 'Lync Server 2013: Planeación del enrutamiento de voz saliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning outbound voice routing
ms:assetid: 37c55fa4-175a-4190-b9e4-c2e5ac7b9261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425853(v=OCS.15)
ms:contentKeyID: 48183835
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fbcb976ed4f3d1464b6b956ef60dc1d00bd6907
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-outbound-voice-routing-in-lync-server-2013"></a><span data-ttu-id="dfd13-102">Planeación del enrutamiento de voz saliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfd13-102">Planning outbound voice routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfd13-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="dfd13-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="dfd13-p101">El enrutamiento de llamadas realizadas se aplica a las llamadas destinadas a una puerta de enlace de red telefónica conmutada (RTC), un enlace troncal o una central de conmutación PBX. Cuando un usuario realiza una llamada, el servidor normaliza el número de teléfono al formato E.164, si es necesario, e intenta establecer una coincidencia con un URI de SIP. Si el servidor no puede establecer la coincidencia, aplicará la lógica de enrutamiento de llamadas realizadas basándose en la cadena de marcado proporcionada. Dicha lógica se define con la configuración de las opciones de servidor que se describe en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="dfd13-p101">Outbound call routing applies to calls that are destined for a public switched telephone network (PSTN) gateway, trunk, or private branch exchange (PBX). When a user places a call, the server normalizes the phone number to E.164 format, if necessary, and attempts to match it to a SIP URI. If the server cannot make the match, it applies outbound call routing logic based on the supplied dial string. You define that logic by configuring the server settings that are described in the following table.</span></span>

### <a name="lync-server-outbound-call-routing-settings"></a><span data-ttu-id="dfd13-108">Configuración del servidor de enrutamiento de llamadas realizadas de Lync Server</span><span class="sxs-lookup"><span data-stu-id="dfd13-108">Lync Server Outbound Call Routing Settings</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dfd13-109">Objeto</span><span class="sxs-lookup"><span data-stu-id="dfd13-109">Object</span></span></th>
<th><span data-ttu-id="dfd13-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="dfd13-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dfd13-111">Plan de marcado</span><span class="sxs-lookup"><span data-stu-id="dfd13-111">Dial Plan</span></span></p></td>
<td><p><span data-ttu-id="dfd13-112">Un plan de marcado es un conjunto de reglas de normalización especificado por el usuario que convierte números de teléfono para una ubicación especificada por el usuario, un usuario individual o un objeto de contacto a un formato estándar único (E.164) con fines de autorización telefónica y enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="dfd13-112">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfd13-113">Regla de normalización</span><span class="sxs-lookup"><span data-stu-id="dfd13-113">Normalization rule</span></span></p></td>
<td><p><span data-ttu-id="dfd13-p102">Las reglas de normalización definen la forma en que los números de teléfono expresados en diversos formatos se van a enrutar en cada ubicación, usuario u objeto de contacto que se haya especificado. Una misma cadena de marcado se puede interpretar y convertir de manera distinta en función de la ubicación desde la que se marque y la persona o el objeto de contacto que realice la llamada. Un conjunto de reglas de normalización asociado a una ubicación determinada constituye un plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="dfd13-p102">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object. The same dial string may be interpreted and translated differently, depending on the location from which it is dialed and the person or contact object that makes the call. A set of normalization rules associated with a particular location constitutes a dial plan.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfd13-117">Directiva de voz</span><span class="sxs-lookup"><span data-stu-id="dfd13-117">Voice policy</span></span></p></td>
<td><p><span data-ttu-id="dfd13-p103">Una directiva de voz asocia uno o varios registros de uso de RTC a un usuario o un grupo de usuarios. Además proporciona una lista de características de llamada que se puede habilitar o deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="dfd13-p103">A voice policy associates one or more PSTN usage records with one user or a group of users. A voice policy also provides a list of calling features that you can enable or disable.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfd13-120">Registro de uso de RTC</span><span class="sxs-lookup"><span data-stu-id="dfd13-120">PSTN usage record</span></span></p></td>
<td><p><span data-ttu-id="dfd13-121">Un registro de uso de RTC especifica la clase de llamada (por ejemplo, interna, local o de larga distancia) que pueden realizar los diversos usuarios o grupos de usuarios en una organización.</span><span class="sxs-lookup"><span data-stu-id="dfd13-121">A PSTN usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users, or groups of users, in an organization.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfd13-122">Ruta de llamada</span><span class="sxs-lookup"><span data-stu-id="dfd13-122">Call Route</span></span></p></td>
<td><p><span data-ttu-id="dfd13-p104">Una ruta de llamada asocia los números de teléfono de destino a determinados circuitos de enlace y a determinados registros de uso de PSTN. Un circuito de enlace de PSTN se considera una puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="dfd13-p104">A call route associates destination phone numbers with particular trunks and PSTN usage records. A PSTN gateway is considered a trunk.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="dfd13-125">En esta sección</span><span class="sxs-lookup"><span data-stu-id="dfd13-125">In This Section</span></span>

<span data-ttu-id="dfd13-126">En esta sección se proporcionan instrucciones para configurar las siguientes opciones del servidor de enrutamiento de llamadas realizadas:</span><span class="sxs-lookup"><span data-stu-id="dfd13-126">This section provides guidelines for configuring the following outbound call routing server settings:</span></span>

  - <span></span>  
    [<span data-ttu-id="dfd13-127">Planes de marcado y reglas de normalización en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfd13-127">Dial plans and normalization rules in Lync Server 2013</span></span>](lync-server-2013-dial-plans-and-normalization-rules.md)

  - <span></span>  
    [<span data-ttu-id="dfd13-128">Directivas de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfd13-128">Voice policies in Lync Server 2013</span></span>](lync-server-2013-voice-policies.md)

  - <span></span>  
    [<span data-ttu-id="dfd13-129">Registros de uso de RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfd13-129">PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-pstn-usage-records.md)

  - <span></span>  
    [<span data-ttu-id="dfd13-130">Rutas de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfd13-130">Voice routes in Lync Server 2013</span></span>](lync-server-2013-voice-routes.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dfd13-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="dfd13-131">See Also</span></span>


[<span data-ttu-id="dfd13-132">Enlace troncal SIP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfd13-132">SIP trunking in Lync Server 2013</span></span>](lync-server-2013-sip-trunking.md)  
[<span data-ttu-id="dfd13-133">Conexiones SIP directas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfd13-133">Direct SIP connections in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

