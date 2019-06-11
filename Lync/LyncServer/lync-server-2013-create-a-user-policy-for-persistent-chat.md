---
title: 'Lync Server 2013: Crear una directiva de usuario para chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a user policy for Persistent Chat
ms:assetid: aa3774af-d442-4206-8a68-2fbb9102e9d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205170(v=OCS.15)
ms:contentKeyID: 48185103
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a1d2cd767af4cbee7c416dc8f600ed9e9e192a0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-user-policy-for-persistent-chat-in-lync-server-2013"></a>Crear una directiva de usuario para chat persistente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-06_

En el panel de control de Lync Server, se definen directivas de usuario que se pueden asignar a los usuarios en **los usuarios**.

La directiva de usuario reemplaza la directiva global y las directivas de sitio, pero solo para los usuarios específicos que tienen asignada dicha directiva.

<div>


> [!NOTE]  
> Para configurar y usar el servidor de chat persistente, primero debe usar topología Builder para agregar la compatibilidad con el servidor de chat persistente a la topología y, a continuación, publicar la topología. Para obtener más información, vea <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Agregar un servidor de chat persistente a su implementación en Lync Server 2013</A> en la documentación de implementación.<BR>Para configurar las opciones de configuración del servidor de chat persistentes, vea <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">configurar las opciones del servidor de chat persistente globalmente o para el grupo de servidores de chat persistente en Lync Server 2013</A> en la documentación de implementación.



</div>

<div>

## <a name="to-create-a-user-policy-for-persistent-chat"></a>Para crear una directiva de usuario para el chat persistente

1.  Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.

2.  En el menú **Inicio** , seleccione el panel de control de Lync Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > También puede usar los cmdlets de Windows PowerShell. Para ver la <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">configuración del servidor de chat persistente, use los cmdlets de Windows PowerShell</A> en la documentación de implementación.

    
    </div>

3.  En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Directiva de chat persistente**.

4.  Haga clic en **Nuevo** y, luego, en **Directiva de usuario**.

5.  En **Nueva directiva de chat persistente**, haga lo siguiente:
    
      - En **Nombre**, especifique un nombre para la nueva directiva de usuario.
    
      - En **Descripción**, proporcione detalles sobre qué es la Directiva de usuario (por ejemplo, la Directiva de chat persistente para un usuario específico).
    
      - Para controlar el chat persistente para todos los usuarios que no se controlan específicamente mediante una directiva de usuario, Active o desactive la casilla de verificación **Habilitar conversación persistente** .

6.  Haga clic en **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

