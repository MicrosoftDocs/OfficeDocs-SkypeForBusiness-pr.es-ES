---
title: 'Lync Server 2013: Resumen de DNS-proxy inverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Reverse proxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48183755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a468e74206fdc6bad8f078267688450636b8a725
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532147"
---
# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a>Resumen de DNS-proxy inverso en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-22_

Puede configurar dos adaptadores de red en el proxy inverso de la siguiente forma:

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a>Requisitos del adaptador de red con proxy inverso

  - Ejemplo de **adaptador de red 1 (Interfaz interna)**
    
    Interfaz interna con 172.25.33.40 asignada.
    
    No se ha definido ninguna puerta de enlace predeterminada.
    
    Asegúrese de que existe una ruta desde la red que contiene la interfaz interna del proxy inverso a cualquier red que contenga servidores de grupo de servidores front-end de Lync Server (por ejemplo, de 172.25.33.0 a 192.168.10.0).

  - Ejemplo de **adaptador de red 2 (Interfaz externa)**
    
    Se asigna un mínimo de una dirección IP pública a este adaptador de red.
    
    Se ha definido la puerta de enlace para señalar al enrutador o al firewall integrado de su perímetro exterior. (10.45.16.1 en los ejemplos del escenario)

### <a name="dns-records-required-for-reverse-proxy"></a>Registros DNS requeridos para proxy inverso

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ubicación/tipo/puerto</th>
<th>FQDN</th>
<th>Dirección IP</th>
<th>Asignado a/Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS/A externo</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>Escucha asignada para los recursos publicados externamente</p></td>
<td><p>Servicios web externos desde la implementación interna. Se pueden definir y crear registros adicionales para todos los grupos de servidores y servidores únicos para cualquier dominio de SIP que use este proxy inverso y tenga definidos servicios web externos.</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externo</p></td>
<td><p>webdirext.contoso.com</p></td>
<td><p>Escucha asignada para los recursos publicados externamente</p></td>
<td><p>Servicios web externos para los directores o grupos de directores en su implementación de. Puede definir tantos directores como un número de directores distintos, de los cuales se pueden asociar a otros dominios SIP.</p>
<div>

> [!IMPORTANT]  
> La definición de los registros DNS para y la publicación de los directores no es un grupo de servidores front-end ni la decisión de director. Si usa directores, debe definir y publicar el director y los servicios web externos del grupo de servidores front-end. Los tipos de tráfico específicos (para la autenticación y otros usos) se enviarán primero al Director, si está definido en la topología.


</div></td>
</tr>
<tr class="odd">
<td><p>DNS/A externo</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Escucha asignada para los recursos publicados externamente</p></td>
<td><p>Conferencias de acceso telefónico local publicadas externamente</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externo</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Escucha asignada para los recursos publicados externamente</p></td>
<td><p>Conferencias publicadas externamente</p></td>
</tr>
<tr class="odd">
<td><p>DNS/A externo</p></td>
<td><p>officewebapps01.contoso.com</p></td>
<td><p>Escucha asignada para Office Web Apps Server</p></td>
<td><p>Office Web Apps Server implementado internamente o en el perímetro, y publicado para el acceso de clientes externos</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externo</p></td>
<td><p>lyncdiscover.contoso.com</p></td>
<td><p>Escucha asignada para los recursos publicados externamente</p></td>
<td><p>Registro externo de detección de Lync para la detección automática publicada externamente e incluye movilidad, aplicación Web de Microsoft Lync y aplicación Web de programador</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

