---
title: 'Lync Server 2013: Configurar categorías'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure categories
ms:assetid: 4547f514-f0c0-404d-890f-092ddeeac852
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204859(v=OCS.15)
ms:contentKeyID: 48184033
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf7b7b3ceb24e3b5bffb307cdde048e7a0cabb8c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-categories-in-lync-server-2013"></a>Configurar categorías en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-06_

En el panel de control de Lync Server 2013, puede usar la sección **categoría** de la página **chat persistente** para configurar categorías. Una categoría de salón de chat persistente es una estructura lógica para organizar salones de chat. Una categoría define un conjunto predeterminado de listas de control de acceso (ACL) para controlar los usuarios y grupos de usuarios que se pueden crear o unir a salones de chat. Puede usar zonas de protección de datos confidenciales de imposición de categorías entre distintas subdivisiones en sus organizaciones.

Las categorías de salones de chat pueden contener salones de chat, pero no otras categorías. Cada categoría describe su contenido con metadatos como Name y Description. Además, la categoría tiene propiedades que se pueden definir para controlar el comportamiento de los salones de chat que pertenecen a esta categoría; así, si el salón de chat permite Invitations, File Uploads o contiene el Chat History.

<div>

## <a name="to-configure-categories-for-chat-rooms"></a>Para configurar categorías para salones de chat

1.  Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator o CsAdministrator.

2.  En el menú **Inicio** , seleccione el panel de control de Lync Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > También puede usar los cmdlets de Windows PowerShell. Para obtener más información, vea <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">configuración del servidor de chat persistente mediante cmdlets de Windows PowerShell</A> en la documentación de implementación.

    
    </div>

3.  En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Categoría**.
    
    Para varias implementaciones del grupo de servidores de chat persistentes, seleccione el grupo adecuado de la lista desplegable.

4.  En la página **Categoría**, haga clic en **Nuevo** o en **Editar**.

5.  En **seleccionar un servicio**, seleccione el servicio correspondiente al grupo de servidores de chat persistente en el que se debe crear la categoría. El servicio es el grupo de servidores de chat persistente que usa el chat persistente (cliente) para identificar a qué grupo pertenece la categoría. Una categoría puede pertenecer a un único grupo de servidores de chat persistentes, no se puede mover a otro grupo o compartir con otro grupo.

6.  En **Nueva categoría**, haga lo siguiente:
    
    1.  En **Nombre**, especifique un nombre para la nueva categoría de salón.
    
    2.  En **Descripción**, proporcione una descripción detallada sobre la categoría del salón (por ejemplo, una categoría de salón para Contoso).
    
    3.  Para controlar si las invitaciones se pueden habilitar para salones de chat que pertenecen a esta categoría, active o desactive la casilla **Habilitar invitaciones**. Si está activada, los salones de esta categoría puedan tener invitaciones activas o inactivas y, si está desactivada, el salón de esta categoría no puede tener invitaciones. Si un salón tiene invitaciones, cuando se agrega un nuevo miembro a un salón, recibe una notificación de la nueva sala en su cliente de chat persistente.
    
    4.  Para controlar las cargas de archivos en salones de chat que pertenecen a esta categoría, active o desactive la casilla **Habilitar carga de archivo**. Si está activada, los salones de esta categoría pueden habilitar o deshabilitar las cargas de archivos y, si no está activada, los salones de esta categoría no pueden tener cargas de archivos.
        
        <div>
        

        > [!IMPORTANT]  
        > Esta configuración se aplica en el servidor porque las aplicaciones personalizadas o los clientes de chat de grupo anteriores que usan el servidor de&nbsp;chat grupal de Office Communications Server 2007 R2 o Lync Server 2010, la conversación grupal puede publicar archivos en un salón. El cliente de Lync 2013 no tiene la funcionalidad de carga y descarga de archivos, por lo que si tiene una implementación de Lync 2013 pura o un cliente de Lync 2013, no es posible publicar archivos en un salón de chat del servidor de chat persistente.

        
        </div>
    
    5.  Para controlar el historial de conversaciones, Active o desactive la casilla de verificación **Habilitar el historial de chat** . Si está activada, los salones de chat serán persistentes; en caso contrario, los mensajes de chats no persisten. Si el cumplimiento está habilitado, los chats del salón se guardarán en consecuencia, pero los usuarios no podrán tener acceso a los mensajes antiguos. Esta opción puede usarse en salones designados para la colaboración en tiempo real y ad-hoc que no necesiten que el historial de chat persista.

7.  En **Editar categoría**, haga lo siguiente:
    
      - En **pertenencia**, en la sección **miembros permitidos** , agregue o quite usuarios y otros principios de los servicios de dominio de Active Directory (usuarios, grupos de distribución, unidades organizativas, etc.) que pueden agregarse como miembros de los salones de chat que pertenecen a la categoría. Las entidades de seguridad permitidas por una categoría pueden buscar los salones de la categoría (a menos que el salón esté oculto, en cuyo caso solo los miembros del salón podrán encontrarlo en el directorio).
    
      - En **pertenencia**, en la sección **miembros denegados** , agregue o quite usuarios y otros principales de Active Directory asociados a miembros que se deniegan del salón.
    
      - En **pertenencia**, en la sección **creadores** , agregue o quite usuarios y otras entidades de Active Directory asociadas con los creadores de la categoría. Un creador es un usuario que tiene permisos para crear salones de chat y asignar administradores y miembros de los salones de chat.

8.  Haga clic en **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

