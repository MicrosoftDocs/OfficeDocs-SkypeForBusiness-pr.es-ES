---
title: 'Lync Server 2013: Lista de comprobación para la implementación de servidores de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Persistent Chat Server
ms:assetid: b1108f8f-88a2-4660-8086-d25ba76f7239
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412851(v=OCS.15)
ms:contentKeyID: 48185155
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d80122534739d443dedaeeb203ab09da94cb0067
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762708"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a>Lista de comprobación para la implementación de servidores de chat persistente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-16_

Implementación de Lync Server 2013, el servidor de chat persistente requiere que lo implemente en el orden correcto y que complete todos los pasos de implementación necesarios.

<div>

## <a name="deployment-sequence"></a>Secuencia de implementación

Puede implementar un servidor de chat persistente después de implementar su Topología inicial, incluido al menos un servidor de Lync Server 2013, un grupo de servidores front-end o un servidor de Lync Server 2013, Standard Edition. En este tema se describe cómo implementar un servidor de chat persistente agregándolo a una implementación existente.

</div>

<div>

## <a name="deployment-process"></a>Proceso de implementación

En la tabla siguiente se enumeran los pasos básicos para implementar el servidor de chat persistente y se proporcionan vínculos para obtener más información.

### <a name="persistent-chat-server-deployment-process"></a>Proceso de implementación del servidor de chat persistente

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Tarea</th>
<th>Pasos</th>
<th>Roles y pertenencias a grupos necesarios</th>
<th>Temas relacionados</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Instalar los requisitos previos de hardware y software</strong></p></td>
<td><p>En un hardware que cumpla los requisitos del sistema, instale los siguientes elementos:</p>
<ul>
<li><p>En los servidores front-end del servidor de chat persistente:</p></li>
</ul>
<ul>
<li><p>Un sistema operativo que cumpla los requisitos del sistema</p></li>
<li><p>Requisitos previos de software para equipos que ejecutan Lync Server 2013</p></li>
<li><p>SQL Server en el servidor que hospedará la base de datos del servidor de chat persistente</p></li>
</ul>
<p>Si se requiere el cumplimiento del servidor de chat persistente:</p>
<ul>
<li><p>SQL Server en el servidor que hospedará la base de datos de cumplimiento del servidor de chat persistente</p></li>
</ul></td>
<td><p>Cualquier usuario que pertenezca al grupo de administradores locales.</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Hardware compatible con Lync Server 2013</a> en la documentación de soporte técnico</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Compatibilidad con el software de servidor y la infraestructura en Lync Server 2013</a> en la documentación de soporte técnico</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Determinar los requisitos del sistema para Lync Server 2013</a></p>
<p><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Requisitos técnicos para el servidor de chat persistente en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Crear la topología interna adecuada para admitir el servidor de chat persistente (y, opcionalmente, el cumplimiento persistente de la conversación)</strong></p></td>
<td><p>Ejecute el generador de topología para agregar un grupo de servidores de chat persistente a su topología:</p>
<ul>
<li><p>Agregar componentes de servidor de chat persistentes a la topología</p></li>
<li><p>Crear una base de datos de SQL Server para el almacén de servidor de chat persistente (y una copia de seguridad de SQL Server para recuperación ante desastres)</p></li>
<li><p>Definir un nuevo almacén de archivos de Lync o usar un almacén de archivos existente de Lync para los archivos del servidor de chat persistente</p></li>
<li><p>Asociar el grupo de servidores de Lync Server 2013 que pueden enrutar solicitudes a este grupo de servidores de chat persistente</p></li>
</ul>
<p>Si se necesita el cumplimiento del chat persistente:</p>
<ul>
<li><p>Agregar almacén de cumplimiento persistente de chat</p></li>
<li><p>Haga clic en la casilla definición del grupo de servidores de chat persistente para habilitar el cumplimiento.</p></li>
<li><p>Publicar la topología</p></li>
</ul>
<p>Si instala el servidor de chat persistente en Standard Edition, el nombre de dominio completo (FQDN) del grupo de servidores de chat persistente debe coincidir con el servidor Standard Edition y las bases de datos de SQL Server se colocan en la instancia de SQL Server Express en el estándar Servidor de edición</p></td>
<td><p>Para definir una topología, una cuenta que pertenezca al grupo de usuarios locales.</p>
<p>Para publicar la topología, una cuenta que sea miembro del grupo administradores del dominio y del grupo RTCUniversalServerAdmins, y el usuario también debe tener permisos de control total (lectura y escritura/modificación) en el almacén de archivos de Lync para los archivos del servidor de chat persistentes (de modo que el generador de topología pueda configurar las DACL obligatorias).</p></td>
<td><p><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Agregar un servidor de chat persistente a su implementación en Lync Server 2013</a> en la documentación de implementación</p></td>
</tr>
<tr class="odd">
<td><p><strong>Implementar el servidor de chat persistente</strong></p></td>
<td><p>Ejecute el programa de instalación de Lync Server en todos los equipos que ejecuten el servidor de chat persistente. El programa de instalación del servidor de chat persistente está integrado en el Asistente para la implementación de Lync Server 2013 que proporciona las siguientes instrucciones:</p>
<ul>
<li><p>Implemente el almacén de administración local.</p></li>
<li><p>Instalar servicios de servidor de chat persistentes</p></li>
<li><p>Solicite y asigne los certificados.</p></li>
<li><p>Ejecute e inicie los servicios.</p></li>
</ul></td>
<td><p>Cualquier usuario que pertenezca al grupo de administradores locales.</p></td>
<td><p><a href="lync-server-2013-deploying-persistent-chat-server.md">Implementar un servidor de chat persistente en Lync Server 2013</a> en la documentación de implementación</p></td>
</tr>
<tr class="even">
<td><p><strong>Crear un administrador de chat persistente</strong></p></td>
<td><p>Agregue usuarios al grupo de seguridad CsPersistentChatAdministrator.</p></td>
<td><p>Cualquier usuario que pertenezca al grupo de administradores de dominio.</p></td>
<td><p><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Agregar un administrador de chat persistente en Lync Server 2013</a> en la documentación de implementación</p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurar el servidor de chat persistente</strong></p></td>
<td><p>Configure usuarios:</p>
<ul>
<li><p>El usuario debe estar habilitado por la Directiva para tener acceso al servidor de chat persistente. De manera predeterminada, la directiva está desactivada para todos los usuarios, y se puede definir en el ámbito global, de sitio, de grupo o de usuario.</p></li>
<li><p>Defina la configuración</p></li>
</ul></td>
<td><p>El usuario necesita pertenecer al grupo CsPersistentChatAdministrator. Para cambiar la directiva, es preciso que el usuario sea miembro de CsUserAdministrator, como mínimo.</p></td>
<td><p><a href="lync-server-2013-configuring-persistent-chat-server.md">Configuración del servidor de chat persistente en Lync Server 2013</a> en la documentación de implementación</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> Puede implementar uno o varios grupos de servidores de chat persistentes. Admitimos varios grupos de servidores de chat persistente por razones normativas por las cuales es necesario que los datos generados en una región determinada permanezcan en esa región. Por ejemplo, si implementa un grupo de servidores de chat persistente en Chicago y otro en Zurich para cumplir con las normativas de datos de Suiza, los usuarios pueden conectarse a salas en los grupos de servidores de chat persistentes, siempre que tengan acceso.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

