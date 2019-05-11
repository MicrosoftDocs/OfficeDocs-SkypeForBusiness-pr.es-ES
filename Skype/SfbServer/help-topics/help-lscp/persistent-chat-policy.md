---
title: Directiva de chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatPolicy
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb9e95b9-f69d-4545-970f-9dfdd93b0eff
description: Puede usar la página Directiva de chat persistente del grupo Chat persistente para administrar directivas en un nivel global, de grupo, de sitio o de usuario, además de configurar la directiva global predeterminada y crear una o varias directivas de sitio y usuario adicionales para su implementación. Si el servidor de Chat persistente está habilitado para un usuario mediante una directiva, el entorno de servidor de Chat persistente aparece en su cliente.
ms.openlocfilehash: 73abb43b79baa807f4319cde8c7643f6bc5caa9d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906651"
---
# <a name="persistent-chat-policy"></a>Directiva de chat persistente
 
Puede usar la página **Directiva de chat persistente** del grupo **Chat persistente** para administrar directivas en un nivel global, de grupo, de sitio o de usuario, además de configurar la directiva global predeterminada y crear una o varias directivas de sitio y usuario adicionales para su implementación. Si el servidor de Chat persistente está habilitado para un usuario mediante una directiva, el entorno de servidor de Chat persistente aparece en su cliente.
  
La directiva global se crea automáticamente al implementar servidor de Chat persistente, y puede ser configurada, pero no elimina. Debido a que la directiva global se aplica a todos los usuarios, no tiene que se establecerá por usuario.
  
Puede crear y configurar varias directivas de usuario y de sitio que, junto con la directiva global, permiten a los usuarios para el servidor de Chat persistente. Las directivas de servidor de Chat persistente de grupo de servidores y sitios reemplazan la directiva global del servidor de Chat persistente, pero sólo para los usuarios de ese sitio. Las directivas de usuario reemplazan a las directivas globales, de grupo y de sitio para los usuarios que tengan asignada esa directiva de usuario.
  
> [!NOTE]
> Para configurar y usar el servidor de Chat persistente, debe primero usar el generador de topología para agregar compatibilidad con servidor de Chat persistente a la topología y, a continuación, publique la topología. Para obtener información detallada, vea [Agregar servidor de Chat persistente a su Skype para topología empresarial Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md). 
  
## <a name="tasks-that-you-can-perform"></a>Tareas que puede realizar

En la página **Directiva de chat persistente** puede realizar las siguientes tareas: habilitar y administrar la directiva de servidor de chat persistente.
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a>Para configurar la directiva Global para Chat persistente

1. Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.
    
2. Desde el menú **Inicio** , seleccione el Skype para el Panel de Control de servidor empresarial o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.
    
3. En Skype para el Panel de Control de servidor empresarial, haga clic en **Chat persistente**y, a continuación, haga clic en **Directiva de Chat persistente**.
    
4. Haga clic en **Global** en la lista de directivas, en **Editar** y, luego, en **Mostrar detalles**.
    
5. En **Editar directiva de chat persistente - Global**, haga lo siguiente:
    
   - En **Nombre**, especifique un nuevo nombre para la directiva global si no desea usar el valor predeterminado de Global.
    
   - En **Descripción**, proporcione información detallada acerca de la directiva de usuario (por ejemplo, directiva Global de _centralSiteName_).
    
   - Para controlar el Chat persistente para todos los sitios y los usuarios no controlados específicamente mediante una directiva de sitio o usuario, active o desactive la casilla de verificación **Habilitar Chat persistente** .
    
6. Haga clic en **Confirmar**.
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a>Para crear una directiva de Chat persistente para un sitio

Para cada sitio que haya implementado, puede crear una directiva de Chat persistente específica del sitio.
  
La configuración de la directiva de sitio reemplaza la directiva global, pero solo para el sitio específico que abarca la directiva de sitio.
  
1. Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.
    
2. Desde el menú **Inicio** , seleccione el Skype para el Panel de Control de servidor empresarial o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Directiva de chat persistente**.
    
4. Haga clic en **Nuevo** y en **Directiva de sitio**.
    
5. En **Seleccionar un sitio**, haga clic en el sitio al que se va a aplicar la directiva.
    
6. En **Nueva directiva de chat persistente**, haga lo siguiente:
    
   - En **Nombre**, especifique un nombre para la nueva directiva de sitio (por ejemplo, Redmond).
    
   - En **Descripción**, dé detalles sobre lo que es la directiva del sitio (por ejemplo, directiva de salón de chat de Redmond).
    
   - Para controlar el chat persistente para todos los sitios no controlados específicamente con una directiva de sitio, active o desactive la casilla **Habilitar chat persistente**.
    
7. Haga clic en **Confirmar**.
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a>Para crear una directiva de usuario para Chat persistente

En Skype para el Panel de Control de servidor empresarial, es posible definir directivas de usuario que se pueden asignar a los usuarios de **los usuarios**.
  
La directiva de usuario reemplaza la directiva global y las directivas de sitio, pero solo para los usuarios específicos que tienen asignada dicha directiva.
  
1. Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.
    
2. Desde el menú **Inicio** , seleccione el Skype para el Panel de Control de servidor empresarial o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Directiva de chat persistente**.
    
4. Haga clic en **Nuevo** y, luego, en **Directiva de usuario**.
    
5. En **Nueva directiva de chat persistente**, haga lo siguiente:
    
   - En **Nombre**, especifique un nombre para la nueva directiva de usuario.
    
   - En **Descripción**, proporcione información detallada acerca de la directiva de usuario (por ejemplo, directiva de Chat persistente para usuario específico).
    
   - Para controlar el Chat persistente para todos los usuarios que no se controlan específicamente a través de una directiva de usuario, active o desactive la casilla de verificación **Habilitar Chat persistente** .
    
6. Haga clic en **Confirmar**.
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a>Para aplicar una directiva de usuario de Chat persistente a una cuenta de usuario

Si un usuario tiene habilitado para Skype para Business Server, puede aplicar las directivas adecuadas a determinados usuarios para habilitar o deshabilitarlas para servidor de Chat persistente.
  
Use el procedimiento de este tema para aplicar una directiva de usuario de Chat persistente creada previamente a una o más cuentas de usuario o grupos de usuarios.
  
1. Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.
    
2. Desde el menú **Inicio** , seleccione el Skype para el Panel de Control de servidor empresarial o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.
    
3. En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, busque la cuenta de usuario que desea configurar.
    
4. En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, luego, en **Mostrar detalles**.
    
5. En **Editar usuario de Lync Server** en **Directiva de Chat persistente**, seleccione la directiva de usuario de Chat persistente que se desea aplicar.
    
    > [!NOTE]
    > La ** \<automática\> ** configuración aplica la directiva en vigor de forma predeterminada. El servidor aplica automáticamente esta configuración.
  
6. Haga clic en **Confirmar**.
    

