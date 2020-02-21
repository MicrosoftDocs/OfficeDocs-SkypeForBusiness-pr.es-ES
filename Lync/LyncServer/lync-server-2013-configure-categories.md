---
title: 'Lync Server 2013: configurar categorías'
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
ms.openlocfilehash: fb70397514589ac6f3cc74d84a6ae7509c9baa5b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205117"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-categories-in-lync-server-2013"></a>Configurar categorías en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-06_

En el panel de control de Lync Server 2013, puede usar la sección **categoría** de la página **chat persistente** para configurar las categorías. Una categoría de salón de chat persistente es una estructura lógica para organizar salones de chat. Una categoría define un conjunto predeterminado de listas de control de acceso (ACL) para controlar los usuarios y grupos de usuarios que pueden crear o unirse a salones de chat. Puede usar zonas de protección de datos confidenciales de imposición de categorías entre distintas subdivisiones en sus organizaciones.

Las categorías de salones de chat pueden contener salones de chat, pero no otras categorías. Cada categoría describe su contenido con metadatos, como Nombre y Descripción. Además, la categoría tiene propiedades que se pueden definir para controlar el comportamiento de los salones de chat que pertenecen a esta categoría, por ejemplo si el salón de chat permite invitaciones, cargas de archivos o contiene el historial de chat.

<div>

## <a name="to-configure-categories-for-chat-rooms"></a>Para configurar categorías para salones de chat

1.  Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier PC en la implementación interna.

2.  En el menú **Inicio** , seleccione el panel de control de Lync Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > También puede usar cmdlets de Windows PowerShell. Para obtener más información, consulte <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring persistent chat Server by Using Windows PowerShell cmdlets</A> en la documentación sobre implementación.

    
    </div>

3.  En la barra de navegación izquierda, haga clic en **Chat persistente** y, a continuación, en **Categoría**.
    
    Para varias implementaciones del grupo de servidores de chat persistente, seleccione el grupo adecuado de la lista desplegable.

4.  En la página **Categoría**, haga clic en **Nueva** o **Editar**.

5.  En **seleccionar un servicio**, seleccione el servicio correspondiente al grupo de servidores de chat persistente en el que se debe crear la categoría. El servicio es el grupo de servidores de chat persistente que usa el chat persistente (cliente) para identificar a qué grupo pertenece la categoría. Una categoría puede pertenecer solo a un grupo de servidores de chat persistente y no se puede mover a otro o compartido con otro grupo.

6.  En **Nueva categoría**, haga lo siguiente:
    
    1.  En **Nombre **, especifique un nombre para el nuevo salón.
    
    2.  En  **Descripción **, proporcione una descripción detallada de la categoría del salón (por ejemplo, una categoría de salón para Contoso).
    
    3.  Para controlar si se pueden habilitar invitaciones para salones de chat, active o desactive la casilla **Habilitar invitaciones**. Si la activa, los salones de esta categoría pueden tener invitaciones activadas o desactivadas; si se desactiva, los salones de esta categoría no pueden tener invitaciones. Si un salón tiene invitaciones, cuando se agrega un nuevo miembro a un salón, recibe una notificación del nuevo salón en su cliente de chat persistente.
    
    4.  Para controlar las cargas de archivos en salones de chat que pertenezcan a esta categoría, active o desactive la casilla **Habilitar carga de archivo**. Si se activa, los salones de esta categoría pueden habilitar o deshabilitar las cargas de archivos; si se desactiva, los salones de esta categoría no pueden tener cargas de archivos.
        
        <div>
        

        > [!IMPORTANT]  
        > Esta configuración se aplica en el servidor porque las aplicaciones personalizadas o los clientes de chat de grupo anteriores que usan el servidor de&nbsp;chat en grupo de Office Communications Server 2007 R2 o Lync Server 2010, el chat en grupo puede publicar archivos en un salón. El cliente de Lync 2013 no tiene capacidad de carga y descarga de archivos, por lo que si tiene una implementación pura de Lync 2013 o un cliente de Lync 2013, no se pueden publicar archivos en un salón de chat del servidor de chat persistente.

        
        </div>
    
    5.  Para controlar el historial de chat, Active o desactive la casilla **Habilitar el historial de chat** . Si se activa, los salones de chat se vuelven persistentes; en caso contrario, los mensajes de chat no permanecen. Si se habilita el cumplimiento, los chats de los salones se guardarán en conformidad, pero los usuarios no podrán obtener acceso a los mensajes más antiguos. Esta opción se puede usar para salones designados para colaboraciones ad hoc en tiempo real y que no necesitan que se conserve el historial de chat.

7.  En **Editar categoría**, haga lo siguiente:
    
      - En **pertenencia**, en la sección **miembros permitidos** , agregue o quite usuarios y otras entidades de seguridad de servicios de dominio de Active Directory (usuarios, grupos de distribución, unidades organizativas, etc.) que pueden agregarse como miembros de los salones de chat que pertenecen a la categoría. Los elementos principales permitidos por una categoría pueden buscar salones en la categoría (a menos que el salón esté oculto, en cuyo caso solo los miembros del salón pueden buscarlo en el directorio).
    
      - En **pertenencia**, en la sección **miembros denegados** , agregue o quite usuarios y otras entidades de Active Directory asociadas con miembros denegados del salón.
    
      - En **pertenencia**, en la sección **creadores** , agregue o quite usuarios y otras entidades de Active Directory asociadas con los creadores de la categoría. Un creador es un usuario que tiene permisos para crear salones de chat y asignar administradores y miembros de salones de chat.

8.  Haga clic en **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

