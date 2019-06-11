---
title: 'Lync Server 2013: roles de usuario en el servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User roles in Persistent Chat Server
ms:assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ676774(v=OCS.15)
ms:contentKeyID: 49361095
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36f84f71ca5253d28d9182acc9279010127ee6f3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-roles-in-persistent-chat-server-in-lync-server-2013"></a>Roles de usuario en el servidor de chat persistente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-03-19_

El servidor de chat persistente proporciona el concepto de miembros permitidos o denegados, que se aplica a categorías de chat persistentes y controles que pueden acceder a salas en una determinada categoría.

<div>


> [!IMPORTANT]  
> Los miembros permitidos o denegados de una categoría no son iguales a los de un rol de <STRONG>miembro</STRONG> , que se aplica a un salón de chat persistente.<BR>Las búsquedas muestran todos los salones de chat abiertos y cerrados en los que el usuario que realiza la búsqueda se encuentra en la lista de miembros permitido o denegado. Los salones secretos no se muestran a menos que el usuario que efectúa la búsqueda sea miembro del salón secreto. De este modo, el usuario solo puede buscar salones de los que sea miembro o aquellos a los que pueda solicitar ser miembro.



</div>

El fundamento principal para el concepto de miembros permitidos o rechazados son las paredes éticas. Por ejemplo, en las instituciones financieras y bancarias, es muy común disponer de límites de protección que impidan a los comerciantes y analistas compartir comunicaciones al implementar directivas y convenciones. Para abordar este requisito, el administrador puede crear categorías de manera que una categoría admita la creación y el uso de salones por parte de los comerciantes, mientras que la otra admita la creación y el uso de salones por parte de los analistas. Con esta restricción está diseñada en el sistema, prohíbe agregar un usuario como miembro del salón si la categoría principal lo impide.

A continuación se muestran los cuatro roles de usuario servidor de chat persistente:

  - **Creador:** Usuarios que tienen permisos para crear salones de chat. Estos usuarios figuran en la lista de autores de determinadas categorías: pueden crear salones de chat en sus categorías, asignar miembros en función de la categoría y asignar administradores del salón de chat. El usuario que cree un salón de chat se agregará automáticamente como administrador del salón.
    
    <div>
    

    > [!NOTE]  
    > Los autores solo están autorizados a crear salones de chat. La promoción automática al rol de Administrador es la que permite al Autor delimitar las pertenencias a grupos, etc., en los servicios de chat creados.

    
    </div>
    
    Este rol ofrece la opción de controlar quién crea salones de chat en su organización, lo cual resulta de especial utilidad si desea administrar de forma centralizada creación de salones de chat para garantizar el cumplimiento de directivas y convenciones, con la consiguiente delegación de la administración de la sala de chat a los usuarios de la organización.

  - **Administrador:** Usuarios que administran las propiedades de un salón de chat. Los administradores de salones de chat pueden modificar la lista de miembros (agregar o quitar miembros), así como la lista de administradores de la sala de chat (agregar y quitar administradores). Los administradores de los salones de chat pueden agregarse a sí mismos a la lista de miembros o de moderadores (en salones de auditorio) para participar en el salón de chat. También pueden deshabilitar salones de chat (los administradores pueden consultar los salones de chat deshabilitados para eliminarlos de forma permanente). Los administradores pueden cambiar todas las propiedades de los salones de chat, excepto la categoría del salón de chat. Solo el administrador de chat persistente puede cambiar la categoría después de que se haya creado el salón de chat.
    
    <div>
    

    > [!IMPORTANT]  
    > En caso de que el administrador también sea autor en otra categoría, estará autorizado a cambiar la categoría a otra en la que esté autorizado a crear salones de chat.

    
    </div>

  - **Miembro:** Usuarios que son miembros de un salón de chat. Estos usuarios pueden ver los salones de chat en el directorio (incluso si el salón de chat es secreto), así como suscribirte al salón de chat (incluidas las opciones de metadatos como, por ejemplo, los mensajes no leídos, los filtros de ego y los filtros de palabras clave), y participar en el salón de chat (puede publicar, a menos que el salón es un salón de auditorio en el que solo los moderadores pueden publicar, obtener contenido y buscar). Los usuarios que no son miembros del salón de chat pueden buscar el salón de chat si están en la lista de miembros permitidos de la categoría, pero necesitan solicitar acceso para que se unan a estos salones de chat y tengan acceso al contenido. (No hay acceso ni aprobaciones de solicitudes integradas en el sistema; estas se realizan externamente por correo electrónico, teléfono u otras formas de contacto).

  - **Moderador:** Usuarios que pueden publicar en una sala de Auditorio.

<div>


> [!NOTE]  
> El servidor de chat persistente permite a los usuarios crear y administrar el salón de chat para un sitio específico. Sin embargo, los usuarios no pueden crear ni administrar salones de chat en otros sitios dentro de la misma topología. Asegúrese de especificar los creadores y administradores del salón de chat de todos los sitios de su organización.



</div>

Los roles siguientes son roles de administrador para el servidor de chat persistente:

  - **Administrador de chat persistente (CsPersistentChatAdministrator):** Este es un nuevo rol de control de acceso basado en roles (RBAC) para administrar y administrar el servidor de chat persistente. Los usuarios o grupos de seguridad designados como CsPersistentChatAdministrator pueden administrar el servidor de chat persistente mediante cmdlets de Windows PowerShell de forma remota (es decir, desde un equipo que no sea el servidor de chat persistente). El servidor de chat persistente comprueba que el administrador de chat persistente sea miembro del grupo local RTC local Administrators en el servidor front-end del servidor de chat persistente.
    
    El rol CsPersistentChatAdministrator puede administrar salones de chat (modificar todas las propiedades, como la pertenencia, los jefes, las categorías, marcar salas como deshabilitadas), así como crear y administrar categorías de salones de chat que definan quién puede crear y acceder a salones de chat. Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active. Administrators are not subject to the Creators or Allowed Members restrictions. Administrators can create any kind of chat room and add themselves as a member to any chat room. Los administradores también pueden modificar y administrar la configuración de los chats persistentes (propiedades de grupo, configuración global y configuración de cumplimiento) y también pueden planear e implementar la migración desde una implementación de servidor de chat de grupo anterior a Lync Server 2013 chat persistente Servidores.

  - **Administrador de Lync:** Administrador corporativo general de Lync Server 2013 responsable de la implementación.

  - **Operations Manager:** Usuario responsable de administrar las operaciones diarias.

  - **Desarrolladores y socios de terceros:** Los programadores de terceros amplían el sistema, en especial proporcionando una solución de pared ética para las conversaciones grupales, soporte técnico y herramientas de cumplimiento, clientes web/móviles y un marco para el desarrollo de bot.

</div>

<span> </span>

</div>

</div>

</div>

