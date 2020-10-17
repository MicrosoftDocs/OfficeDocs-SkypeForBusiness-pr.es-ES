---
title: 'Lync Server 2013: componentes de VoIP de red perimetral'
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
ms.openlocfilehash: 16c823d290c52f91d8a25e2b9f76c36bf54c9145
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524337"
---
# <a name="perimeter-network-voip-components-for-lync-server-2013"></a><span data-ttu-id="59080-102">Componentes de VoIP de red perimetral para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59080-102">Perimeter network VoIP components for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59080-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="59080-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="59080-104">Los autores de llamada externos que usan clientes de comunicaciones unificadas para llamadas individuales o de conferencia dependen del servidor perimetral para la comunicación de voz con compañeros de trabajo.</span><span class="sxs-lookup"><span data-stu-id="59080-104">Outside callers who use unified communications clients for individual or conference calls rely on Edge Server for voice communication with coworkers.</span></span>

<span data-ttu-id="59080-105">En un servidor perimetral, el servicio perimetral de acceso proporciona señalización SIP para las llamadas de los usuarios de Lync que están fuera del firewall de la organización.</span><span class="sxs-lookup"><span data-stu-id="59080-105">On an Edge Server, the Access Edge service provides SIP signaling for calls from Lync users who are outside your organization’s firewall.</span></span> <span data-ttu-id="59080-106">El servicio perimetral A/V habilita el cruce seguro de medios de NAT y los firewalls.</span><span class="sxs-lookup"><span data-stu-id="59080-106">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="59080-107">Un autor de llamada que usa un cliente de comunicaciones unificadas (UC) desde fuera del Firewall corporativo se basa en el servicio perimetral A/V para llamadas individuales y de conferencia.</span><span class="sxs-lookup"><span data-stu-id="59080-107">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>

<span data-ttu-id="59080-108">El servicio de autenticación A/V se combina con y proporciona servicios de autenticación para el servicio perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="59080-108">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service.</span></span> <span data-ttu-id="59080-109">Los usuarios externos que intenten conectarse al servicio perimetral a/V necesitan un token de autenticación proporcionado por el servicio de autenticación A/V antes de que puedan pasar sus llamadas.</span><span class="sxs-lookup"><span data-stu-id="59080-109">Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

