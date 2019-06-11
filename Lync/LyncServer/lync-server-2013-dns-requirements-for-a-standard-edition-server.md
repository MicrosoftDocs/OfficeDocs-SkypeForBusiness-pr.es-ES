---
title: 'Lync Server 2013: Requisitos DNS para un servidor Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for a Standard Edition server
ms:assetid: 5d1daf54-6e60-4ce0-9254-7d57a0835fa4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204936(v=OCS.15)
ms:contentKeyID: 48184259
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7508fea0fa6640546bda4f1ecb559821d468803d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835371"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-a-standard-edition-server-in-lync-server-2013"></a>Requisitos DNS para un servidor Standard Edition en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

En esta sección se describen los registros del sistema de nombres de dominio (DNS) necesarios para la implementación de servidores Standard Edition.

<div>

## <a name="dns-records-for-standard-edition-servers"></a>Registros de DNS para servidores Standard Edition

En la tabla siguiente se especifican los requisitos DNS para la implementación de Lync Server 2013 Standard Edition.


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
<td><p>Servidor Standard Edition</p></td>
<td><p>Un registro A interno que resuelve el nombre de dominio completo (FQDN) del servidor en su dirección IP.</p></td>
</tr>
<tr class="even">
<td><p>Inicio de sesión de clientes automático</p></td>
<td><p>Para cada dominio SIP admitido, un registro SRV para _sipinternaltls. _ TCP. &lt;dominio&gt; sobre el puerto 5061 que se asigna al FQDN del servidor Standard Edition que autentica y redirige las solicitudes de inicio de sesión de los clientes. Para obtener más información, consulte <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">requisitos de DNS para el inicio de sesión automático de cliente en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Detección del servicio web de actualización de dispositivos por los dispositivos de comunicaciones unificadas (UC)</p></td>
<td><p>Un registro A interno con el nombre ucupdates-R2. &lt;Dominio&gt; SIP que se resuelve como la dirección IP del servidor Standard Edition que aloja el servicio Web de actualización de dispositivos. En una situación en la que un dispositivo de comunicaciones unificadas esté activado, pero en el que nunca un usuario inició sesión, el registro A permite al dispositivo detectar el servidor que hospeda el servicio web de actualización de dispositivos y obtener actualizaciones. De lo contrario, los dispositivos obtienen la información del servidor a través del aprovisionamiento en banda la primera vez que un usuario inicia sesión. Para obtener más información, vea <a href="lync-server-2013-device-update-web-service.md">servicio Web de actualización de dispositivos en Lync Server 2013</a> en la documentación de operaciones.</p></td>
</tr>
<tr class="even">
<td><p>Un proxy inverso compatible con el tráfico HTTP</p></td>
<td><p>Un registro A externo que resuelve el FQDN externo de la granja de servidores web en la dirección IP externa del proxy inverso. Los clientes y los dispositivos de UC usan este registro para conectarse al proxy inverso. Para obtener más información, consulte <a href="lync-server-2013-determine-dns-requirements.md">determinar los requisitos de DNS para Lync Server 2013</a> en la documentación de planeación.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Vea también


[Requisitos de DNS para el inicio de sesión automático de cliente en Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)  
[Determinar los requisitos DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  


[Servicio web de actualización de dispositivos en Lync Server 2013](lync-server-2013-device-update-web-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

