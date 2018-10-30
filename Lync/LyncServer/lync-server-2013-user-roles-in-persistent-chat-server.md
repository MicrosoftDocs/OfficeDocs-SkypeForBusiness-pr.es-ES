---
title: Roles de usuario en el servidor de chat persistente
TOCTitle: Roles de usuario en el servidor de chat persistente
ms:assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ676774(v=OCS.15)
ms:contentKeyID: 49889039
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Roles de usuario en el servidor de chat persistente

 

_**Última modificación del tema:** 2015-03-19_

El Servidor de chat persistente ofrece el concepto de miembros permitidos/denegados, que se aplica a las categorías de Chat persistente y controla quién puede tener acceso a los salones de chat de una categoría determinada.

> [!IMPORTANT]  
> Los miembros permitidos/denegados de una categoría no son lo mismo que el rol <strong>Miembro</strong>, que se aplica a un salón de Chat persistente.<br />
> Las búsquedas muestran todos los salones de chat abiertos y cerrados para los que el usuario que realiza la búsqueda se encuentra en la lista de miembros permitidos/denegados. Los salones secretos no se muestran a menos que el usuario que realiza la búsqueda sea miembro del salón secreto. De este modo, el usuario solo puede buscar salones de los que sea miembro o aquellos a los que pueda solicitar ser miembro.


El principio básico del concepto de miembros permitidos/denegados son las zonas de protección. Por ejemplo, en las instituciones financieras y bancarias, es muy común disponer de límites de protección que impidan a los comerciantes y analistas compartir comunicaciones durante la implementación de directivas y convenciones. Para ello, el administrador puede crear categorías de manera que una categoría admita la creación y el uso de salones por parte de los comerciantes, mientras que la otra admita la creación y el uso de salones por parte de los analistas. Esta limitación está diseñada para impedir que se agreguen usuarios como miembros del salón si la categoría principal lo prohíbe.

A continuación se muestran los cuatro roles de usuario del Servidor de chat persistente:

  - **Autor:** usuarios que tienen permiso para crear salones de chat. Estos usuarios figuran en la lista de autores de determinadas categorías: pueden crear salones de chat en sus categorías, asignar miembros en función de la categoría y asignar administradores del salón de chat. El usuario que cree un salón de chat se agregará automáticamente como administrador del salón.
    

    > [!NOTE]
    > Los autores solo están autorizados a crear salones de chat. La promoción automática al rol de Administrador es la que permite al Autor delimitar las pertenencias a grupos, etc., en los servicios de chat creados.

    
    Este rol ofrece la opción de controlar quién crea salones de chat en su organización, lo cual resulta de especial utilidad si desea administrar de forma centralizada creación de salones de chat para garantizar el cumplimiento de directivas y convenciones, con la consiguiente delegación de la administración de la sala de chat a los usuarios de la organización.

  - **Administrador:** usuarios que administran las propiedades de un salón de chat. Los administradores de salones de chat pueden modificar la lista de miembros (agregar o quitar miembros), así como la lista de administradores de la sala de chat (agregar y quitar administradores). Los administradores de los salones de chat pueden agregarse a sí mismos a la lista de miembros o de moderadores (en salones de auditorio) para participar en el salón de chat. También pueden deshabilitar salones de chat (los administradores pueden consultar los salones de chat deshabilitados para eliminarlos de forma permanente). Los administradores pueden cambiar todas las propiedades de los salones de chat, excepto la categoría del salón de chat. Solo el Administrador del Chat persistente puede modificar la categoría una vez creado el salón de chat.
    
    > [!IMPORTANT]  
    > En caso de que el administrador también sea autor en otra categoría, estará autorizado a cambiar la categoría a otra en la que esté autorizado a crear salones de chat.
    


  - **Miembro:** usuarios miembros de un salón de chat. Estos usuarios pueden ver los salones de chat en el directorio (incluso si el salón de chat es secreto) y suscribirse al salón de chat (incluidas las opciones de metadatos como, por ejemplo, los mensajes no leídos, los filtros ego y de palabras clave) para participar en el salón de chat (pueden publicar contenido a menos que el salón sea un salón de auditorio en el que solo los moderadores pueden publicar, obtener y buscar contenido). Los usuarios que no sean miembros del salón de chat puede buscar el salón de chat solo si están en la lista de miembros permitidos de la categoría, aunque deberán solicitar el acceso para unirse a esos salones de chat y tener acceso al contenido. (La solicitud o la aprobación del acceso no están integrados en el sistema. Estas acciones se llevan a cabo de forma externa por teléfono, correo electrónico o a través de otros medios de contacto.)

  - **Moderador:** usuarios que pueden publicar contenido en un salón de auditorio.

Los roles que se describen a continuación son roles de administrador de Servidor de chat persistente:

  - **Administrador de Chat persistente (CsPersistentChatAdministrator):** se trata de un nuevo rol de control de acceso basado en roles (RBAC) que permite controlar y administrar Servidor de chat persistente. Los usuarios o grupos de seguridad identificados como CsPersistentChatAdministrator pueden administrar Servidor de chat persistente de forma remota mediante los cmdlets de Windows PowerShell (es decir, desde un equipo distinto del equipo del Servidor de chat persistente). El Servidor de chat persistente comprueba que el Administrador de Chat persistente es miembro del grupo local de administradores de RTC en el Servidor front-end del Servidor de chat persistente.
    
    El rol CsPersistentChatAdministrator puede administrar los salones de chat (modificar todas las propiedades como, por ejemplo, la pertenencia a grupos, los administradores o las categorías, marcar los salones como deshabilitados, etc.) y crear y administrar categorías de salones de chat que definan quién puede crear y tener acceso a los salones. Los administradores también pueden marcar salones de chat como deshabilitados y eliminar los salones de chat que ya no estén activos. Los administradores no están sujetos a las restricciones que tienen los Autores o los Miembros permitidos. Los administradores pueden crear cualquier tipo de salón de chat y agregarse a sí mismos como miembros de cualquier salón de chat. Los administradores también pueden modificar y administrar la configuración del Chat persistente (propiedades del grupo, configuración global y configuración de cumplimiento) y planificar e implementar la migración de implementaciones anteriores de Servidor de chat en grupo al Servidor de chat persistente de Lync Server 2013.

  - **Administrador de Lync:** administrador empresarial general de Lync Server 2013 responsable de la implementación.

  - **Administrador de operaciones:** usuario responsable de la administración de las operaciones diarias.

  - **Socios y desarrolladores externos:** desarrolladores externos que amplían el sistema, sobre todo al proporcionar soluciones de zonas de protección para conversaciones de grupos, herramientas de cumplimiento, clientes móviles/web y marcos de trabajo para el desarrollo de robots.

