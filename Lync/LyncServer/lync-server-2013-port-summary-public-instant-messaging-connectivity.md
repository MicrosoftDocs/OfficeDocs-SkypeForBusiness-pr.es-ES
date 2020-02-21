---
title: 'Lync Server 2013: Resumen de Puerto-conectividad de mensajería instantánea pública'
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
ms.openlocfilehash: bfc057f4d41104dcebc89003ff77eb75622ee3c1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="845e9-102">Resumen de Puerto-conectividad de mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="845e9-102">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="845e9-103">_**Última modificación del tema:** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="845e9-103">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="845e9-104">Para configurar el firewall para los puertos y protocolos necesarios para la conectividad de mensajería instantánea pública, en primer lugar, tenga en cuenta que SIP/MTLS/TCP 5061 es bidireccional para tener en cuenta la capacidad de los contactos en el proveedor de mi pública para ponerse en contacto con clientes de Lync o Lync para ponerse en contacto con los contactos de mi pública.</span><span class="sxs-lookup"><span data-stu-id="845e9-104">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="845e9-105">Windows Live Messenger puede participar en las comunicaciones de audio y vídeo con los clientes de Lync.</span><span class="sxs-lookup"><span data-stu-id="845e9-105">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="845e9-106">Esto cuenta con una configuración de protocolos y puertos de Firewall muy similares que normalmente tendría en el firewall para admitir clientes de Lync como usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="845e9-106">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="845e9-107">Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="845e9-107">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="845e9-108">La Federación con Windows Live Messenger no requiere licencias de usuario o de dispositivo adicionales aparte de la licencia de acceso de cliente (CAL) de Lync Standard.</span><span class="sxs-lookup"><span data-stu-id="845e9-108">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="845e9-109">La Federación de Skype se agregará a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con mi y voz.</span><span class="sxs-lookup"><span data-stu-id="845e9-109">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="845e9-110">La Federación con los contactos del cliente de Messenger finalizará oficialmente el 15 de marzo de 2013, excepto para China continental.</span><span class="sxs-lookup"><span data-stu-id="845e9-110">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="845e9-111">Skype se convertirá en cliente de Federación para los usuarios federados que usaron Messenger anteriormente.</span><span class="sxs-lookup"><span data-stu-id="845e9-111">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="845e9-112">Resumen de firewall: Conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="845e9-112">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="845e9-113">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="845e9-113">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="845e9-114">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="845e9-114">Source IP address</span></span></th>
<th><span data-ttu-id="845e9-115">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="845e9-115">Destination IP address</span></span></th>
<th><span data-ttu-id="845e9-116">Notas</span><span class="sxs-lookup"><span data-stu-id="845e9-116">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="845e9-117">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="845e9-117">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="845e9-118">Socios de conectividad de MI pública</span><span class="sxs-lookup"><span data-stu-id="845e9-118">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="845e9-119">Interfaz de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="845e9-119">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="845e9-120">Para la conectividad de mensajería instantánea pública y federada que usan SIP.</span><span class="sxs-lookup"><span data-stu-id="845e9-120">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="845e9-121">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="845e9-121">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="845e9-122">Interfaz de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="845e9-122">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="845e9-123">Socios de conectividad de MI pública</span><span class="sxs-lookup"><span data-stu-id="845e9-123">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="845e9-124">Para la conectividad de mensajería instantánea pública y federada que usan SIP.</span><span class="sxs-lookup"><span data-stu-id="845e9-124">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="845e9-125">Acceso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="845e9-125">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="845e9-126">Clientes</span><span class="sxs-lookup"><span data-stu-id="845e9-126">Clients</span></span></p></td>
<td><p><span data-ttu-id="845e9-127">Interfaz de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="845e9-127">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="845e9-128">Tráfico SIP de cliente a servidor para el acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="845e9-128">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="845e9-129">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="845e9-129">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="845e9-130">Interfaz de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="845e9-130">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="845e9-131">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="845e9-131">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="845e9-132">Usado para sesiones de A/V con Windows Live Messenger si se ha configurado la conectividad de MI.</span><span class="sxs-lookup"><span data-stu-id="845e9-132">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="845e9-133">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="845e9-133">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="845e9-134">Interfaz de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="845e9-134">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="845e9-135">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="845e9-135">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="845e9-136">Necesario para la conectividad de mensajería instantánea pública con Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="845e9-136">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="845e9-137">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="845e9-137">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="845e9-138">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="845e9-138">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="845e9-139">Interfaz de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="845e9-139">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="845e9-140">Necesario para la conectividad de mensajería instantánea pública con Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="845e9-140">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="845e9-141">Consulta también</span><span class="sxs-lookup"><span data-stu-id="845e9-141">See Also</span></span>


[<span data-ttu-id="845e9-142">Escenarios para el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="845e9-142">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="845e9-143">Determinación de los requisitos de los puertos y el Firewall de A/V externos para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="845e9-143">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

