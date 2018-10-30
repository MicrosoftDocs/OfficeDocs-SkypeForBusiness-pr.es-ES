---
title: 'Lync Server 2013: Compatibilidad del software cliente Lync'
TOCTitle: Compatibilidad del software cliente Lync
ms:assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412781(v=OCS.15)
ms:contentKeyID: 48276275
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Compatibilidad del software cliente Lync en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

La siguiente tabla contiene los requisitos de hardware y software mínimos para Lync 2013 y para el Complemento para conferencia en línea para Lync 2013.


> [!NOTE]
> El Complemento para conferencia en línea para Lync 2013, que admite la administración de reuniones desde dentro del cliente de colaboración y mensajería de Outlook, se instala automáticamente con Lync 2013.



### Requisitos de software para Lync 2013 y Complemento para conferencia en línea para Lync 2013

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
<td><p>Windows 8,1</p>
<p>Windows 8</p>
<p>Sistema operativo Windows 7</p>
<p>Windows Server 2008 R2 con el Service Pack más reciente</p>
<div>

> [!NOTE]
> Lync 2013 y Complemento para conferencia en línea para Lync 2013 no son compatibles en Windows Vista ni Windows XP (en ninguna versión).


</div></td>
</tr>
<tr class="even">
<td><p>Instalación y actualizaciones</p></td>
<td><p>Permisos y derechos de administrador</p></td>
</tr>
<tr class="odd">
<td><p>Explorador</p></td>
<td><p>Explorador de Internet Windows Internet Explorer 10</p>
<p>Explorador Internet Explorer 9</p>
<p>Internet Explorer 8</p>
<p>Explorador Internet Explorer 7</p>
<p>Explorador web Mozilla Firefox</p>
<div>

> [!NOTE]
> Si está usando Lync con Microsoft Exchange Online y su organización implementó un proxy HTTP de autenticación, se requiere Internet Explorer 9 o Internet Explorer 8.


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


## Sistemas operativos Macintosh

Lync 2013 solo está disponible para Windows. No obstante, Lync Server 2013 es compatible con los siguientes clientes en equipos que ejecuten Mac OS 10.5.8 o sistemas operativos de versiones o Service Packs más recientes (Intel) (actualmente, el sistema operativo de Mac OS 10.9 no es compatible). Para más información sobre características compatibles, consulte [Tablas de comparación de clientes para Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md).

  - Microsoft Lync para Mac 2011 (vea "Guía de implementación de Lync para Mac 2011" en [http://go.microsoft.com/fwlink/p/?LinkId=268786](http://go.microsoft.com/fwlink/p/?linkid=268786))

  - Microsoft Communicator para Mac 2011 (vea "Guía de implementación de Communicator para Mac 2011") en [http://go.microsoft.com/fwlink/p/?LinkId=268787](http://go.microsoft.com/fwlink/p/?linkid=268787))

## Exploradores de Lync Web App

Lync Web App admite combinaciones específicas de sistemas operativos y exploradores. Para obtener más información, consulte [Plataformas admitidas en Lync Web App en Lync Server 2013](lync-server-2013-lync-web-app-supported-platforms.md) en la documentación sobre planeamiento.

## Compatibilidad con Microsoft Office

Los clientes de Lync Server 2013 admiten integración con diversas versiones de Microsoft Office, según se resume en esta sección.

  - Las características de integración de Lync 2013 son compatibles con Outlook 2013 y Microsoft Outlook 2010.

  - Las características de integración de Lync 2013 son compatibles con Microsoft Exchange Server 2013 y Microsoft Exchange Server 2010.

  - El Complemento para reunión en línea de Lync 2013 es compatible con Office 2013 y Microsoft Office 2010.

## Uso de perfiles obligatorios

Si los usuarios planean usar características de conferencia de Lync 2013, no deberían usar perfiles obligatorios de Servicios de dominio de Active Directory para iniciar sesión en el cliente de Lync 2013. Puesto que los perfiles obligatorios son perfiles de usuario de solo lectura, las claves de infraestructura de clave pública (PKI) que son necesarias para la conferencia de Lync 2013 no se pueden guardar en el perfil. Para obtener más información, consulte el artículo 2552221 de Microsoft Knowledge Base, "La característica de conferencia de Lync 2010 provoca error cuando el usuario ha iniciado sesión usando un perfil de usuario obligatorio", en [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2552221](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2552221).

## Vea también

#### Conceptos

[Compatibilidad de hardware del cliente Lync en Lync Server 2013](lync-server-2013-lync-client-hardware-support.md)  
[Requisitos de vídeo del cliente de Lync para Lync Server 2013](lync-server-2013-lync-client-video-requirements.md)  
[Clientes admitidos de implementaciones anteriores en Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md)

