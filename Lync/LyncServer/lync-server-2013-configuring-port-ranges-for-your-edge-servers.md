---
title: 'Lync Server 2013: configuración de intervalos de puertos para los servidores perimetrales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Edge Servers
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
ms.date: 07/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6eddf59f6fe4b2575e0e7d70adddb2e94c90e05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a>Configurar intervalos de puertos para los servidores perimetrales en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-07-24_

Con los servidores perimetrales no es necesario configurar distintos intervalos de puertos para el audio, el vídeo y el uso compartido de aplicaciones. del mismo modo, los intervalos de puertos usados para los servidores perimetrales no tienen que coincidir con los intervalos de puertos que se usan en los servidores de conferencias, aplicaciones y mediación. Antes de continuar con nuestro ejemplo, es importante enfatizar que, a pesar de que esta opción existe, le recomendamos que no cambie los intervalos de puerto, ya que esto puede afectar negativamente a algunos escenarios si sale del intervalo de puertos 50000.

Por ejemplo, supongamos que ha configurado los servidores de conferencias, aplicaciones y mediación para que usen estos intervalos de puertos:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de paquete</th>
<th>Puerto de inicio</th>
<th>Número de puertos reservados</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Uso compartido de aplicaciones</p></td>
<td><p>40803</p></td>
<td><p>8348</p></td>
</tr>
<tr class="even">
<td><p>Audio</p></td>
<td><p>49152</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>Vídeo</p></td>
<td><p>57500</p></td>
<td><p>8034</p></td>
</tr>
<tr class="even">
<td><p><strong>Totales</strong></p></td>
<td><p>--</p></td>
<td><p>24730</p></td>
</tr>
</tbody>
</table>


Como puede ver, los intervalos de puertos para el audio, el vídeo y el uso compartido de aplicaciones comienzan en el puerto 40803 y abarcan un total de 24732 puertos. Si lo prefiere, puede configurar un servidor perimetral determinado para usar estos valores de Puerto generales ejecutando un comando similar a este en el shell de administración de Lync Server:

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

O bien, use el comando siguiente para configurar simultáneamente todos los servidores perimetrales de su organización:

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

Puede comprobar la configuración actual del puerto de los servidores perimetrales con este comando del shell de administración de Lync Server:

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

De nuevo, si bien proporcionamos estas opciones, le recomendamos encarecidamente que deje las cosas como están para la configuración del puerto.

</div>

<span> </span>

</div>

</div>

</div>

