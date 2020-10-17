---
title: 'Lync Server 2013: Resumen de Puerto-conectividad de mensajería instantánea pública'
description: 'Lync Server 2013: Resumen de Puerto-conectividad de mensajería instantánea pública.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Public instant messaging connectivity
ms:assetid: f46756ec-1401-4ca2-a4a4-5cd28bcfdc7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618376(v=OCS.15)
ms:contentKeyID: 49105663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4137b5f92e043dc15dc9aa1f0b9593b4d9f7c2ca
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543066"
---
# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="039ab-103">Resumen de Puerto-conectividad de mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="039ab-103">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="039ab-104">_**Última modificación del tema:** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="039ab-104">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="039ab-105">Para configurar el firewall para los puertos y protocolos necesarios para la conectividad de mensajería instantánea pública, en primer lugar, tenga en cuenta que SIP/MTLS/TCP 5061 es bidireccional para tener en cuenta la capacidad de los contactos en el proveedor de mi pública para ponerse en contacto con clientes de Lync o Lync para ponerse en contacto con los contactos de mi pública.</span><span class="sxs-lookup"><span data-stu-id="039ab-105">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="039ab-106">Windows Live Messenger puede participar en las comunicaciones de audio y vídeo con los clientes de Lync.</span><span class="sxs-lookup"><span data-stu-id="039ab-106">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="039ab-107">Esto cuenta con una configuración de protocolos y puertos de Firewall muy similares que normalmente tendría en el firewall para admitir clientes de Lync como usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="039ab-107">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="039ab-108">Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="039ab-108">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="039ab-109">La Federación con Windows Live Messenger no requiere licencias de usuario o de dispositivo adicionales aparte de la licencia de acceso de cliente (CAL) de Lync Standard.</span><span class="sxs-lookup"><span data-stu-id="039ab-109">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="039ab-110">La Federación de Skype se agregará a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con mi y voz.</span><span class="sxs-lookup"><span data-stu-id="039ab-110">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="039ab-111">La Federación con los contactos del cliente de Messenger finalizará oficialmente el 15 de marzo de 2013, excepto para China continental.</span><span class="sxs-lookup"><span data-stu-id="039ab-111">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="039ab-112">Skype se convertirá en cliente de Federación para los usuarios federados que usaron Messenger anteriormente.</span><span class="sxs-lookup"><span data-stu-id="039ab-112">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="039ab-113">Resumen de firewall: Conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="039ab-113">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="039ab-114">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="039ab-114">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="039ab-115">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="039ab-115">Source IP address</span></span></th>
<th><span data-ttu-id="039ab-116">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="039ab-116">Destination IP address</span></span></th>
<th><span data-ttu-id="039ab-117">Notas</span><span class="sxs-lookup"><span data-stu-id="039ab-117">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="039ab-118">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="039ab-118">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="039ab-119">Socios de conectividad de MI pública</span><span class="sxs-lookup"><span data-stu-id="039ab-119">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="039ab-120">Interfaz de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="039ab-120">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="039ab-121">Para la conectividad de mensajería instantánea pública y federada que usan SIP.</span><span class="sxs-lookup"><span data-stu-id="039ab-121">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="039ab-122">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="039ab-122">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="039ab-123">Interfaz de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="039ab-123">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="039ab-124">Socios de conectividad de MI pública</span><span class="sxs-lookup"><span data-stu-id="039ab-124">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="039ab-125">Para la conectividad de mensajería instantánea pública y federada que usan SIP.</span><span class="sxs-lookup"><span data-stu-id="039ab-125">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="039ab-126">Acceso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="039ab-126">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="039ab-127">Clientes</span><span class="sxs-lookup"><span data-stu-id="039ab-127">Clients</span></span></p></td>
<td><p><span data-ttu-id="039ab-128">Interfaz de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="039ab-128">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="039ab-129">Tráfico SIP de cliente a servidor para el acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="039ab-129">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="039ab-130">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="039ab-130">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="039ab-131">Interfaz de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="039ab-131">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="039ab-132">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="039ab-132">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="039ab-133">Usado para sesiones de A/V con Windows Live Messenger si se ha configurado la conectividad de MI.</span><span class="sxs-lookup"><span data-stu-id="039ab-133">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="039ab-134">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="039ab-134">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="039ab-135">Interfaz de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="039ab-135">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="039ab-136">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="039ab-136">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="039ab-137">Necesario para la conectividad de mensajería instantánea pública con Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="039ab-137">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="039ab-138">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="039ab-138">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="039ab-139">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="039ab-139">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="039ab-140">Interfaz de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="039ab-140">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="039ab-141">Necesario para la conectividad de mensajería instantánea pública con Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="039ab-141">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="039ab-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="039ab-142">See Also</span></span>


[<span data-ttu-id="039ab-143">Escenarios para el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="039ab-143">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="039ab-144">Determinación de los requisitos de los puertos y el Firewall de A/V externos para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="039ab-144">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

