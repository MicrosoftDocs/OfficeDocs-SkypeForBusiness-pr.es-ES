---
title: Página principal de directiva de chat persistente
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0dc18d5c-82d6-4d39-afb1-efdb3ae6d2c7
description: Puede utilizar la página de directiva persistente Chat del grupo Chat persistentes para administrar directivas en un nivel global, de grupo, sitio o usuario, incluyendo la configuración de la directiva global predeterminada y la creación de uno o más usuarios y sitio directivas adicionales para su implementación. Si un usuario está habilitado para el servidor de charla persistente por directiva, el entorno de servidor de charla persistente aparece en su cliente.
ms.openlocfilehash: 14d600c558a7a72887aa7ff3e349857115e8a792
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="persistent-chat-policy-main-page"></a>Página principal de directiva de chat persistente
 
Puede usar la página **Directiva de chat persistente** del grupo **Chat persistente** para administrar directivas en un nivel global, de grupo, de sitio o de usuario, además de configurar la directiva global predeterminada y crear una o varias directivas de sitio y usuario adicionales para su implementación. Si un usuario está habilitado para el servidor de charla persistente por directiva, el entorno de servidor de charla persistente aparece en su cliente.
  
> [!NOTE]
> En la topología, el servidor de charla persistente sitio directivas se aplica globalmente, por grupo de usuario, o por el sitio del usuario o por usuario. 
  
La directiva global se crea automáticamente al implementar servidor de Chat persistente, y puede ser configurado, pero no eliminar. Porque la directiva global se aplica a todos los usuarios, no tiene que establecerse para cada usuario.
  
Puede crear y configurar varias directivas de usuario y sitio que, junto con la directiva global, permiten a los usuarios para el servidor de charla persistente. Sitio y grupo de directivas de servidor de charla persistente anulan la directiva persistente Chat Server global, pero sólo para los usuarios de ese sitio. Las directivas de usuario reemplazan a las directivas globales, de grupo y de sitio para los usuarios que tengan asignada esa directiva de usuario.
  
> [!NOTE]
> Para configurar y utilizar el servidor de charla persistente, debe utilizar primero el generador de topología para agregar compatibilidad con el servidor de charla persistente a la topología y, a continuación, publicar la topología. Para obtener información detallada, vea [Agregar servidor Chat persistente a su Skype para Business Server 2015 topología](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md). 
  
## <a name="tasks-that-you-can-perform"></a>Tareas que puede realizar

En la página **Directiva de chat persistente** puede realizar las siguientes tareas: habilitar y administrar la directiva de servidor de chat persistente.
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a>Para configurar la directiva Global para Chat persistente

1. Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.
    
2. Desde el menú **Inicio** , seleccione el Skype para Panel de Control de servidor de Business o abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin.
    
3. En Skype para Business Server Control Panel, haga clic en **Charla persistente**y, a continuación, haga clic en **Directiva de Chat persistentes**.
    
4. Haga clic en **Global** en la lista de directivas, en **Editar** y, luego, en **Mostrar detalles**.
    
5. En **Editar directiva de chat persistente - Global**, haga lo siguiente:
    
  - En **Nombre**, especifique un nuevo nombre para la directiva global si no desea usar el valor predeterminado de Global.
    
  - En **Descripción**, proporcione detalles acerca de la directiva de usuario (por ejemplo, la directiva Global para _centralSiteName_).
    
  - Para controlar la charla persistente para todos los sitios y los usuarios que no específicamente se controla a través de una directiva de sitio o usuario, active o desactive la casilla de verificación **Habilitar Chat persistente** .
    
6. Haga clic en **Confirmar**.
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a>Para crear una directiva persistente de charla para un sitio

Para cada sitio que se ha implementado, puede crear una directiva persistente Chat específico del sitio.
  
La configuración de la directiva de sitio reemplaza la directiva global, pero solo para el sitio específico que abarca la directiva de sitio.
  
1. Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.
    
2. Desde el menú **Inicio** , seleccione el Skype para Panel de Control de servidor de Business o abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin.
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Directiva de chat persistente**.
    
4. Haga clic en **Nuevo** y en **Directiva de sitio**.
    
5. En **Seleccionar un sitio**, haga clic en el sitio al que se va a aplicar la directiva.
    
6. En **Nueva directiva de chat persistente**, haga lo siguiente:
    
  - En **Nombre**, especifique un nombre para la nueva directiva de sitio (por ejemplo, Redmond).
    
  - En **Descripción**, dé detalles sobre lo que es la directiva del sitio (por ejemplo, directiva de salón de chat de Redmond).
    
  - Para controlar el chat persistente para todos los sitios no controlados específicamente con una directiva de sitio, active o desactive la casilla **Habilitar chat persistente**.
    
7. Haga clic en **Confirmar**.
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a>Para crear una directiva de usuario para Chat persistente

Skype para el Panel de Control de servidor empresarial, para definir las directivas de usuario que se pueden asignar a los usuarios de **los usuarios**.
  
La directiva de usuario reemplaza la directiva global y las directivas de sitio, pero solo para los usuarios específicos que tienen asignada dicha directiva.
  
1. Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.
    
2. Desde el menú **Inicio** , seleccione el Skype para Panel de Control de servidor de Business o abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin.
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Directiva de chat persistente**.
    
4. Haga clic en **Nuevo** y, luego, en **Directiva de usuario**.
    
5. En **Nueva directiva de chat persistente**, haga lo siguiente:
    
  - En **Nombre**, especifique un nombre para la nueva directiva de usuario.
    
  - En **Descripción**, proporcione detalles acerca de la directiva de usuario (por ejemplo, la directiva persistente de charla para un usuario específico).
    
  - Para controlar la charla persistente para todos los usuarios que no están controlados específicamente a través de una directiva de usuario, active o desactive la casilla de verificación **Habilitar Chat persistente** .
    
6. Haga clic en **Confirmar**.
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a>Para aplicar una directiva de usuario de charla persistente a una cuenta de usuario

Si un usuario se ha habilitado para Skype para el negocio, puede aplicar las políticas apropiadas a usuarios específicos para habilitarlos o deshabilitarlos para servidor de Chat persistente.
  
Utilice el procedimiento de este tema para aplicar una directiva de usuario de charla persistente creada anteriormente a una o más cuentas de usuario o grupos de usuarios.
  
1. Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.
    
2. Desde el menú **Inicio** , seleccione el Skype para Panel de Control de servidor de Business o abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin.
    
3. En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, busque la cuenta de usuario que desea configurar.
    
4. En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, finalmente, en **Mostrar detalles**.
    
5. En **Editar usuario de Lync Server** en **charla persistente de la política**, seleccione la directiva de usuario persistentes de charla que desea aplicar.
    
    > [!NOTE]
    > La ** \<automática\> ** configuración aplica la directiva efectiva de forma predeterminada. El servidor aplica esta configuración automáticamente.
  
6. Haga clic en **Confirmar**.
    

