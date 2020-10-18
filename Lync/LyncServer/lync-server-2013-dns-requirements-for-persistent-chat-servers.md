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
# <a name="dns-requirements-for-persistent-chat-servers-in-lync-server-2013"></a>Requisitos de DNS para los servidores de chat persistente en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-28_

En esta sección se describen los registros del sistema de nombres de dominio (DNS) necesarios para la implementación de servidores de chat persistente.

<div>

## <a name="dns-records-for-persistent-chat-servers"></a>Registros DNS para servidores de chat persistente

En la tabla siguiente se especifican los requisitos de DNS para la implementación del servidor de chat persistente.

### <a name="dns-requirements-for-a-persistent-chat-server"></a>Requisitos de DNS para un servidor de chat persistente

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Escenario de implementación</th>
<th>Requisito de DNS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Un servidor de chat persistente</p></td>
<td><p>Un registro A interno que resuelve el nombre de dominio completo (FQDN) del servidor como su dirección IP.</p></td>
</tr>
<tr class="even">
<td><p>Grupo de servidores de chat persistente</p></td>
<td><p>Un registro A interno que resuelve el nombre de dominio completo (FQDN) de los servidores como su dirección IP.</p>
<p><strong>Ejemplo</strong></p>
<p>PersistentChatServer01.contoso.com 10.10.10.1</p>
<p>PersistentChatServer02.contoso.com 10.10.10.2</p>
<p>Un registro A interno que resuelve el nombre de dominio completo (FQDN) de los servidores como su dirección IP.</p>
<p><strong>Ejemplo</strong></p>
<p>PersistentChatPool.contoso.com 10.10.10.1</p>
<p>PersistentChatPool.contoso.com 10.10.10.2</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

