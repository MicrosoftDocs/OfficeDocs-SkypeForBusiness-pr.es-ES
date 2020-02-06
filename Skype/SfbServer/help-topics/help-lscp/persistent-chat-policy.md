---
title: Directiva de chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatPolicy
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb9e95b9-f69d-4545-970f-9dfdd93b0eff
description: Puede usar la página Directiva de chat persistente del grupo Chat persistente para administrar directivas en un nivel global, de grupo, de sitio o de usuario, además de configurar la directiva global predeterminada y crear una o varias directivas de sitio y usuario adicionales para su implementación. Si el servidor de chat persistente está habilitado para un usuario por directiva, el entorno del servidor de chat persistente aparece en el cliente.
ms.openlocfilehash: 6692ef8314c3eb1ef38ade8cdbee26d3d76410ef
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822513"
---
# <a name="persistent-chat-policy"></a>Directiva de chat persistente
 
Puede usar la página **Directiva de chat persistente** del grupo **Chat persistente** para administrar directivas en un nivel global, de grupo, de sitio o de usuario, además de configurar la directiva global predeterminada y crear una o varias directivas de sitio y usuario adicionales para su implementación. Si el servidor de chat persistente está habilitado para un usuario por directiva, el entorno del servidor de chat persistente aparece en el cliente.
  
La directiva global se crea automáticamente al implementar un servidor de chat persistente, y puede configurarse, pero no eliminarse. Puesto que la directiva global se aplica a todos los usuarios, no es necesario establecerla para cada usuario.
  
Puede crear y configurar varias directivas de sitio y de usuario que, junto con la directiva global, permitan a los usuarios usar el servidor de chat persistente. Las directivas del servidor de chat persistente del sitio y del grupo invalidan la Directiva del servidor de chat persistente global, pero solo para los usuarios de ese sitio. Las directivas de usuario reemplazan a las directivas globales, de grupo y de sitio para los usuarios que tengan asignada esa directiva de usuario.
  
> [!NOTE]
> Para configurar y usar el servidor de chat persistente, primero debe usar topología Builder para agregar la compatibilidad con el servidor de chat persistente a la topología y, a continuación, publicar la topología. Para obtener más información, consulte [Agregar un servidor de chat persistente a su topología de 2015 de Skype empresarial Server](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md). 
  
## <a name="tasks-that-you-can-perform"></a>Tareas que puede realizar

En la página **Directiva de chat persistente** puede realizar las siguientes tareas: habilitar y administrar la directiva de servidor de chat persistente.
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a>Para configurar la directiva global para el chat persistente

1. Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.
    
2. En el menú **Inicio** , seleccione el panel de control de Skype empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador.
    
3. En el panel de control de Skype empresarial Server, haga clic en **chat persistente**y, a continuación, en **Directiva de chat persistente**.
    
4. Haga clic en **Global** en la lista de directivas, en **Editar** y, luego, en **Mostrar detalles**.
    
5. En **Editar directiva de chat persistente - Global**, haga lo siguiente:
    
   - En **Nombre**, especifique un nuevo nombre para la directiva global si no desea usar el valor predeterminado de Global.
    
   - En **Descripción**, proporcione detalles sobre cuál es la Directiva de usuario (por ejemplo, la directiva global de _centralSiteName_).
    
   - Para controlar el chat persistente de todos los sitios y usuarios que no se controlan específicamente mediante una directiva de sitio o una directiva de usuario, Active o desactive la casilla de verificación **Habilitar conversación persistente** .
    
6. Haga clic en **Confirmar**.
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a>Para crear una directiva de chat persistente para un sitio

Para cada sitio que haya implementado, puede crear una directiva de chat persistente específica de un sitio.
  
La configuración de la directiva de sitio reemplaza la directiva global, pero solo para el sitio específico que abarca la directiva de sitio.
  
1. Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.
    
2. En el menú **Inicio** , seleccione el panel de control de Skype empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador.
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Directiva de chat persistente**.
    
4. Haga clic en **Nuevo** y en **Directiva de sitio**.
    
5. En **Seleccionar un sitio**, haga clic en el sitio al que se va a aplicar la directiva.
    
6. En **Nueva directiva de chat persistente**, haga lo siguiente:
    
   - En **Nombre**, especifique un nombre para la nueva directiva de sitio (por ejemplo, Redmond).
    
   - En **Descripción**, dé detalles sobre lo que es la directiva del sitio (por ejemplo, directiva de salón de chat de Redmond).
    
   - Para controlar el chat persistente para todos los sitios no controlados específicamente con una directiva de sitio, active o desactive la casilla **Habilitar chat persistente**.
    
7. Haga clic en **Confirmar**.
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a>Para crear una directiva de usuario para el chat persistente

En el panel de control de Skype empresarial Server, puede definir directivas de usuario que se pueden asignar a los usuarios de **los usuarios**.
  
La directiva de usuario reemplaza la directiva global y las directivas de sitio, pero solo para los usuarios específicos que tienen asignada dicha directiva.
  
1. Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.
    
2. En el menú **Inicio** , seleccione el panel de control de Skype empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador.
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Directiva de chat persistente**.
    
4. Haga clic en **Nuevo** y, luego, en **Directiva de usuario**.
    
5. En **Nueva directiva de chat persistente**, haga lo siguiente:
    
   - En **Nombre**, especifique un nombre para la nueva directiva de usuario.
    
   - En **Descripción**, proporcione detalles sobre qué es la Directiva de usuario (por ejemplo, la Directiva de chat persistente para un usuario específico).
    
   - Para controlar el chat persistente para todos los usuarios que no se controlan específicamente mediante una directiva de usuario, Active o desactive la casilla de verificación **Habilitar conversación persistente** .
    
6. Haga clic en **Confirmar**.
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a>Para aplicar una directiva de usuario de chat persistente a una cuenta de usuario

Si se ha habilitado un usuario para Skype empresarial Server, puede aplicar las directivas apropiadas a determinados usuarios para habilitarlos o deshabilitarlos para el servidor de chat persistente.
  
Use el procedimiento de este tema para aplicar una directiva de usuario de chat persistente creada previamente a una o más cuentas de usuario o grupos de usuarios.
  
1. Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.
    
2. En el menú **Inicio** , seleccione el panel de control de Skype empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador.
    
3. En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, busque la cuenta de usuario que desea configurar.
    
4. En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, luego, en **Mostrar detalles**.
    
5. En **Editar usuario de Lync Server** en **Directiva de chat persistente**, seleccione la Directiva de usuario de chat persistente que desea aplicar.
    
    > [!NOTE]
    > La ** \<configuración\> automática** aplica la Directiva vigente predeterminada. El servidor aplica automáticamente esta configuración.
  
6. Haga clic en **Confirmar**.
    

