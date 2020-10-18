---
title: 'Lync Server 2013: crear una directiva de usuario para chat persistente'
description: 'Lync Server 2013: crear una directiva de usuario para chat persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a user policy for Persistent Chat
ms:assetid: aa3774af-d442-4206-8a68-2fbb9102e9d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205170(v=OCS.15)
ms:contentKeyID: 48185103
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fcbe761d535f8c58c2f83750cdc8808cfb62634
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578026"
---
# <a name="create-a-user-policy-for-persistent-chat-in-lync-server-2013"></a>Crear una directiva de usuario para chat persistente en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-06_

En el panel de control de Lync Server, puede definir directivas de usuario que se pueden asignar a usuarios en **usuarios**.

Las directivas de usuario invalidan las directivas globales y las directivas de sitio, aunque solo se pueden asignar a usuarios específicos.

<div>


> [!NOTE]  
> Para configurar y usar el servidor de chat persistente, primero debe usar el generador de topologías para agregar compatibilidad con el servidor de chat persistente a la topología y, a continuación, publicar la topología. Para obtener más información, consulte <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Agregar un servidor de chat persistente a la implementación en Lync Server 2013</A> en la documentación sobre implementación.<BR>Para configurar las opciones de configuración del servidor de chat persistente, vea <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure persistent chat Server Options Globally or for persistent chat Server Pool in Lync Server 2013</A> en la documentación sobre implementación.



</div>

<div>

## <a name="to-create-a-user-policy-for-persistent-chat"></a>Para crear una directiva de usuario para chat persistente

1.  Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  En el menú **Inicio** , seleccione el panel de control de Lync Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración. Para obtener más información acerca de los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > También puede usar cmdlets de Windows PowerShell. Consulte <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring persistent chat Server by Using Windows PowerShell cmdlets</A> en la documentación sobre implementación.

    
    </div>

3.  En la barra de navegación izquierda, haga clic en **Chat persistente** y, a continuación, en **Directiva de chat persistente**.

4.  Haga clic en **Nuevo** y en **Directiva de usuario **.

5.  En **Nueva directiva de chat persistente**, haga lo siguiente:
    
      - En **Nombre**, especifique un nombre para la nueva directiva de usuario.
    
      - En **Descripción**, proporcione información detallada acerca de la función de la Directiva de usuario (por ejemplo, Directiva de chat persistente para un usuario específico).
    
      - Para controlar el chat persistente para todos los usuarios que no se controlan específicamente mediante una directiva de usuario, Active o desactive la casilla **Habilitar chat persistente** .

6.  Haga clic en **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

