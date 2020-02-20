---
title: 'Lync Server 2013: configurar la directiva global para chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the global policy for Persistent Chat
ms:assetid: 6176eb5c-19de-4c07-bcc0-2e38f8965966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204951(v=OCS.15)
ms:contentKeyID: 48184323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c77093e640d51204a7e16b2b32df02afcefe0bd7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-global-policy-for-persistent-chat-in-lync-server-2013"></a>Configure la directiva global para chat persistente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-06_

Puede usar la directiva global predeterminada solo para habilitar la configuración de chat persistente para todos los usuarios de la implementación. También puede especificar directivas adicionales para sitios y usuarios para controlar si el chat persistente está habilitado o deshabilitado para determinados usuarios y sitios.

No puede eliminar la directiva global. Si intenta eliminarla, la configuración se restablecerá con los valores predeterminados.

<div>


> [!NOTE]  
> Para configurar y usar el servidor de chat persistente, primero debe usar el generador de topologías para agregar compatibilidad con el servidor de chat persistente a la topología y, a continuación, publicar la topología. Para obtener más información, consulte <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Agregar un servidor de chat persistente a la implementación en Lync Server 2013</A> en la documentación sobre implementación.<BR>Para configurar las opciones de configuración del servidor de chat persistente, vea <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure persistent chat Server Options Globally or for persistent chat Server Pool in Lync Server 2013</A> en la documentación sobre implementación.



</div>

<div>

## <a name="to-configure-the-global-policy-for-persistent-chat"></a>Para configurar la directiva global para chat persistente

1.  Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  En el menú **Inicio** , seleccione el panel de control de Lync Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md) en la documentación de operaciones.
    
    <div>
    

    > [!IMPORTANT]  
    > También puede usar cmdlets de Windows PowerShell. Para obtener más información, consulte <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring persistent chat Server by Using Windows PowerShell cmdlets</A> in Deployment Documentation.

    
    </div>

3.  En el panel de control de Lync Server, haga clic en **chat persistente**y, a continuación, en **Directiva de chat persistente**.

4.  Haga clic en **Global** en la lista de directivas, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.

5.  In **Editar directiva de chat persistente - Global**, haga lo siguiente:
    
      - En **Nombre **, especifique un nombre nuevo para la directiva global, si no desea usar el nombre predeterminado (Global).
    
      - En **Descripción**, proporcione información detallada sobre la función de la Directiva de usuario (por ejemplo, directiva global para centralSiteName).
    
      - Para controlar el chat persistente para todos los sitios y usuarios que no se controlan específicamente mediante una directiva de sitio o de usuario, Active o desactive la casilla **Habilitar chat persistente** .

6.  Haga clic en **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

