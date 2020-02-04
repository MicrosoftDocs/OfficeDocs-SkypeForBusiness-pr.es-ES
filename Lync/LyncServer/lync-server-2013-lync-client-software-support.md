---
title: 'Lync Server 2013: compatibilidad con el software de cliente de Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync client software support
ms:assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412781(v=OCS.15)
ms:contentKeyID: 48184994
ms.date: 02/25/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c17f30b05141e9b47ce09685ff18cd166c195f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765521"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-client-software-support-in-lync-server-2013"></a>Compatibilidad del software de cliente de Lync en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-02-25_

En esta sección se resume la compatibilidad de software para Lync 2013 y el complemento de reunión en línea para Lync 2013.

<div>


> [!NOTE]  
> El complemento de reunión en línea para Lync 2013, que admite la administración de reuniones desde el cliente de mensajería y colaboración de Outlook, se instala automáticamente con Lync 2013.



</div>

### <a name="software-requirements-for-lync-2013-and-the-online-meeting-add-in-for-lync-2013"></a>Requisitos de software para Lync 2013 y complemento de reuniones en línea para Lync 2013

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente del sistema</th>
<th>Requisito mínimo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Sistema operativo Windows</p></td>
<td><p>Windows 10</p>
<p>Windows 8.1</p>
<p>Windows 8</p>
<p>Sistema operativo Windows 7</p>
<p>Windows Server 2008 R2 con el Service Pack más reciente</p>
<div>

> [!NOTE]  
> Lync 2013 y el complemento de reunión en línea para Lync 2013 no son compatibles con Windows Vista o Windows XP (cualquier versión).


</div></td>
</tr>
<tr class="even">
<td><p>Instalación y actualizaciones</p></td>
<td><p>Permisos y derechos de administrador</p></td>
</tr>
<tr class="odd">
<td><p>Explorador</p></td>
<td><p>Explorador Internet Explorer 11</p>
<p>Explorador de Internet de Internet Explorer 10</p>
<p>Explorador Internet Explorer 9</p>
<p>Explorador Internet Explorer 8</p>
<p>Explorador Internet Explorer 7</p>
<p>Explorador web Mozilla Firefox</p>
<div>

> [!NOTE]  
> Si está usando Lync con Microsoft Exchange Online y su organización ha implementado un proxy HTTP de autenticación, se necesita Internet Explorer 9 o Internet Explorer 8.


</div></td>
</tr>
<tr class="even">
<td><p>Integración de Microsoft Office</p></td>
<td><p>Para todo el conjunto de características de integración:</p>
<ul>
<li><p>Cliente de mensajería y colaboración de Outlook 2013</p></li>
<li><p>Cliente de mensajería y colaboración de Outlook 2010</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Integración de Microsoft Exchange</p></td>
<td><p>Para todo el conjunto de características de integración:</p>
<ul>
<li><p>Microsoft Exchange Server 2013</p></li>
<li><p>Microsoft Exchange Server 2010</p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>

## <a name="macintosh-operating-systems"></a>Sistemas operativos Macintosh

Lync 2013 solo está disponible para Windows. Sin embargo, Lync Server 2013 admite los siguientes clientes en equipos que ejecutan Mac OS 10.5.8 o versiones más recientes de los sistemas operativos Service Packs o versiones (basados en Intel) (no se admite actualmente el sistema operativo de Mac OS 10,9). Para obtener más información sobre las características admitidas, vea [tablas de comparación de clientes para Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md).

  - Microsoft Lync para Mac 2011 (consulte "Guía de implementación de Lync para Mac 2011 [http://go.microsoft.com/fwlink/p/?LinkId=268786](http://go.microsoft.com/fwlink/p/?linkid=268786)" en la)

  - Microsoft Communicator para Mac 2011 (consulte la "Guía de implementación de Communicator para Mac [http://go.microsoft.com/fwlink/p/?LinkId=268787](http://go.microsoft.com/fwlink/p/?linkid=268787)2011" en la)

</div>

<div>

## <a name="lync-web-app-browsers"></a>Exploradores de Lync Web App

Lync Web App admite combinaciones específicas de sistemas operativos y exploradores. Para obtener más información, consulte [plataformas compatibles con Lync Web App para Lync Server 2013](lync-server-2013-lync-web-app-supported-platforms.md) en la documentación de planeación.

</div>

<div>

## <a name="microsoft-office-supportability"></a>Compatibilidad con Microsoft Office

Los clientes de Lync Server 2013 admiten la integración con varias versiones de Microsoft Office, tal y como se resume en esta sección.

  - Las características de integración de Lync 2013 son compatibles con Outlook 2013 y Microsoft Outlook 2010.

  - Las características de integración de Lync 2013 son compatibles con Microsoft Exchange Server 2013 y Microsoft Exchange Server 2010.

  - El complemento de reunión en línea para Lync 2013 es compatible con Office 2013 y Microsoft Office 2010.

</div>

<div>

## <a name="using-mandatory-profiles"></a>Uso de perfiles obligatorios

Si los usuarios planean usar las características de conferencia de Lync 2013, no deben usar perfiles obligatorios de servicios de dominio de Active Directory para iniciar sesión en el cliente de Lync 2013. Como los perfiles obligatorios son de solo lectura, las claves de infraestructura de clave pública (PKI) que se requieren para las conferencias de Lync 2013 no se pueden guardar en el perfil. Para obtener más información, consulte el artículo 2552221 de Microsoft Knowledge base, "la característica Conferencia de Lync 2010 falla cuando el usuario inicia sesión con un perfil [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2552221](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2552221)de usuario obligatorio" en.

</div>

<div>

## <a name="see-also"></a>Vea también


[Compatibilidad de hardware del cliente Lync en Lync Server 2013](lync-server-2013-lync-client-hardware-support.md)  
[Requisitos de vídeo de cliente de Lync para Lync Server 2013](lync-server-2013-lync-client-video-requirements.md)  
[Clientes admitidos de implementaciones anteriores en Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

