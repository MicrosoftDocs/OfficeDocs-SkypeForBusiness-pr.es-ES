---
title: Página principal de directiva de chat persistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0dc18d5c-82d6-4d39-afb1-efdb3ae6d2c7
description: Puede usar la página Directiva de chat persistente del grupo de chat persistente para administrar directivas a nivel global, de grupo, de sitio o de usuario, incluida la configuración de la directiva global predeterminada y la creación de una o más directivas de usuario y sitio adicionales para la implementación. Si un usuario está habilitado para el servidor de chat persistente por directiva, el entorno del servidor de chat persistente aparece en su cliente.
ms.openlocfilehash: 9664cbf182fe388fbffd2b270e306a4c17b36e95
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819310"
---
# <a name="persistent-chat-policy-main-page"></a>Página principal de directiva de chat persistente
 
Puede usar la página Directiva de **chat** persistente del grupo de **chat** persistente para administrar directivas a nivel global, de grupo, de sitio o de usuario, incluida la configuración de la directiva global predeterminada y la creación de una o más directivas de usuario y sitio adicionales para su implementación. Si un usuario está habilitado para el servidor de chat persistente por directiva, el entorno del servidor de chat persistente aparece en su cliente.
  
> [!NOTE]
> En la topología, las directivas de sitio del servidor de chat persistente se aplican globalmente, por grupo de usuarios, por sitio de usuario o por usuario. 
  
La directiva global se crea automáticamente al implementar el servidor de chat persistente y se puede configurar, pero no eliminar. Dado que la directiva global se aplica a todos los usuarios, no tiene que establecerse por usuario.
  
Puede crear y configurar varias directivas de sitio y usuario que, junto con la directiva global, habilitan a los usuarios para el servidor de chat persistente. Las directivas de servidor de chat persistente de grupo y sitio invalidan la directiva global del servidor de chat persistente, pero solo para los usuarios de ese sitio. Las directivas de usuario anulan las directivas globales, de grupo y de sitio para los usuarios a los que se asigna la directiva de usuario.
  
> [!NOTE]
> Para configurar y usar el servidor de chat persistente, primero debe usar el Generador de topologías para agregar compatibilidad con el servidor de chat persistente a la topología y, a continuación, publicar la topología. Para obtener más información, consulte Agregar un servidor de chat persistente a la topología de [Skype Empresarial Server 2015.](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md) 
  
## <a name="tasks-that-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas en la página Directiva de **chat** persistente: habilitar y administrar la directiva de servidor de chat persistente.
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a>Para configurar la directiva global para chat persistente

1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. En el **menú Inicio,** seleccione el Panel de control de Skype Empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.
    
3. En el Panel de control de Skype Empresarial Server, haga clic en **Chat** persistente y, a continuación, haga clic en **Directiva de chat persistente.**
    
4. Haga clic en **Global** en la lista de directivas, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.
    
5. In **Editar directiva de chat persistente - Global**, haga lo siguiente:
    
   - En **Nombre**, especifique un nombre nuevo para la directiva global, si no desea usar el nombre predeterminado (Global).
    
   - En **Descripción,** proporcione detalles sobre cuál es la directiva de usuario (por ejemplo, Directiva global para  _centralSiteName_).
    
   - Para controlar el chat persistente para todos los sitios y usuarios que no se controlan específicamente a través de una directiva de sitio o de usuario, active o desactive la casilla Habilitar **chat** persistente.
    
6. Haga clic en **Confirmar**.
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a>Para crear una directiva de chat persistente para un sitio

Para cada sitio que haya implementado, puede crear una directiva de chat persistente específica del sitio.
  
La configuración de la directiva de sitio invalida la directiva global, pero solo en el caso del sitio específico que determina la directiva.
  
1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. En el **menú Inicio,** seleccione el Panel de control de Skype Empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, a continuación, en **Directiva de chat persistente**.
    
4. Haga clic en **Nuevo** y en **Directiva de sitio**.
    
5. En **Seleccionar un sitio**, haga clic en el sitio al que se va a aplicar la directiva.
    
6. En **Nueva directiva de chat persistente**, haga lo siguiente:
    
   - En **Nombre**, especifique un nombre para la nueva directiva de sitio (por ejemplo, Redmond).
    
   - En **Descripción**, proporcione información detallada sobre la directiva de sitio (por ejemplo, directiva de salón de chat para Redmond).
    
   - Para controlar el chat persistente para todos los sitios no controlados específicamente mediante una directiva de sitio, active o desactive la casilla **Habilitar chat persistente**.
    
7. Haga clic en **Confirmar**.
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a>Para crear una directiva de usuario para chat persistente

En el Panel de control de Skype Empresarial Server, defina las directivas de usuario que se pueden asignar a los usuarios en **Usuarios.**
  
Las directivas de usuario invalidan las directivas globales y las directivas de sitio, aunque solo se pueden asignar a usuarios específicos.
  
1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. En el **menú Inicio,** seleccione el Panel de control de Skype Empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, a continuación, en **Directiva de chat persistente**.
    
4. Haga clic en **Nuevo** y en **Directiva de usuario**.
    
5. En **Nueva directiva de chat persistente**, haga lo siguiente:
    
   - En **Nombre**, especifique un nombre para la nueva directiva de usuario.
    
   - En **Descripción,** proporcione detalles sobre la directiva de usuario (por ejemplo, directiva de chat persistente para un usuario específico).
    
   - Para controlar el chat persistente para todos los usuarios que no están controlados específicamente a través de una directiva de usuario, active o desactive la casilla Habilitar **chat** persistente.
    
6. Haga clic en **Confirmar**.
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a>Para aplicar una directiva de usuario de chat persistente a una cuenta de usuario

Si un usuario se ha habilitado para Skype Empresarial, puede aplicar directivas adecuadas a usuarios específicos para habilitarlos o deshabilitarlos para el servidor de chat persistente.
  
Use el procedimiento descrito en este tema para aplicar una directiva de usuario de chat persistente creada anteriormente a una o varias cuentas de usuario o grupos de usuarios.
  
1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. En el **menú Inicio,** seleccione el Panel de control de Skype Empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.
    
3. En la barra de navegación izquierda, haga clic en  **Usuarios** y, a continuación, busque en la cuenta de usuario que desea configurar.
    
4. En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en  **Editar** y, a continuación, en  **Mostrar detalles**.
    
5. En **Editar usuario de Lync Server en** la directiva de chat **persistente,** seleccione la directiva de usuario de chat persistente que desee aplicar.
    
    > [!NOTE]
    > La **\<Automatic\>** configuración aplica la directiva efectiva predeterminada. Esta configuración se aplica automáticamente por el servidor.
  
6. Haga clic en **Confirmar**.
    

