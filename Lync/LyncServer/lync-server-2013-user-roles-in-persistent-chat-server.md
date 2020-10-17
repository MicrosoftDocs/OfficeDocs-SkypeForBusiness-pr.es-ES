---
title: 'Lync Server 2013: roles de usuario en el servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User roles in Persistent Chat Server
ms:assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ676774(v=OCS.15)
ms:contentKeyID: 49361095
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c91fcb656d936d0fb469cdec4b01824d3fa97d1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518857"
---
# <a name="user-roles-in-persistent-chat-server-in-lync-server-2013"></a>Roles de usuario en el servidor de chat persistente en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-03-19_

El servidor de chat persistente proporciona el concepto de miembros permitidos/denegados, que se aplica a las categorías de chat persistentes y a los controles que pueden tener acceso a salones de una categoría determinada.

<div>


> [!IMPORTANT]  
> Los miembros permitidos o denegados de una categoría no son los mismos que los de un rol de <STRONG>miembro</STRONG> , que se aplican a un salón de chat persistente.<BR>Las búsquedas muestran todos los salones de chat abiertos y cerrados para los que el usuario que realiza la búsqueda se encuentra en la lista de miembros permitidos/denegados. Los salones secretos no se muestran a menos que el usuario que realiza la búsqueda sea miembro del salón secreto. De este modo, el usuario solo puede buscar salones de los que sea miembro o aquellos a los que pueda solicitar ser miembro.



</div>

El principio básico del concepto de miembros permitidos/denegados son las zonas de protección. Por ejemplo, en las instituciones financieras y bancarias, es muy común disponer de límites de protección que impidan a los comerciantes y analistas compartir comunicaciones durante la implementación de directivas y convenciones. Para ello, el administrador puede crear categorías de manera que una categoría admita la creación y el uso de salones por parte de los comerciantes, mientras que la otra admita la creación y el uso de salones por parte de los analistas. Esta limitación está diseñada para impedir que se agreguen usuarios como miembros del salón si la categoría principal lo prohíbe.

A continuación se muestran los cuatro roles de usuario servidor de chat persistente:

  - **Creador:** Usuarios con permisos para crear salones de chat. Estos usuarios figuran en la lista de autores de determinadas categorías: pueden crear salones de chat en sus categorías, asignar miembros en función de la categoría y asignar administradores del salón de chat. El usuario que cree un salón de chat se agregará automáticamente como administrador del salón.
    
    <div>
    

    > [!NOTE]  
    > Los autores solo están autorizados a crear salones de chat. La promoción automática al rol de Administrador es la que permite al Autor delimitar las pertenencias a grupos, etc., en los servicios de chat creados.

    
    </div>
    
    Este rol ofrece la opción de controlar quién crea salones de chat en su organización, lo cual resulta de especial utilidad si desea administrar de forma centralizada creación de salones de chat para garantizar el cumplimiento de directivas y convenciones, con la consiguiente delegación de la administración de la sala de chat a los usuarios de la organización.

  - **Administrador:** Usuarios que administran las propiedades de un salón de chat. Los administradores de salones de chat pueden modificar la lista de miembros (agregar o quitar miembros), así como la lista de administradores de la sala de chat (agregar y quitar administradores). Los administradores de los salones de chat pueden agregarse a sí mismos a la lista de miembros o de moderadores (en salones de auditorio) para participar en el salón de chat. También pueden deshabilitar salones de chat (los administradores pueden consultar los salones de chat deshabilitados para eliminarlos de forma permanente). Los administradores pueden cambiar todas las propiedades de los salones de chat, excepto la categoría del salón de chat. Solo el administrador de chat persistente puede cambiar la categoría una vez que se haya creado el salón de chat.
    
    <div>
    

    > [!IMPORTANT]  
    > En caso de que el administrador también sea autor en otra categoría, estará autorizado a cambiar la categoría a otra en la que esté autorizado a crear salones de chat.

    
    </div>

  - **Miembro:** Usuarios que son miembros de un salón de chat. Estos usuarios pueden ver los salones de chat en el directorio (incluso si el salón de chat es secreto), así como suscribirse al salón de chat (incluidas las opciones de metadatos, como los mensajes no leídos, los filtros de ego y los filtros de palabras clave), y participar en el salón de chat (puede publicar, a menos que el salón sea un salón de auditorio en el Los usuarios que no son miembros del salón de chat pueden buscar el salón de chat si están en la lista de miembros permitidos de la categoría, pero necesitan solicitar acceso para unirse a estos salones de chat para tener acceso al contenido. (No hay acceso ni aprobaciones de solicitud integradas en el sistema; estas se realizan de forma externa por correo electrónico, teléfono u otros formularios de contacto).

  - **Moderador:** Usuarios que pueden publicar en un salón de Auditorio.

<div>


> [!NOTE]  
> El servidor de chat persistente permite a los usuarios crear y administrar salones de chat para un sitio específico. Sin embargo, los usuarios no pueden crear ni administrar salones de chat en otros sitios dentro de la misma topología. Asegúrese de especificar los creadores y creadores de salones de chat para todos los sitios de la organización.



</div>

Los siguientes roles son roles de administrador para el servidor de chat persistente:

  - **Administrador de chat persistente (CsPersistentChatAdministrator):** Se trata de un nuevo rol de control de acceso de Role-Based (RBAC) para administrar y administrar el servidor de chat persistente. Los usuarios o grupos de seguridad designados como CsPersistentChatAdministrator pueden administrar el servidor de chat persistente con los cmdlets de Windows PowerShell de forma remota (es decir, desde un equipo que no sea el servidor de chat persistente). El servidor de chat persistente comprueba que el administrador de chat persistente sea miembro del grupo local de administradores de RTC local en el servidor front-end del servidor de chat persistente.
    
    El rol CsPersistentChatAdministrator puede administrar los salones de chat (modificar todas las propiedades como, por ejemplo, la pertenencia a grupos, los administradores o las categorías, marcar los salones como deshabilitados, etc.) y crear y administrar categorías de salones de chat que definan quién puede crear y tener acceso a los salones. Los administradores también pueden marcar salones de chat como deshabilitados y eliminar los salones de chat que ya no estén activos. Los administradores no están sujetos a las restricciones que tienen los Autores o los Miembros permitidos. Los administradores pueden crear cualquier tipo de salón de chat y agregarse a sí mismos como miembros de cualquier salón de chat. Los administradores también pueden modificar y administrar la configuración de los chats persistentes (propiedades de grupo, la configuración global y la configuración de cumplimiento) y también pueden planear e implementar la migración desde una implementación de servidor de chat de grupo anterior al servidor de chat persistente de Lync Server 2013.

  - **Administrador de Lync:** Administrador empresarial general de Lync Server 2013 responsable de la implementación.

  - **Operations Manager:** Usuario responsable de la administración de las operaciones diarias.

  - **Desarrolladores y partners de terceros:** Los desarrolladores de terceros amplían el sistema y, en particular, proporcionan una solución de pared ética para conversaciones en grupo, herramientas y soporte de cumplimiento, clientes web/móviles y un marco para el desarrollo de robots.

</div>

<span> </span>

</div>

</div>

</div>

