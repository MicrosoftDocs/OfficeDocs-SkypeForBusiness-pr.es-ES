---
title: 'Lync Server 2013: configuración de intervalos de puertos para los servidores de conferencias, aplicaciones y mediación'
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
ms.openlocfilehash: 54aab5efbca06d918cc2dbeccc0e36aee9d4abf8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a>Configuración de intervalos de puertos en Lync Server 2013 para sus servidores de conferencias, aplicaciones y mediación

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-04-30_

Para implementar la calidad de servicio, debe configurar los intervalos de puertos idénticos para el audio, el vídeo y el uso compartido de aplicaciones en sus servidores de conferencias, aplicaciones y mediación. Además, esos intervalos de puertos no deben superponerse de ninguna manera. Para usar un ejemplo sencillo, suponga que usa los puertos 10000 a 10999 para vídeo en los servidores de conferencia. Eso significa que también debe reservar los puertos 10000 a 10999 para vídeo en su aplicación y servidores de mediación. De lo contrario, QoS no funcionará de la forma esperada.

De forma similar, suponga que reserva los puertos 10000 a 10999 para video, pero después reserva los puertos 10500 a 11999 para audio. Esto puede crear problemas de calidad de servicio porque los intervalos de puertos se superponen. Con QoS, cada modalidad debe tener un único conjunto de puertos: Si usas los puertos 10000 a 10999 para video, tendrás que usar un intervalo diferente (por ejemplo, 11000 a 11999 para audio).

De forma predeterminada, los intervalos de puertos de audio y vídeo no se superponen en Microsoft Lync Server 2013; sin embargo, los intervalos de puertos asignados al uso compartido de aplicaciones se superponen con los intervalos de puertos de audio y vídeo. (Que, a su vez, significa que ninguno de estos intervalos es único). Puede comprobar los intervalos de puertos existentes para los servidores de conferencia, aplicación y mediación ejecutando los siguientes tres comandos desde el shell de administración de Lync Server 2013:

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> Como puede ver en los comandos anteriores, cada tipo de puerto (audio, vídeo y uso compartido de aplicaciones) tiene asignados dos valores de propiedad distintos: el inicio del puerto y el recuento de puertos. El inicio del puerto indica el primer puerto utilizado para ese modal; por ejemplo, si el inicio del puerto de audio es igual a 50000, significa que el primer puerto que se usa para el tráfico de audio es el puerto 50000. Si el recuento de puertos de audio es 2 (que no es un valor válido, pero se usa aquí con fines de ilustración) significa que solo se asignan 2 puertos para el audio. Si el primer puerto es el puerto 50000 y hay un total de dos puertos, significa que el segundo puerto debe ser el puerto 50001 (los intervalos de puertos deben ser contiguos). Como resultado, el intervalo de puertos para el audio sería los puertos 50000 a 50001, ambos incluidos.<BR>Ten en cuenta que el servidor de aplicaciones y el servidor de mediación solo admiten QoS para el audio; no es necesario cambiar los puertos de uso compartido de vídeo o aplicaciones en los servidores de aplicaciones o servidores de mediación.



</div>

Si ejecuta los tres comandos anteriores, verá que los valores de puerto predeterminados de Lync Server 2013 se han configurado de esta manera:


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
<th>Servidor de conferencia</th>
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


Como se mencionó anteriormente, al configurar los puertos de Lync Server para QoS, debe asegurarse de que: 1) la configuración del puerto de audio sea idéntica en los servidores de conferencias, aplicaciones y mediación. y 2) los intervalos de puertos no se superponen. Si examina atentamente la tabla anterior, verá que los intervalos de puertos son idénticos en los tres tipos de servidor. Por ejemplo, el puerto de salida de audio se establece en el puerto 49152 en cada tipo de servidor, y el número total de puertos reservados para el audio en cada servidor también es idéntico: 8348. Sin embargo, los intervalos de puertos se superponen: los puertos de audio comienzan en el puerto 49152, pero también hacen que los puertos reservados para uso compartido de aplicaciones. Para hacer uso óptimo de la calidad de servicio, el uso compartido de aplicaciones debe reconfigurarse para que use un intervalo de puertos único. Por ejemplo, puede configurar el uso compartido de aplicaciones para que se inicie en el puerto 40803 y para usar puertos 8348. (¿Por qué 8348 puertos? Si suma esos valores juntos, 40803 + 8348, eso significa que el uso compartido de aplicaciones usará los puertos 40803 a través del puerto 49150. Puesto que los puertos de audio no comienzan hasta el puerto 49152, ya no tendrá intervalos de puertos superpuestos.)

Una vez que haya seleccionado el nuevo intervalo de puertos para compartir aplicaciones, puede realizar su cambio con el cmdlet Set-CsConferencingServer. No es necesario realizar este cambio en los servidores de aplicaciones o en los servidores de mediación, ya que estos servidores no manejan tráfico de uso compartido de aplicaciones. Solo necesita cambiar los valores de puerto en estos servidores si decide reasignar los puertos usados para el tráfico de audio.

Para modificar los valores de puerto para el uso compartido de aplicaciones en un solo servidor de conferencia ejecute un comando similar a este desde el shell de administración de Lync Server:

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

Si desea realizar estos cambios en todos los servidores de conferencia, puede ejecutar este comando en su lugar:

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

Después de cambiar la configuración del puerto, debe detener y reiniciar cada servicio afectado por los cambios.

No es obligatorio que los servidores de conferencia, los servidores de aplicaciones y los servidores de mediación compartan exactamente el mismo intervalo de puertos; el único requisito es que se reserven intervalos de puertos exclusivos en todos los servidores. Sin embargo, la administración generalmente será más fácil si usa el mismo conjunto de puertos en todos los servidores.

</div>

<span> </span>

</div>

</div>

</div>

