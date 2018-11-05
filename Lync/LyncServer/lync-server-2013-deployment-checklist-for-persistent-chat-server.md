---
title: "Lync Server 2013: Lista comprobación implementación de servidores de chat persistente"
TOCTitle: Lista de comprobación para la implementación de servidores de chat persistente
ms:assetid: b1108f8f-88a2-4660-8086-d25ba76f7239
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412851(v=OCS.15)
ms:contentKeyID: 48276384
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lista de comprobación para la implementación de servidores de chat persistente en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

El Servidor de chat persistente de Lync Server 2013 se debe implementar en la secuencia correcta y se deben completar todos los pasos de implementación necesarios.

## Secuencia de implementación

Puede implementar el Servidor de chat persistente tras implementar la topología inicial, incluido al menos un servidor Lync Server 2013, un Grupo de servidores front-end o un Servidor Standard Edition de Lync Server 2013. En este tema se describe cómo implementar el Servidor de chat persistente agregándolo a otra implementación existente.

## Proceso de implementación

En la tabla siguiente se muestran los pasos básicos para implementar el Servidor de chat persistente y se proporcionan vínculos para más información.

### Proceso de implementación del Servidor de chat persistente

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
<li><p>En los Servidores front-end del Servidor de chat persistente:</p></li>
</ul>
<ul>
<li><p>Un sistema operativo que cumpla los requisitos del sistema</p></li>
<li><p>Requisitos previos de software para equipos que ejecutan Lync Server 2013</p></li>
<li><p>SQL Server en el servidor donde se va a hospedar la base de datos del Servidor de chat persistente</p></li>
</ul>
<p>Si el cumplimiento del Servidor de chat persistente es necesario:</p>
<ul>
<li><p>SQL Server en el servidor donde se va a hospedar la base de datos de cumplimiento del Servidor de chat persistente</p></li>
</ul></td>
<td><p>Cualquier usuario que pertenezca al grupo de administradores locales.</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Hardware admitido en Lync Server 2013</a> en la documentación sobre compatibilidad</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Software de servidor y compatibilidad con la infraestructura en Lync Server 2013</a> en la documentación sobre compatibilidad</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Determinar los requisitos del sistema para Lync Server 2013</a></p>
<p><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Requisitos técnicos para el servidor de chat persistente en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Crear la topología interna adecuada para admitir el Servidor de chat persistente (y, opcionalmente, el cumplimiento del Chat persistente)</strong></p></td>
<td><p>Ejecute el Generador de topologías para agregar un Grupo de servidores de chat persistente a la topología:</p>
<ul>
<li><p>Agregue los componentes del Servidor de chat persistente a la topología</p></li>
<li><p>Cree una base de datos de SQL Server para el almacén del Servidor de chat persistente (y un servidor SQL Server de reserva para la recuperación ante desastres)</p></li>
<li><p>Defina un nuevo almacén de archivos de Lync o use un almacén de archivos existente de Lync para archivos del Servidor de chat persistente</p></li>
<li><p>Asocie el grupo de servidores Lync Server 2013 que puede enrutar solicitudes a este Grupo de servidores de chat persistente</p></li>
</ul>
<p>Si el cumplimiento del Chat persistente es necesario:</p>
<ul>
<li><p>Agregue el almacén de cumplimiento del Chat persistente</p></li>
<li><p>Haga clic en la casilla de definición del Grupo de servidores de chat persistente para habilitar el cumplimiento</p></li>
<li><p>Publique la topología</p></li>
</ul>
<p>Si instala el Servidor de chat persistente en un servidor Standard Edition, el nombre de dominio completo (FQDN) del Grupo de servidores de chat persistente debe coincidir con el Servidor Standard Edition, y las bases de datos de SQL Server se instalan en la instancia de SQL Server Express en el Servidor Standard Edition.</p></td>
<td><p>Para definir una topología, una cuenta que pertenezca al grupo de usuarios locales.</p>
<p>Para publicar la topología, una cuenta que pertenezca al grupo de administradores de domino y al grupo RTCUniversalServerAdmins, y el usuario debe tener permisos de control total (lectura/escritura/modificación) en el almacén de archivos de Lync para los archivos del Servidor de chat persistente (de modo que el Generador de topologías pueda configurar las DACL necesarias).</p></td>
<td><p><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Agregar un servidor de chat persistente a la implementación en Lync Server 2013</a> en la documentación de implementación</p></td>
</tr>
<tr class="odd">
<td><p><strong>Implementar el Servidor de chat persistente</strong></p></td>
<td><p>Ejecute el programa de instalación de Lync Server en todos los equipos que usen el Servidor de chat persistente. El programa de instalación del Servidor de chat persistente está integrado en el Asistente para la implementación de Lync Server 2013, que proporciona las instrucciones siguientes:</p>
<ul>
<li><p>Implemente el almacén de administración local</p></li>
<li><p>Instale los servicios del Servidor de chat persistente</p></li>
<li><p>Solicite y asigne certificados</p></li>
<li><p>Ejecute e inicie los servicios</p></li>
</ul></td>
<td><p>Cualquier usuario que pertenezca al grupo de administradores locales.</p></td>
<td><p><a href="lync-server-2013-deploying-persistent-chat-server.md">Implementar el servidor de chat persistente en Lync Server 2013</a> en la documentación de implementación</p></td>
</tr>
<tr class="even">
<td><p><strong>Cree un administrador de Chat persistente</strong></p></td>
<td><p>Agregue usuarios al grupo de seguridad CsPersistentChatAdministrator.</p></td>
<td><p>Cualquier usuario que pertenezca al grupo de administradores de dominio.</p></td>
<td><p><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Agregar un administrador de chat persistente en Lync Server 2013</a> en la documentación de implementación</p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurar el Servidor de chat persistente</strong></p></td>
<td><p>Configure usuarios:</p>
<ul>
<li><p>El usuario debe estar habilitado por la directiva para tener acceso al Servidor de chat persistente. De manera predeterminada, la directiva está desactivada para todos los usuarios, y se puede definir en el ámbito global, de sitio, de grupo o de usuario.</p></li>
<li><p>Defina la configuración</p></li>
</ul></td>
<td><p>El usuario debe pertenecer al grupo CsPersistentChatAdministrator. Para cambiar la directiva, el usuario ser miembro de CsUserAdministrator, como mínimo.</p></td>
<td><p><a href="lync-server-2013-configuring-persistent-chat-server.md">Configurar servidor de chat persistente en Lync Server 2013</a> en la documentación de implementación</p></td>
</tr>
</tbody>
</table>


> [!IMPORTANT]  
> Puede implementar uno o varios Grupos de servidores de chat persistente. Admitimos el uso de varios Grupos de servidores de chat persistente con fines de cumplimiento de normativas, cuando los datos generados en una región determinada deben permanecer en esa región. Por ejemplo, si implementa un Grupo de servidores de chat persistente en Chicago y otro en Zurich para cumplir con las normativas de datos de Suiza, los usuarios podrán conectarse con salones de ambos Grupos de servidores de chat persistente, siempre que tengan acceso.


