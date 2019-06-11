---
title: 'Lync Server 2013: Configurar la directiva global para chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the global policy for Persistent Chat
ms:assetid: 6176eb5c-19de-4c07-bcc0-2e38f8965966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204951(v=OCS.15)
ms:contentKeyID: 48184323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 236023756f8d2c917812d38f5a03da8dd4c40b5b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-global-policy-for-persistent-chat-in-lync-server-2013"></a>Configurar la directiva global para chat persistente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-06_

Puede usar la directiva global predeterminada por sí misma para habilitar la configuración de chat persistente para todos los usuarios de su implementación. También puede especificar directivas adicionales para que los usuarios puedan controlar si el chat persistente está habilitado o deshabilitado para determinados usuarios y sitios.

No puede eliminar la directiva global. Si intenta eliminarla, la configuración se restablecerá en los valores predeterminados.

<div>


> [!NOTE]  
> Para configurar y usar el servidor de chat persistente, primero debe usar topología Builder para agregar la compatibilidad con el servidor de chat persistente a la topología y, a continuación, publicar la topología. Para obtener más información, vea <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Agregar un servidor de chat persistente a su implementación en Lync Server 2013</A> en la documentación de implementación.<BR>Para configurar las opciones de configuración del servidor de chat persistentes, vea <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">configurar las opciones del servidor de chat persistente globalmente o para el grupo de servidores de chat persistente en Lync Server 2013</A> en la documentación de implementación.



</div>

<div>

## <a name="to-configure-the-global-policy-for-persistent-chat"></a>Para configurar la directiva global para el chat persistente

1.  Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.

2.  En el menú **Inicio** , seleccione el panel de control de Lync Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md) en la documentación de operaciones.
    
    <div>
    

    > [!IMPORTANT]  
    > También puede usar los cmdlets de Windows PowerShell. Para obtener más información, vea <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">configuración del servidor de chat persistente mediante cmdlets de Windows PowerShell</A> en la documentación de implementación.

    
    </div>

3.  En el panel de control de Lync Server, haga clic en **chat persistente**y en **Directiva de chat persistente**.

4.  Haga clic en **Global** en la lista de directivas, en **Editar** y, luego, en **Mostrar detalles**.

5.  En **Editar directiva de chat persistente - Global**, haga lo siguiente:
    
      - En **Nombre**, especifique un nuevo nombre para la directiva global si no desea usar el valor predeterminado de Global.
    
      - En **Descripción**, proporcione detalles sobre cuál es la Directiva de usuario (por ejemplo, la directiva global de centralSiteName).
    
      - Para controlar el chat persistente de todos los sitios y usuarios que no se controlan específicamente mediante una directiva de sitio o una directiva de usuario, Active o desactive la casilla de verificación **Habilitar conversación persistente** .

6.  Haga clic en **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

