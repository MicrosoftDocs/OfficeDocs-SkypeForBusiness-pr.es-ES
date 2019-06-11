---
title: 'Lync Server 2013: Proceso de implementación para la integración de la mensajería unificada de Exchange hospedada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for integrating hosted Exchange UM with Lync Server
ms:assetid: dbec9c38-7f66-419d-b8c3-c61380052cac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398968(v=OCS.15)
ms:contentKeyID: 48185586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6269efd85261c702c77568fac67c96034ba01a71
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835469"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a>Proceso de implementación para la integración de la mensajería unificada de Exchange hospedada con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-25_

Una planeación eficaz para integrar Lync Server 2013 con mensajería unificada de Exchange hospedado (UM) requiere tener en cuenta lo siguiente:

  - Requisitos previos para integrar Lync Server 2013 con mensajería unificada de Exchange hospedado

  - Pasos necesarios durante el proceso de integración

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a>Requisitos previos de implementación para la integración con mensajería unificada de Exchange hospedado

Antes de que pueda comenzar el proceso de integración, debe haber implementado ya Lync Server 2013 (como mínimo, un grupo de servidores front-end o un servidor Standard Edition), un servidor perimetral y clientes de Lync 2013 o Lync 2010.

</div>

<div>

## <a name="integration-process"></a>Proceso de integración

En la tabla siguiente se ofrece información general sobre el proceso de integración de mensajería unificada de Exchange hospedado. Para obtener más información sobre los pasos de implementación, consulte [proporcionar a los usuarios de Lync Server 2013 correo de voz en la mensajería unificada de Exchange hospedada](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) en la documentación de implementación.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Pasos</th>
<th>Derechos y permisos</th>
<th>Documentación de implementación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configurar el servidor perimetral.</p></td>
<td><ol>
<li><p>Configure el servidor perimetral para la federación.</p></li>
<li><p>Replicar manualmente los datos en el servidor perimetral.</p></li>
<li><p>Configure el proveedor de hospedaje en el servidor perimetral.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configurar el servidor perimetral para la integración con la mensajería unificada de Exchange hospedada</a></p></td>
</tr>
<tr class="even">
<td><p>Configurar la Directiva de correo de voz hospedado.</p></td>
<td><ol>
<li><p>Modifique la Directiva de correo de voz hospedado global o cree una nueva Directiva de correo de voz hospedada con ámbito de sitio o por usuario.</p></li>
<li><p>Para las directivas con ámbito por usuario, asigne la Directiva a los usuarios o grupos.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Administrar directivas de correo de voz hospedado en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Habilitar a los usuarios para el correo de voz hospedado.</p></td>
<td><ul>
<li><p>Configure cuentas de usuario para los usuarios cuyos buzones estén en un servicio de Exchange hospedado.</p></li>
</ul></td>
<td><p>RTCUniversalUserAdmins</p></td>
<td><p><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Habilitar a los usuarios para el correo de voz hospedado en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurar objetos de contacto hospedados.</p></td>
<td><ol>
<li><p>Crear objetos de contacto de operador automático para mensajería unificada de Exchange hospedado.</p></li>
<li><p>Crear objetos de contacto de acceso de suscriptores para mensajería unificada de Exchange hospedado.</p></li>
</ol></td>
<td><p>RTCUniversalUserAdmins</p>
<div>

> [!NOTE]  
> Para crear, modificar o quitar objetos de contacto, el usuario que ejecuta el cmdlet New-CsExUmContact, Set-CsExUmContact o Remove-CsExUmContact debe tener el permiso correcto para la unidad organizativa de Active Directory donde se almacenan los nuevos objetos de contacto. Este permiso se puede conceder si se ejecuta el cmdlet Grant-CsOUPermission. Para obtener más información, consulte la documentación del shell de administración de Lync Server.


</div></td>
<td><p><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Crear objetos de contacto para la mensajería unificada de Exchange hospedada en Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

