---
title: 'Lync Server 2013: compatibilidad con software de cliente de Lync'
description: 'Lync Server 2013: compatibilidad con software de cliente de Lync.'
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
ms.openlocfilehash: 80300e46d82f5947bd68713bbea036548a1fabee
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570516"
---
# <a name="lync-client-software-support-in-lync-server-2013"></a>Compatibilidad de software de cliente de Lync en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-02-25_

En esta sección se resume la compatibilidad de software para Lync 2013 y el complemento para reunión en línea para Lync 2013.

<div>


> [!NOTE]  
> El complemento para reunión en línea para Lync 2013, que admite la administración de reuniones desde el cliente de colaboración y mensajería de Outlook, se instala automáticamente con Lync 2013.



</div>

### <a name="software-requirements-for-lync-2013-and-the-online-meeting-add-in-for-lync-2013"></a>Requisitos de software para Lync 2013 y el complemento para reunión en línea para Lync 2013

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
> Lync 2013 y el complemento para reunión en línea para Lync 2013 no son compatibles con Windows Vista o Windows XP (cualquier versión).


</div></td>
</tr>
<tr class="even">
<td><p>Instalación y actualizaciones</p></td>
<td><p>Permisos y derechos de administrador</p></td>
</tr>
<tr class="odd">
<td><p>Explorador</p></td>
<td><p>Explorador de Internet Internet Explorer 11</p>
<p>Explorador de Internet de Internet Explorer 10</p>
<p>Explorador de Internet de Internet Explorer 9</p>
<p>Explorador de Internet Internet Explorer 8</p>
<p>Explorador de Internet Internet Explorer 7</p>
<p>Explorador web Mozilla Firefox</p>
<div>

> [!NOTE]  
> Si usa Lync con Microsoft Exchange Online y su organización ha implementado un proxy HTTP de autenticación, se requiere Internet Explorer 9 o Internet Explorer 8.


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

Lync 2013 solo está disponible para Windows. Sin embargo, Lync Server 2013 admite los siguientes clientes en equipos que ejecutan Mac OS 10.5.8 o sistemas operativos más recientes de Service Pack o versiones (basados en Intel) (no se admite actualmente el sistema operativo Mac OS 10,9). Para obtener más información sobre las características admitidas, consulte [Client Comparison tables for Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md).

  - Microsoft Lync para Mac 2011 (consulte la "Guía de implementación de Lync para Mac 2011" en la [https://go.microsoft.com/fwlink/p/?LinkId=268786](https://go.microsoft.com/fwlink/p/?linkid=268786) )

  - Microsoft Communicator para Mac 2011 (consulte la "Guía de implementación de Communicator para Mac 2011" en [https://go.microsoft.com/fwlink/p/?LinkId=268787](https://go.microsoft.com/fwlink/p/?linkid=268787) )

</div>

<div>

## <a name="lync-web-app-browsers"></a>Exploradores de Lync Web App

Lync Web App admite combinaciones específicas de sistemas operativos y exploradores. Para obtener información detallada, consulte [Lync Web App Supported platforms for Lync Server 2013](lync-server-2013-lync-web-app-supported-platforms.md) en la documentación referente a la planeación.

</div>

<div>

## <a name="microsoft-office-supportability"></a>Compatibilidad con Microsoft Office

Los clientes de Lync Server 2013 admiten la integración con diversas versiones de Microsoft Office, como se resume en esta sección.

  - Las características de integración de Lync 2013 se admiten en Outlook 2013 y Microsoft Outlook 2010.

  - Las características de integración de Lync 2013 son compatibles con Microsoft Exchange Server 2013 y Microsoft Exchange Server 2010.

  - El complemento para reunión en línea para Lync 2013 es compatible con Office 2013 y Microsoft Office 2010.

</div>

<div>

## <a name="using-mandatory-profiles"></a>Uso de perfiles obligatorios

Si los usuarios planean usar las características de conferencia de Lync 2013, no deben usar los perfiles obligatorios de servicios de dominio de Active Directory para iniciar sesión en el cliente de Lync 2013. Debido a que los perfiles obligatorios son de solo lectura, las claves de infraestructura de clave pública (PKI) necesarias para la Conferencia de Lync 2013 no se pueden guardar en el perfil. Para obtener más información, consulte el artículo 2552221 de Microsoft Knowledge base, "error en la característica de conferencia de Lync 2010 cuando el usuario ha iniciado sesión con un perfil de usuario obligatorio", en [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2552221](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2552221) .

</div>

<div>

## <a name="see-also"></a>Consulte también


[Compatibilidad de hardware del cliente Lync en Lync Server 2013](lync-server-2013-lync-client-hardware-support.md)  
[Requisitos de vídeo del cliente de Lync para Lync Server 2013](lync-server-2013-lync-client-video-requirements.md)  
[Clientes admitidos de implementaciones anteriores en Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

