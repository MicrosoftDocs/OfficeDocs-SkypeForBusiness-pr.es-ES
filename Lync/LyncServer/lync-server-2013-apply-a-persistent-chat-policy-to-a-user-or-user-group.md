---
title: 'Lync Server 2013: Aplicar una directiva de chat persistente a un usuario o grupo de usuarios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Apply a Persistent Chat policy to a user or user group
ms:assetid: 809ef4e0-8d42-4feb-b7c0-3995f39867a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205038(v=OCS.15)
ms:contentKeyID: 48184652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a2fbed0a752c1bf97bab5a4f67fadf12d8077a6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="apply-a-persistent-chat-policy-to-a-user-or-user-group-in-lync-server-2013"></a>Aplicar una directiva de chat persistente a un usuario o grupo de usuarios en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-06_

Si se ha habilitado un usuario para Lync Server 2013, puede aplicar las directivas apropiadas a determinados usuarios para habilitarlos o deshabilitarlos para el servidor de chat persistente.

<div>


> [!NOTE]  
> Para configurar y usar el servidor de chat persistente, primero debe usar topología Builder para agregar la compatibilidad con el servidor de chat persistente a la topología y, a continuación, publicar la topología. Para obtener más información, vea <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Agregar un servidor de chat persistente a su implementación en Lync Server 2013</A> en la documentación de implementación.<BR>Para configurar las opciones de configuración del servidor de chat persistentes, vea <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">configurar las opciones del servidor de chat persistente globalmente o para el grupo de servidores de chat persistente en Lync Server 2013</A> en la documentación de implementación.



</div>

Use el procedimiento de este tema para aplicar una directiva de usuario de chat persistente creada previamente a una o más cuentas de usuario o grupos de usuarios.

<div>

## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a>Para aplicar una directiva de usuario de chat persistente a una cuenta de usuario

1.  Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.

2.  En el menú **Inicio** , seleccione el panel de control de Lync Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, busque la cuenta de usuario que desea configurar.

4.  En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, luego, en **Mostrar detalles**.

5.  En **Editar usuario de Lync Server** en **Directiva de chat persistente**, seleccione la Directiva de usuario de chat persistente que desea aplicar.
    
    <div>
    

    > [!NOTE]  
    > La <STRONG> &lt;configuración&gt; automática</STRONG> aplica la Directiva vigente predeterminada. El servidor aplica automáticamente esta configuración.

    
    </div>

6.  Haga clic en **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

