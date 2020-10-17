---
title: 'Lync Server 2013: configuración de intervalos de puertos para los servidores de conferencia, aplicación y mediación'
description: 'Lync Server 2013: configuración de intervalos de puertos para los servidores de conferencia, aplicación y mediación.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Conferencing, Application, and Mediation servers
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
ms.date: 05/01/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb3f51e42c86b667b6990f41640bf09e12e840c2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558766"
---
# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a>Configuración de intervalos de puertos en Lync Server 2013 para los servidores de conferencia, aplicación y mediación

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-04-30_

Con el fin de implementar Calidad de servicio, debe configurar intervalos de puertos idénticos para audio, vídeo y aplicaciones que comparten los servidores de conferencias, aplicaciones y la mediación; además, los intervalos de puertos no deben superponerse de ninguna manera. Para usar un ejemplo sencillo, suponga que usa los puertos 10000 hasta 10999 para vídeo en los servidores de conferencias. Eso significa que también deben reservar los puertos 10000 hasta 10999 para vídeo en sus servidores de aplicaciones y mediación. Si no lo haces, QoS no funcionará como se espera.

Del mismo modo, suponga que reserva los puertos 10000 hasta 10999 para vídeo, pero luego reserva los puertos 10500 hasta 11999 para audio. Esto puede crear problemas de Calidad de servicio, porque los intervalos de puerto se superponen. Con QoS, cada modalidad debe tener un único conjunto de puertos: si usa los puertos 10000 hasta 10999 para vídeo, luego tendrá que usar otro intervalo (por ejemplo, 11000 hasta 11999) para audio.

De forma predeterminada, los intervalos de puertos de audio y vídeo no se superponen en Microsoft Lync Server 2013; sin embargo, los intervalos de puertos asignados al uso compartido de aplicaciones se superponen con los intervalos de puertos de audio y vídeo. (Lo que, a su vez, significa que ninguno de estos intervalos es único). Puede comprobar los intervalos de puertos existentes para los servidores de conferencia, aplicación y mediación mediante la ejecución de los siguientes tres comandos desde dentro del shell de administración de Lync Server 2013:

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> Como puede ver en los comandos anteriores, a cada tipo de puerto: audio, vídeo y uso compartido de aplicaciones se les asigna dos valores de propiedad separados: el puerto de inicio y el número de puerto. El inicio de puerto indica el primer puerto que se usa para esa modalidad; por ejemplo, si el puerto de inicio de audio es igual a 50000, significa que el primer puerto que se usa para el tráfico de audio es puerto 50000. Si el recuento del puerto de audio es 2 (que no es un valor válido, pero se usa aquí para fines de ilustración) eso significa que solo se asignan para el audio 2 puertos. Si el primer puerto es el puerto 50000 y hay un total de dos puertos, eso significa que el segundo puerto debe ser el 50001 (los intervalos de puertos tienen que ser contiguos). Como resultado, el intervalo de puertos de audio sería del puerto 50000 hasta el 50001, incluidos.<BR>Tenga en cuenta que el servidor de aplicaciones y el servidor de mediación solo admiten QoS para audio; no necesita cambiar el vídeo o el uso compartido de aplicaciones de puertos en sus servidores de aplicaciones o mediación.



</div>

Si ejecuta los tres comandos anteriores verá que los valores de puerto predeterminados para Lync Server 2013 son los siguientes:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Propiedad</th>
<th>Servidor de conferencias</th>
<th>Servidor de aplicaciones</th>
<th>Servidor de mediación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AudioPortStart</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
</tr>
<tr class="even">
<td><p>AudioPortCount</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>VideoPortStart</p></td>
<td><p>57501</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>VideoPortCount</p></td>
<td><p>8034</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationSharingPortStart</p></td>
<td><p>49152</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>ApplicationSharingPortCount</p></td>
<td><p>16383</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>


Como se indicó anteriormente, al configurar los puertos de Lync Server para QoS, debe asegurarse de que: 1) la configuración del puerto de audio es idéntica en los servidores de conferencia, aplicación y mediación. y 2) los intervalos de puertos no se superponen. Si observa detenidamente la tabla anterior, verá que los intervalos de puertos son idénticos a través de los tres tipos de servidores. Por ejemplo, el puerto de inicio de audio se establece en Puerto 49152 en cada tipo de servidor y el número total de puertos reservados en cada servidor de audio también es idéntico: 8348. Sin embargo, el intervalo de puertos se superpone: los puertos de audio comienzan en el puerto 49152, pero, al hacerlo así, los puertos se reservan para uso compartido de aplicaciones. Para usar correctamente la Calidad de servicio, el uso compartido de aplicaciones debe configurarse para utilizar un único intervalo de puertos. Por ejemplo, podría configurar el uso compartido de aplicaciones para que se inicie en el puerto 40803 y use 8348 puertos. ¿Por qué 8348 puertos? Si agrega estos valores juntos--40803 + 8348, significa que el uso compartido de aplicaciones usará los puertos 40803 a través del puerto 49150. Ya que los puertos de audio no comienzan hasta el puerto 49152, ya no tendrá ningún intervalo de puertos superpuestos.

Después de haber seleccionado el nuevo intervalo de puertos para uso compartido de aplicaciones, puede hacer el cambio con el cmdlet Set-CsConferencingServer. Este cambio no tiene que hacerse en los servidores de aplicaciones o en los servidores de mediación, porque estos servidores no controlan tráfico de uso compartido de aplicaciones. Solo necesita cambiar los valores del puerto en estos servidores si decide volver a asignar los puertos usados para el tráfico de audio.

Para modificar los valores de puerto para el uso compartido de aplicaciones en un solo servidor de conferencia, ejecute un comando similar a este desde dentro del shell de administración de Lync Server:

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

Si desea realizar estos cambios en todos los servidores de conferencias, puede ejecutar este comando en su lugar:

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

Después de cambiar la configuración del puerto debe detener y reiniciar cada servicio afectado por los cambios.

No es obligatorio que los servidores de conferencias, servidores de aplicaciones y servidores de mediación compartan el mismo intervalo de puertos exacto; el único requisito real es que reserve intervalos de puertos únicos en todos los servidores. Sin embargo, la administración suele ser más fácil si se usa el mismo conjunto de puertos en todos los servidores.

</div>

<span> </span>

</div>

</div>

</div>

