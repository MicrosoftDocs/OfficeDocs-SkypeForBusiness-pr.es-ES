---
title: 'Lync Server 2013: requisitos de DNS para servidores de chat persistentes'
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
ms.openlocfilehash: b97d3238c64173cb5f9bfcfc12dce40f987da123
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-persistent-chat-servers-in-lync-server-2013"></a>Requisitos de DNS para servidores de chat persistentes en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-28_

En esta sección se describen los registros del sistema de nombres de dominio (DNS) necesarios para la implementación de servidores de chat persistentes.

<div>

## <a name="dns-records-for-persistent-chat-servers"></a>Registros de DNS para los servidores de chat persistente

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
<td><p>Un registro A interno que resuelve el nombre de dominio completo (FQDN) del servidor en su dirección IP.</p></td>
</tr>
<tr class="even">
<td><p>Grupo de servidores de chat persistente</p></td>
<td><p>Un registro A interno que resuelve el nombre de dominio completo (FQDN) de los servidores en su dirección IP.</p>
<p><strong>Ejemplo</strong></p>
<p>PersistentChatServer01.contoso.com 10.10.10.1</p>
<p>PersistentChatServer02.contoso.com 10.10.10.2</p>
<p>Un registro A interno que resuelve el nombre de dominio completo (FQDN) de los servidores en su dirección IP.</p>
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

