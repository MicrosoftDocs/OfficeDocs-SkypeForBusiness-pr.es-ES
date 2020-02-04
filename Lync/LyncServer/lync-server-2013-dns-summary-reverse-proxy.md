---
title: 'Lync Server 2013: Resumen DNS - Proxy inverso'
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
ms.openlocfilehash: ae4834ce608f6726403e8742a4d506b173309b35
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a>Resumen DNS - Proxy inverso en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-22_

Para configurar dos adaptadores de red en el proxy inverso, siga estos pasos:

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a>Requisitos del adaptador de red de proxy inverso

  - Ejemplo de **adaptador de red 1 (interfaz interna)**
    
    Interfaz interna con 172.25.33.40 asignado.
    
    No hay ninguna puerta de enlace predeterminada definida.
    
    Asegúrese de que haya una ruta desde la red que contiene la interfaz interna de proxy inverso a cualquier red que contenga servidores de grupos de servidores de aplicaciones para el usuario de Lync Server (por ejemplo, de 172.25.33.0 a 192.168.10.0).

  - Ejemplo de **adaptador de red 2 (interfaz externa)**
    
    Se asigna al menos una dirección IP pública a este adaptador de red.
    
    La puerta de enlace está definida para señalar el router o el firewall integrado en el perímetro exterior. (10.45.16.1 en el escenario ejemplos)

### <a name="dns-records-required-for-reverse-proxy"></a>Registros DNS necesarios para el proxy inverso

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
<th>Se asigna a/comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS externo/A</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>Escucha asignada para recursos publicados externamente</p></td>
<td><p>Servicios web externos de la implementación interna. Se pueden definir y crear registros adicionales para todos los grupos y servidores únicos para cualquier dominio SIP que use este proxy inverso y para los que haya definido servicios web externos.</p></td>
</tr>
<tr class="even">
<td><p>DNS externo/A</p></td>
<td><p>webdirext.contoso.com</p></td>
<td><p>Escucha asignada para recursos publicados externamente</p></td>
<td><p>Servicios web externos para los grupos de directores o directores de su implementación. Puede definir tantos directores como un número de directores distintos, de los cuales pueden estar asociados a otros dominios SIP.</p>
<div>

> [!IMPORTANT]  
> Definir los registros DNS para y publicar los directores no es una de las agrupaciones front-end ni la decisión de director. Si está usando directores, debe definir y publicar el director y los servicios web externos del grupo de servidores front-end. Los tipos de tráfico específicos (para autenticación y otros usos) se enviarán primero al Director, si está definido en la topología.


</div></td>
</tr>
<tr class="odd">
<td><p>DNS externo/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Escucha asignada para recursos publicados externamente</p></td>
<td><p>Conferencias de acceso telefónico local publicadas externamente</p></td>
</tr>
<tr class="even">
<td><p>DNS externo/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Escucha asignada para recursos publicados externamente</p></td>
<td><p>Conferencias publicadas externamente</p></td>
</tr>
<tr class="odd">
<td><p>DNS externo/A</p></td>
<td><p>officewebapps01.contoso.com</p></td>
<td><p>Escucha asignada para el servidor de Office Web Apps</p></td>
<td><p>Office Web Apps Server implementado internamente o en el perímetro, y publicado para acceso externo de clientes</p></td>
</tr>
<tr class="even">
<td><p>DNS externo/A</p></td>
<td><p>lyncdiscover.contoso.com</p></td>
<td><p>Escucha asignada para recursos publicados externamente</p></td>
<td><p>Registro externo de detección de Lync para detección automática publicada externamente e incluye movilidad, Microsoft Lync Web App y la aplicación Web de programador</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

