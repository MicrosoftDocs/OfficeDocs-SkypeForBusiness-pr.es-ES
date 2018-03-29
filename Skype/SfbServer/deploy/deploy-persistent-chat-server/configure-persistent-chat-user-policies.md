---
title: Configurar las directivas de usuario del chat persistente de Skype Empresarial Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 'Resumen: Leer este tema para aprender a crear directivas de usuario inicial para servidor de Chat persistente en Skype para Business Server 2015. Las directivas de usuario persistentes de charla determinan si los usuarios tienen acceso a salones de chat.'
ms.openlocfilehash: 01ed6eb048f1949c93260c554eb58d0c76c5259f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a>Configurar las directivas de usuario del chat persistente de Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para aprender a crear directivas de usuario inicial para servidor de Chat persistente en Skype para Business Server 2015. Las directivas de usuario persistentes de charla determinan si los usuarios tienen acceso a salones de chat.
  
Puede administrar las directivas de usuario de servidor de charla persistente en los siguientes niveles: global, sitio o usuario. Inicialmente, configurar la directiva global para habilitar la configuración de Chat persistentes para todos los usuarios en la implementación y luego crear directivas de sitios y de usuario para controlar si la charla persistente está activado para sitios y usuarios específicos.
  
Este tema incluye las secciones siguientes:
  
- Configurar la directiva global
    
- Crear una directiva de sitio
    
- Crear una directiva de usuario
    
- Aplicar una directiva a un usuario o a un grupo de usuarios
    
## <a name="configure-the-global-policy"></a>Configurar la directiva global

Para configurar la directiva global:
  
1. En una cuenta de usuario asignada al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Desde el menú **Inicio** , seleccione el Skype para Panel de Control de servidor de Business o abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin.
    
3. En Skype para Business Server Control Panel, haga clic en **Charla persistente**y, a continuación, haga clic en **Directiva de Chat persistentes**.
    
4. Haga clic en **Global** en la lista de directivas, en **Editar** y, luego, en **Mostrar detalles**.
    
5. En **Editar directiva de chat persistente - Global**, haga lo siguiente: 
    
   - En **Nombre**, especifique un nuevo nombre para la directiva global si no desea usar el valor predeterminado de Global.
    
   - En **Descripción**, proporcione detalles acerca de la directiva de usuario (por ejemplo, la directiva Global para _centralSiteName_).
    
   - Para controlar la charla persistente para todos los sitios y los usuarios que no específicamente se controla a través de una directiva de sitio o usuario, active o desactive la casilla de verificación **Habilitar Chat persistente** .
    
6. Haga clic en **Confirmar**.
    
## <a name="create-a-site-policy"></a>Crear una directiva de sitio

Para cada sitio que ha implementado, puede crear una directiva de chat persistente específica para el sitio. La configuración de la directiva de sitio reemplaza la directiva global, pero solo para el sitio específico que abarca la directiva de sitio. Para crear una directiva de sitio:
  
1. En una cuenta de usuario asignada al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Desde el menú **Inicio** , seleccione el Skype para Panel de Control de servidor de Business o abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin.
    
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
  
1. En una cuenta de usuario asignada al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Desde el menú **Inicio** , seleccione el Skype para Panel de Control de servidor de Business o abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin.
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Directiva de chat persistente**.
    
4. Haga clic en **Nuevo** y, luego, en **Directiva de usuario**.
    
5. En **Nueva directiva de chat persistente**, haga lo siguiente:
    
   - En **Nombre**, especifique un nombre para la nueva directiva de usuario.
    
   - En **Descripción**, proporcione detalles acerca de la directiva de usuario (por ejemplo, la directiva persistente de charla para un usuario específico).
    
   - Para controlar la charla persistente para todos los usuarios que no están controlados específicamente a través de una directiva de usuario, active o desactive la casilla de verificación **Habilitar Chat persistente** .
    
6. Haga clic en **Confirmar**.
    
## <a name="apply-a-policy-to-a-user-account"></a>Aplicar una directiva a una cuenta de usuario

Después de crear políticas, puede aplicarlas a una cuenta de usuario de esta manera:
  
1. En una cuenta de usuario asignada al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Desde el menú **Inicio** , seleccione el Skype para Panel de Control de servidor de Business o abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin.
    
3. En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, busque la cuenta de usuario que desea configurar.
    
4. En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, finalmente, en **Mostrar detalles**.
    
5. En **Editar Skype para usuarios de servidores de empresa** en **charla persistente de la política**, seleccione la directiva de usuario persistentes de charla que desea aplicar.
    
    > [!NOTE]
    > La ** \<automática\> ** configuración aplica la directiva efectiva de forma predeterminada. El servidor aplica esta configuración automáticamente.
  
6. Haga clic en **Confirmar**.
    

