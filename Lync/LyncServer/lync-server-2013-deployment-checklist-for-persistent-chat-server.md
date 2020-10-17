---
title: 'Lync Server 2013: lista de comprobación para la implementación del servidor de chat persistente'
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
ms.openlocfilehash: 2399d6ce6fc17a802c8f6bc39730370948ef0253
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522747"
---
# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a>Lista de comprobación para la implementación del servidor de chat persistente en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-16_

La implementación de Lync Server 2013, el servidor de chat persistente requiere que lo implemente en la secuencia correcta y que complete todos los pasos de implementación necesarios.

<div>

## <a name="deployment-sequence"></a>Secuencia de implementación

Puede implementar el servidor de chat persistente después de implementar la topología inicial, incluido al menos un servidor de Lync Server 2013, un grupo de servidores front-end o un servidor de Lync Server 2013, Standard Edition. En este tema se describe cómo implementar el servidor de chat persistente agregándolo a una implementación existente.

</div>

<div>

## <a name="deployment-process"></a>Proceso de implementación

En la siguiente tabla se enumeran los pasos básicos para implementar el servidor de chat persistente y se proporcionan vínculos para obtener más información.

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
<th>Task</th>
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
<li><p>SQL Server en el servidor donde se hospedará la base de datos del servidor de chat persistente</p></li>
</ul>
<p>Si se requiere el cumplimiento del servidor de chat persistente:</p>
<ul>
<li><p>SQL Server en el servidor donde se hospedará la base de datos de cumplimiento del servidor de chat persistente</p></li>
</ul></td>
<td><p>Cualquier usuario que pertenezca al grupo de administradores locales.</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Hardware compatible para Lync Server 2013</a> en la documentación sobre compatibilidad</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Software de servidor y compatibilidad con la infraestructura en Lync Server 2013</a> en la documentación sobre compatibilidad</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Determinación de los requisitos del sistema para Lync Server 2013</a></p>
<p><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Requisitos técnicos para el servidor de chat persistente en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Crear la topología interna adecuada para admitir el servidor de chat persistente (y, opcionalmente, el cumplimiento de chat persistente)</strong></p></td>
<td><p>Ejecute el generador de topologías para agregar un grupo de servidores de chat persistente a la topología:</p>
<ul>
<li><p>Agregar componentes del servidor de chat persistente a la topología</p></li>
<li><p>Crear una base de datos de SQL Server para el almacén del servidor de chat persistente (y una copia de seguridad de SQL Server para la recuperación ante desastres)</p></li>
<li><p>Definir un nuevo almacén de archivos de Lync o usar un almacén de archivos de Lync existente para los archivos del servidor de chat persistente</p></li>
<li><p>Asociar el grupo de servidores de Lync Server 2013 que puede enrutar solicitudes a este grupo de servidores de chat persistente</p></li>
</ul>
<p>Si se requiere el cumplimiento del chat persistente:</p>
<ul>
<li><p>Agregar almacén de cumplimiento de chat persistente</p></li>
<li><p>Haga clic en la casilla definición del grupo de servidores de chat persistente para habilitar el cumplimiento</p></li>
<li><p>Publicar la topología</p></li>
</ul>
<p>Si instala el servidor de chat persistente en Standard Edition, el nombre de dominio completo (FQDN) del grupo de servidores de chat persistente debe coincidir con el servidor Standard Edition y las bases de datos de SQL Server se combinan en la instancia de SQL Server Express en el servidor Standard Edition.</p></td>
<td><p>Para definir una topología, una cuenta que pertenezca al grupo de usuarios locales.</p>
<p>Para publicar la topología, una cuenta que sea miembro del grupo administradores de dominio y del grupo RTCUniversalServerAdmins, y el usuario también debe tener permisos de control total (lectura/escritura/modificación) en el almacén de archivos de Lync para los archivos del servidor de chat persistente (para que el generador de topologías pueda configurar las DACL necesarias).</p></td>
<td><p><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adición de un servidor de chat persistente a la implementación en Lync Server 2013</a> en la documentación de implementación</p></td>
</tr>
<tr class="odd">
<td><p><strong>Implementar el servidor de chat persistente</strong></p></td>
<td><p>Ejecute el programa de instalación de Lync Server en todos los equipos que ejecuten el servidor de chat persistente. La instalación del servidor de chat persistente está integrada en el Asistente para la implementación de Lync Server 2013 que proporciona las instrucciones siguientes:</p>
<ul>
<li><p>Implemente el almacén de administración local</p></li>
<li><p>Instalar los servicios del servidor de chat persistente</p></li>
<li><p>Solicite y asigne certificados</p></li>
<li><p>Ejecute e inicie los servicios</p></li>
</ul></td>
<td><p>Cualquier usuario que pertenezca al grupo de administradores locales.</p></td>
<td><p><a href="lync-server-2013-deploying-persistent-chat-server.md">Deploying persistent chat Server in Lync Server 2013</a> en la documentación de implementación</p></td>
</tr>
<tr class="even">
<td><p><strong>Crear un administrador de chat persistente</strong></p></td>
<td><p>Agregue usuarios al grupo de seguridad CsPersistentChatAdministrator.</p></td>
<td><p>Cualquier usuario que pertenezca al grupo de administradores de dominio.</p></td>
<td><p><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Adición de un administrador de chat persistente en Lync Server 2013</a> en la documentación de implementación</p></td>
</tr>
<tr class="odd">
<td><p><strong>Configuración del servidor de chat persistente</strong></p></td>
<td><p>Configure usuarios:</p>
<ul>
<li><p>El usuario tiene que estar habilitado por la Directiva para tener acceso al servidor de chat persistente. De manera predeterminada, la directiva está desactivada para todos los usuarios, y se puede definir en el ámbito global, de sitio, de grupo o de usuario.</p></li>
<li><p>Defina la configuración</p></li>
</ul></td>
<td><p>El usuario debe pertenecer al grupo CsPersistentChatAdministrator. Para cambiar la directiva, el usuario ser miembro de CsUserAdministrator, como mínimo.</p></td>
<td><p><a href="lync-server-2013-configuring-persistent-chat-server.md">Configuración del servidor de chat persistente en Lync Server 2013</a> en la documentación de implementación</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> Puede implementar uno o más grupos de servidores de chat persistente. Admitimos varios grupos de servidores de chat persistente por motivos legales por los que se requiere que los datos generados en una región determinada permanezcan en dicha región. Por ejemplo, si implementa un grupo de servidores de chat persistente en Chicago y otro en Zurich para cumplir con las normativas de datos en Suiza, los usuarios pueden conectarse a salas en los grupos de servidores de chat persistente, siempre que tengan acceso.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

