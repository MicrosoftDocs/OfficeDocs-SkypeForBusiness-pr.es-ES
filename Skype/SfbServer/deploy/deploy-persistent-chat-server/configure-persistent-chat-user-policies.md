---
title: Configurar las directivas de usuario del chat persistente de Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 'Resumen: Lea este tema para obtener información sobre cómo crear directivas de usuario inicial para el servidor de Chat persistente en Skype para Business Server 2015. Las directivas de usuario de charla persistentes determinan si los usuarios pueden acceder a salones de chat.'
ms.openlocfilehash: e082898d92e622827e2543316b07a8be224c56c3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225458"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a>Configurar las directivas de usuario del chat persistente de Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para obtener información sobre cómo crear directivas de usuario inicial para el servidor de Chat persistente en Skype para Business Server 2015. Las directivas de usuario de charla persistentes determinan si los usuarios pueden acceder a salones de chat.
  
Puede administrar las directivas de usuario del servidor de Chat persistente en los siguientes niveles: global, sitio o usuario. Inicialmente, configurar la directiva global para habilitar la configuración de Chat persistente para todos los usuarios de la implementación y, a continuación, crear las directivas de sitio y de usuario para controlar si Chat persistente está activado para determinados usuarios y sitios.
  
Este tema incluye las secciones siguientes:
  
- Configurar la directiva global
    
- Crear una directiva de sitio
    
- Crear una directiva de usuario
    
- Aplicar una directiva a un usuario o a un grupo de usuarios
    
> [!NOTE] 
> Chat persistente está disponible en Skype para Business Server 2015, pero ya no se admite en Skype para Business Server 2019. La misma funcionalidad está disponible en los equipos. Para obtener más información, vea [viaje de Skype para la empresa a los equipos de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si necesita usar chat en grupo, las opciones son para migrar los usuarios que requieren esta funcionalidad a los equipos, o para continuar usando Skype para Business Server 2015.

## <a name="configure-the-global-policy"></a>Configurar la directiva global

Para configurar la directiva global:
  
1. Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.
    
2. Desde el menú **Inicio** , seleccione el Skype para el Panel de Control de servidor empresarial o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.
    
3. En Skype para el Panel de Control de servidor empresarial, haga clic en **Chat persistente**y, a continuación, haga clic en **Directiva de Chat persistente**.
    
4. Haga clic en **Global** en la lista de directivas, en **Editar** y, luego, en **Mostrar detalles**.
    
5. En **Editar directiva de chat persistente - Global**, haga lo siguiente: 
    
   - En **Nombre**, especifique un nuevo nombre para la directiva global si no desea usar el valor predeterminado de Global.
    
   - En **Descripción**, proporcione información detallada acerca de la directiva de usuario (por ejemplo, directiva Global de _centralSiteName_).
    
   - Para controlar el Chat persistente para todos los sitios y los usuarios no controlados específicamente mediante una directiva de sitio o usuario, active o desactive la casilla de verificación **Habilitar Chat persistente** .
    
6. Haga clic en **Confirmar**.
    
## <a name="create-a-site-policy"></a>Crear una directiva de sitio

Para cada sitio que ha implementado, puede crear una directiva de chat persistente específica para el sitio. La configuración de la directiva de sitio reemplaza la directiva global, pero solo para el sitio específico que abarca la directiva de sitio. Para crear una directiva de sitio:
  
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
    
## <a name="create-a-user-policy"></a>Crear una directiva de usuario

Puede crear directivas de usuario específicas que reemplazan la directiva global y todas las directivas de sitio que abarcan al usuario. Para crear una directiva de usuario:
  
1. Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.
    
2. Desde el menú **Inicio** , seleccione el Skype para el Panel de Control de servidor empresarial o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Directiva de chat persistente**.
    
4. Haga clic en **Nuevo** y, luego, en **Directiva de usuario**.
    
5. En **Nueva directiva de chat persistente**, haga lo siguiente:
    
   - En **Nombre**, especifique un nombre para la nueva directiva de usuario.
    
   - En **Descripción**, proporcione información detallada acerca de la directiva de usuario (por ejemplo, directiva de Chat persistente para usuario específico).
    
   - Para controlar el Chat persistente para todos los usuarios que no se controlan específicamente a través de una directiva de usuario, active o desactive la casilla de verificación **Habilitar Chat persistente** .
    
6. Haga clic en **Confirmar**.
    
## <a name="apply-a-policy-to-a-user-account"></a>Aplicar una directiva a una cuenta de usuario

Después de crear políticas, puede aplicarlas a una cuenta de usuario de esta manera:
  
1. En una cuenta de usuario asignada al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Desde el menú **Inicio** , seleccione el Skype para el Panel de Control de servidor empresarial o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.
    
3. En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, busque la cuenta de usuario que desea configurar.
    
4. En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, luego, en **Mostrar detalles**.
    
5. En **Editar Skype para usuarios de empresa Server** en **Directiva de Chat persistente**, seleccione la directiva de usuario de Chat persistente que se desea aplicar.
    
    > [!NOTE]
    > La ** \<automática\> ** configuración aplica la directiva en vigor de forma predeterminada. El servidor aplica automáticamente esta configuración.
  
6. Haga clic en **Confirmar**.
    

