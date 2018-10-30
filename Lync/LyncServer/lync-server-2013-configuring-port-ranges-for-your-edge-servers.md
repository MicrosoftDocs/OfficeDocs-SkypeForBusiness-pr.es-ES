---
title: Configuración de los intervalos de puertos para servidores perimetrales
TOCTitle: Configuración de los intervalos de puertos para servidores perimetrales
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48275604
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de los intervalos de puertos para servidores perimetrales

 

_**Última modificación del tema:** 2015-07-24_

Con los servidores perimetrales, no tendrá que configurar de forma independiente los intervalos de puertos para el uso compartido de aplicaciones, audio y vídeo. Del mismo modo, no es necesario que los intervalos de puertos utilizados para los servidores perimetrales coincidan con los utilizados con los servidores de mediación, aplicación y conferencia. No obstante, para facilitar la administración, puede que desee cambiar los intervalos de puertos del de los servidores perimetrales para que coincidan con los de los otros servidores. Supongamos que ha configurado los servidores de mediación, aplicación y conferencia para que usen estos intervalos de puertos:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de paquete</th>
<th>Puerto inicial</th>
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
<td><p><strong>Total</strong></p></td>
<td><p>--</p></td>
<td><p>24730</p></td>
</tr>
</tbody>
</table>


Como puede ver, sus intervalos de puertos para el uso compartido de aplicaciones, vídeo y audio comienzan en el puerto 40803 y abarcan un total de 24732 puertos. Si lo prefiere, puede configurar un servidor perimetral determinado para que utilice estos valores de puerto generales con un comando similar a este del Shell de administración de Communications Server:

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

También puede usar el comando siguiente para configurar simultáneamente todos los servidores perimetrales de su organización:

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

Puede comprobar la configuración actual de puertos de sus servidores perimetrales con este comando del Shell de administración de Lync Server:

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

