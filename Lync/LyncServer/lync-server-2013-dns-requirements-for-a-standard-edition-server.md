---
title: 'Lync Server 2013: requisitos de DNS para un servidor Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for a Standard Edition server
ms:assetid: 5d1daf54-6e60-4ce0-9254-7d57a0835fa4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204936(v=OCS.15)
ms:contentKeyID: 48184259
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12a4d87f0ffa1ab7d6e857a40c2440d35d0b38aa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204866"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-a-standard-edition-server-in-lync-server-2013"></a>Requisitos de DNS para un servidor Standard Edition en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

En esta sección se describen los registros del sistema de nombres de dominio (DNS) necesarios para la implementación de servidores Standard Edition.

<div>

## <a name="dns-records-for-standard-edition-servers"></a>Registros DNS para servidores Standard Edition

En la tabla siguiente se especifican los requisitos de DNS para la implementación de servidor de Lync Server 2013 Standard Edition.


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
<td><p>Registro A interno que resuelve el nombre de dominio completo (FQDN) del servidor en su dirección IP.</p></td>
</tr>
<tr class="even">
<td><p>Inicio de sesión automático de clientes</p></td>
<td><p>Para cada dominio SIP compatible, un registro SRV para _sipinternaltls. _tcp. &lt;dominio&gt; a través del puerto 5061 que se asigna al FQDN del servidor Standard Edition que autentica y redirige las solicitudes de inicio de sesión de los clientes. Para obtener más información, consulte <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">requisitos de DNS para el inicio de sesión automático de los clientes en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Detección del servicio web de actualización de dispositivos mediante dispositivos de comunicaciones unificadas (UC)</p></td>
<td><p>Un registro A interno con el nombre ucupdates-R2. &lt;Dominio&gt; SIP que se resuelve en la dirección IP del servidor Standard Edition que hospeda el servicio Web de actualización de dispositivos. En una situación en la que un dispositivo de comunicaciones unificadas esté activado, pero nunca ningún usuario se haya registrado en él, el registro A permite al dispositivo detectar el servidor que hospeda el Servicio web de actualización de dispositivos y obtener actualizaciones. En otro caso, los dispositivos obtienen la información del servidor a través del aprovisionamiento en banda la primera vez que un usuario inicia sesión. Para obtener más información, vea <a href="lync-server-2013-device-update-web-service.md">servicio Web de actualización de dispositivos en Lync Server 2013</a> en la documentación referente a las operaciones.</p></td>
</tr>
<tr class="even">
<td><p>Un proxy inverso para admitir el tráfico HTTP</p></td>
<td><p>Un registro A externo que resuelva el FQDN externo de la granja de servidores web en la dirección IP externa del proxy inverso. Los clientes y los dispositivos de comunicaciones unificadas usan este registro para conectarse al proxy inverso. Para obtener más información, consulte <a href="lync-server-2013-determine-dns-requirements.md">determinar los requisitos de DNS para Lync Server 2013</a> en la documentación referente a la planeación.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Consulta también


[Requisitos de DNS para el inicio de sesión automático de los clientes en Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)  
[Determinación de los requisitos de DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  


[Servicio Web de actualización de dispositivos en Lync Server 2013](lync-server-2013-device-update-web-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

