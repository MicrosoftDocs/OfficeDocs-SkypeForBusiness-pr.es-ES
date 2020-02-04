---
title: 'Lync Server 2013: Componentes VoIP de la red perimetral'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Perimeter network VoIP components
ms:assetid: 74230008-695d-436a-90b9-9cd060c70f7b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398559(v=OCS.15)
ms:contentKeyID: 48184514
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb8e14228bb927f857aa5e9801f579653eb35fd2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755260"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="perimeter-network-voip-components-for-lync-server-2013"></a><span data-ttu-id="20763-102">Componentes VoIP de la red perimetral para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20763-102">Perimeter network VoIP components for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20763-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="20763-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="20763-104">Las personas que llaman fuera de los clientes de comunicaciones unificadas para llamadas individuales o de conferencia dependen del servidor perimetral para la comunicación de voz con compañeros de trabajo.</span><span class="sxs-lookup"><span data-stu-id="20763-104">Outside callers who use unified communications clients for individual or conference calls rely on Edge Server for voice communication with coworkers.</span></span>

<span data-ttu-id="20763-105">En un servidor perimetral, el servicio perimetral de acceso proporciona señalización SIP para las llamadas de los usuarios de Lync que estén fuera del firewall de la organización.</span><span class="sxs-lookup"><span data-stu-id="20763-105">On an Edge Server, the Access Edge service provides SIP signaling for calls from Lync users who are outside your organization’s firewall.</span></span> <span data-ttu-id="20763-106">El servicio perimetral A/V permite el paso de los medios a través de NAT y firewalls.</span><span class="sxs-lookup"><span data-stu-id="20763-106">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="20763-107">Un autor de llamada que use un cliente de comunicaciones unificadas (UC) desde fuera del firewall corporativo dependerá del servicio perimetral A/V para las llamadas individuales y de conferencia.</span><span class="sxs-lookup"><span data-stu-id="20763-107">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>

<span data-ttu-id="20763-p102">El servicio de autenticación A/V se combina con el servicio perimetral A/V y le proporciona servicios de autenticación. Los usuarios externos que intenten conectarse al servicio perimetral A/V necesitarán un token de autenticación proporcionado por el servicio de autenticación A/V para que sus llamadas se acepten.</span><span class="sxs-lookup"><span data-stu-id="20763-p102">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service. Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

