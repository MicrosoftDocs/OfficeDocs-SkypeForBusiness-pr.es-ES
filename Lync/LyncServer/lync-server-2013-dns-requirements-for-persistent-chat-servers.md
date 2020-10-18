---
title: 'Lync Server 2013: requisitos de DNS para servidores de chat persistente'
description: 'Lync Server 2013: requisitos de DNS para los servidores de chat persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Persistent Chat Servers
ms:assetid: f7531374-d7ed-4b63-ae81-02294cb4496a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205391(v=OCS.15)
ms:contentKeyID: 48185857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01bfc126ab588542ef5160a0eabe0c839dcf0e44
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574276"
---
# <a name="dns-requirements-for-persistent-chat-servers-in-lync-server-2013"></a><span data-ttu-id="e98ca-103">Requisitos de DNS para los servidores de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e98ca-103">DNS requirements for Persistent Chat Servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e98ca-104">_**Última modificación del tema:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="e98ca-104">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="e98ca-105">En esta sección se describen los registros del sistema de nombres de dominio (DNS) necesarios para la implementación de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e98ca-105">This section describes the Domain Name System (DNS) records that are required for deployment of Persistent Chat Servers.</span></span>

<div>

## <a name="dns-records-for-persistent-chat-servers"></a><span data-ttu-id="e98ca-106">Registros DNS para servidores de chat persistente</span><span class="sxs-lookup"><span data-stu-id="e98ca-106">DNS Records for Persistent Chat Servers</span></span>

<span data-ttu-id="e98ca-107">En la tabla siguiente se especifican los requisitos de DNS para la implementación del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e98ca-107">The following table specifies DNS requirements for Persistent Chat Server deployment.</span></span>

### <a name="dns-requirements-for-a-persistent-chat-server"></a><span data-ttu-id="e98ca-108">Requisitos de DNS para un servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="e98ca-108">DNS Requirements for a Persistent Chat Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e98ca-109">Escenario de implementación</span><span class="sxs-lookup"><span data-stu-id="e98ca-109">Deployment scenario</span></span></th>
<th><span data-ttu-id="e98ca-110">Requisito de DNS</span><span class="sxs-lookup"><span data-stu-id="e98ca-110">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e98ca-111">Un servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="e98ca-111">One Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="e98ca-112">Un registro A interno que resuelve el nombre de dominio completo (FQDN) del servidor como su dirección IP.</span><span class="sxs-lookup"><span data-stu-id="e98ca-112">An internal A record that resolves the fully qualified domain name (FQDN) of the server to its IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e98ca-113">Grupo de servidores de chat persistente</span><span class="sxs-lookup"><span data-stu-id="e98ca-113">Persistent Chat pool</span></span></p></td>
<td><p><span data-ttu-id="e98ca-114">Un registro A interno que resuelve el nombre de dominio completo (FQDN) de los servidores como su dirección IP.</span><span class="sxs-lookup"><span data-stu-id="e98ca-114">An internal A record that resolves the fully qualified domain name (FQDN) of the servers to its IP address.</span></span></p>
<p><span data-ttu-id="e98ca-115"><strong>Ejemplo</strong></span><span class="sxs-lookup"><span data-stu-id="e98ca-115"><strong>Example</strong></span></span></p>
<p><span data-ttu-id="e98ca-116">PersistentChatServer01.contoso.com 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="e98ca-116">PersistentChatServer01.contoso.com     10.10.10.1</span></span></p>
<p><span data-ttu-id="e98ca-117">PersistentChatServer02.contoso.com 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="e98ca-117">PersistentChatServer02.contoso.com     10.10.10.2</span></span></p>
<p><span data-ttu-id="e98ca-118">Un registro A interno que resuelve el nombre de dominio completo (FQDN) de los servidores como su dirección IP.</span><span class="sxs-lookup"><span data-stu-id="e98ca-118">An internal A record that resolves the fully qualified domain name (FQDN) of the servers to its IP address.</span></span></p>
<p><span data-ttu-id="e98ca-119"><strong>Ejemplo</strong></span><span class="sxs-lookup"><span data-stu-id="e98ca-119"><strong>Example</strong></span></span></p>
<p><span data-ttu-id="e98ca-120">PersistentChatPool.contoso.com 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="e98ca-120">PersistentChatPool.contoso.com    10.10.10.1</span></span></p>
<p><span data-ttu-id="e98ca-121">PersistentChatPool.contoso.com 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="e98ca-121">PersistentChatPool.contoso.com    10.10.10.2</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

