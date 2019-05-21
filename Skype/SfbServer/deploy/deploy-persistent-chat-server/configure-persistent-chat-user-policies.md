---
title: Configurar las directivas de usuario del chat persistente de Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 'Resumen: Lea este tema para obtener información sobre cómo crear directivas de usuario iniciales para el servidor de chat persistente en Skype empresarial Server 2015. Las directivas de usuario de chat persistente determinan si los usuarios tienen permitido el acceso a salones de chat.'
ms.openlocfilehash: 7c73b34f418946dda76302c0ee2abb18125e6f07
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34273857"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a>Configurar las directivas de usuario del chat persistente de Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para obtener información sobre cómo crear directivas de usuario iniciales para el servidor de chat persistente en Skype empresarial Server 2015. Las directivas de usuario de chat persistente determinan si los usuarios tienen permitido el acceso a salones de chat.
  
Puede administrar directivas de usuario del servidor de chat persistentes en los siguientes niveles: global, sitio o usuario. Inicialmente, debe configurar la directiva global para habilitar la configuración de chat persistente para todos los usuarios de la implementación y, a continuación, crear directivas de usuario y de sitio adicionales para controlar si el chat persistente está activado para usuarios y sitios específicos.
  
Este tema incluye las secciones siguientes:
  
- Configurar la directiva global
    
- Crear una directiva de sitio
    
- Crear una directiva de usuario
    
- Aplicar una directiva a un usuario o a un grupo de usuarios
    
> [!NOTE] 
> Chat persistente está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte Cómo desplazarse [de Skype empresarial a Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams). Si necesita usar una conversación persistente, puede elegir entre migrar los usuarios que tienen esta funcionalidad a teams o continuar usando Skype empresarial Server 2015.

## <a name="configure-the-global-policy"></a>Configurar la directiva global

Para configurar la directiva global:
  
1. Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.
    
2. En el menú **Inicio** , seleccione el panel de control de Skype empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador.
    
3. En el panel de control de Skype empresarial Server, haga clic en **chat persistente**y, a continuación, en **Directiva de chat persistente**.
    
4. Haga clic en **Global** en la lista de directivas, en **Editar** y, luego, en **Mostrar detalles**.
    
5. En **Editar directiva de chat persistente - Global**, haga lo siguiente: 
    
   - En **Nombre**, especifique un nuevo nombre para la directiva global si no desea usar el valor predeterminado de Global.
    
   - En **Descripción**, proporcione detalles sobre cuál es la Directiva de usuario (por ejemplo, la directiva global de _centralSiteName_).
    
   - Para controlar el chat persistente de todos los sitios y usuarios que no se controlan específicamente mediante una directiva de sitio o una directiva de usuario, Active o desactive la casilla de verificación **Habilitar conversación persistente** .
    
6. Haga clic en **Confirmar**.
    
## <a name="create-a-site-policy"></a>Crear una directiva de sitio

Para cada sitio que ha implementado, puede crear una directiva de chat persistente específica para el sitio. La configuración de la directiva de sitio reemplaza la directiva global, pero solo para el sitio específico que abarca la directiva de sitio. Para crear una directiva de sitio:
  
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
    
## <a name="create-a-user-policy"></a>Crear una directiva de usuario

Puede crear directivas de usuario específicas que reemplazan la directiva global y todas las directivas de sitio que abarcan al usuario. Para crear una directiva de usuario:
  
1. Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.
    
2. En el menú **Inicio** , seleccione el panel de control de Skype empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador.
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Directiva de chat persistente**.
    
4. Haga clic en **Nuevo** y, luego, en **Directiva de usuario**.
    
5. En **Nueva directiva de chat persistente**, haga lo siguiente:
    
   - En **Nombre**, especifique un nombre para la nueva directiva de usuario.
    
   - En **Descripción**, proporcione detalles sobre qué es la Directiva de usuario (por ejemplo, la Directiva de chat persistente para un usuario específico).
    
   - Para controlar el chat persistente para todos los usuarios que no se controlan específicamente mediante una directiva de usuario, Active o desactive la casilla de verificación **Habilitar conversación persistente** .
    
6. Haga clic en **Confirmar**.
    
## <a name="apply-a-policy-to-a-user-account"></a>Aplicar una directiva a una cuenta de usuario

Después de crear políticas, puede aplicarlas a una cuenta de usuario de esta manera:
  
1. En una cuenta de usuario asignada al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. En el menú **Inicio** , seleccione el panel de control de Skype empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador.
    
3. En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, busque la cuenta de usuario que desea configurar.
    
4. En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, luego, en **Mostrar detalles**.
    
5. En **Editar usuario de Skype empresarial Server** en **Directiva de chat persistente**, seleccione la Directiva de usuario de chat persistente que desea aplicar.
    
    > [!NOTE]
    > La ** \<configuración\> automática** aplica la Directiva vigente predeterminada. El servidor aplica automáticamente esta configuración.
  
6. Haga clic en **Confirmar**.
    

