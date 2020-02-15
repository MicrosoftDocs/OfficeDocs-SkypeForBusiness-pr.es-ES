---
title: 'Lync Server 2013: clientes admitidos de implementaciones anteriores'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported clients from previous deployments
ms:assetid: 69d427f8-57a5-4244-b2ed-f2eb7600285e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398499(v=OCS.15)
ms:contentKeyID: 48184390
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cff76b750b2c6643ec1bf6ac3419a9892719ea4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029841"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-clients-from-previous-deployments-in-lync-server-2013"></a>Clientes admitidos de implementaciones anteriores en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-12-14_

En un escenario de coexistencia, los clientes de Lync Server 2013 pueden interactuar con clientes de versiones anteriores de Lync Server y Office Communications Server. A diferencia de las versiones anteriores, Lync Server 2010 admite los nuevos clientes de Lync 2013. Esto permite a las organizaciones que actualizan desde Lync Server 2010 implementar nuevos clientes independientes de las actualizaciones de Lync Server.

<div>

## <a name="supported-server-and-client-combinations"></a>Combinaciones de servidor y cliente compatibles

La tabla siguiente muestra las combinaciones compatibles de versiones de cliente y versiones de servidor. Lync Server 2013 admite dos versiones de cliente anteriores y Lync Server 2010 admite el nuevo cliente de Lync 2013.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Client</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
<td><p>No compatible</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2013</p></td>
<td><p>Admitido</p></td>
<td><p>No compatible</p></td>
<td><p>No se admite</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
<td><p>No compatible</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendant</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
<td><p>No compatible</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Group Chat</p></td>
<td><p>No aplicable</p></td>
<td><p>Supported1</p></td>
<td><p>No aplicable</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2010</p></td>
<td><p>No se admite</p></td>
<td><p>Admitido</p></td>
<td><p>No compatible</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Attendee</p></td>
<td><p>No Supported2</p></td>
<td><p>Admitido</p></td>
<td><p>No compatible</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable3</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
</tr>
<tr class="odd">
<td><p>Operador de Microsoft Office Communications Server 2007 R2</p></td>
<td><p>No se admite</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007</p></td>
<td><p>No se admite</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
</tr>
<tr class="odd">
<td><p>Office Live Meeting 2007</p></td>
<td><p>No se admite</p></td>
<td><p>Compatible</p></td>
<td><p>Compatible</p></td>
</tr>
</tbody>
</table>


1Pda Microsoft Lync Server 2010, la funcionalidad de chat en grupo estaba disponible con el servidor de chat en grupo, una aplicación de confianza de terceros para Lync Server 2010. Los clientes de Lync 2013 no son compatibles con Lync Server 2010, chat en grupo.

2Lync Web App 2013 ahora proporciona una experiencia completa para la reunión, incluido el audio y el vídeo del equipo, y se considera el reemplazo de Lync 2010 asistente.

las características de presencia y mensajería instantánea de 3The en Office Communicator 2007 R2 son compatibles con Lync Server 2013, pero las características de conferencia no lo son. Durante la migración de Office Communications Server 2007 R2, Office Communicator 2007 R2 es apto para la presencia y la interoperabilidad de mi, pero los usuarios deben usar Lync Web App 2013 para unirse a reuniones de Lync Server 2013.

<div>


> [!NOTE]  
> Para obtener más información sobre la capacidad de los clientes de Lync Server 2013 de coexistir e interactuar con clientes de versiones anteriores de Lync Server y Office Communications Server, consulte <A href="lync-server-2013-client-interoperability-in-lync-2013.md">Client Interoperability in lync 2013</A> en la documentación de planeación.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

