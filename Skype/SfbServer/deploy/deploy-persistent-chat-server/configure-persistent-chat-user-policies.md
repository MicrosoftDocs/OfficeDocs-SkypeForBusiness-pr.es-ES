---
title: Configurar directivas de usuario de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 'Resumen: lea este tema para obtener información sobre cómo crear directivas de usuario iniciales para el servidor de chat persistente en Skype Empresarial Server 2015. Las directivas de usuario de chat persistente determinan si los usuarios tienen o no permiso de acceso a los salón de chat.'
ms.openlocfilehash: 531146a55b0282db191f503ef39e9be9e4d5f879
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802120"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a>Configurar directivas de usuario de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para obtener información sobre cómo crear directivas de usuario iniciales para el servidor de chat persistente en Skype Empresarial Server 2015. Las directivas de usuario de chat persistente determinan si los usuarios tienen o no permiso de acceso a los salón de chat.
  
Puede administrar las directivas de usuario del servidor de chat persistente en los siguientes niveles: global, de sitio o de usuario. Inicialmente, se configura la directiva global para habilitar la configuración de chat persistente para todos los usuarios de la implementación y, a continuación, se crean directivas de usuario y de sitio adicionales para controlar si el chat persistente está activado para usuarios y sitios específicos.
  
En este tema se presentan las siguientes secciones:
  
- Configurar la directiva global
    
- Crear una directiva de sitio
    
- Crear una directiva de usuario
    
- Aplicar una directiva a un usuario o grupo de usuarios
    
> [!NOTE] 
> El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no es compatible con Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams.](/microsoftteams/upgrade-start-here) Si necesita usar el chat persistente, puede migrar usuarios que requieran esta funcionalidad a Teams o seguir usando Skype Empresarial Server 2015.

## <a name="configure-the-global-policy"></a>Configurar la directiva global

Para configurar la directiva global:
  
1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. En el **menú Inicio,** seleccione el Panel de control de Skype Empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.
    
3. En el Panel de control de Skype Empresarial Server, haga clic en **Chat** persistente y, a continuación, haga clic en **Directiva de chat persistente.**
    
4. Haga clic en **Global** en la lista de directivas, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.
    
5. In **Editar directiva de chat persistente - Global**, haga lo siguiente: 
    
   - En **Nombre**, especifique un nombre nuevo para la directiva global, si no desea usar el nombre predeterminado (Global).
    
   - En **Descripción,** proporcione detalles sobre cuál es la directiva de usuario (por ejemplo, Directiva global para  _centralSiteName_).
    
   - Para controlar el chat persistente para todos los sitios y usuarios que no se controlan específicamente a través de una directiva de sitio o de usuario, active o desactive la casilla Habilitar **chat** persistente.
    
6. Haga clic en **Confirmar**.
    
## <a name="create-a-site-policy"></a>Crear una directiva de sitio

Para cada sitio que haya implementado, puede crear una directiva de chat persistente específica del sitio. La configuración de la directiva de sitio invalida la directiva global, pero solo en el caso del sitio específico que determina la directiva. Para crear una directiva de sitio:
  
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
    
## <a name="create-a-user-policy"></a>Crear una directiva de usuario

Puede crear directivas específicas de usuario que invalide la directiva global y las directivas de sitio a las que pertenece el usuario. Para crear una directiva de usuario:
  
1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. En el **menú Inicio,** seleccione el Panel de control de Skype Empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente** y, a continuación, en **Directiva de chat persistente**.
    
4. Haga clic en **Nuevo** y en **Directiva de usuario**.
    
5. En **Nueva directiva de chat persistente**, haga lo siguiente:
    
   - En **Nombre**, especifique un nombre para la nueva directiva de usuario.
    
   - En **Descripción,** proporcione detalles sobre la directiva de usuario (por ejemplo, directiva de chat persistente para un usuario específico).
    
   - Para controlar el chat persistente para todos los usuarios que no están controlados específicamente a través de una directiva de usuario, active o desactive la casilla Habilitar **chat** persistente.
    
6. Haga clic en **Confirmar**.
    
## <a name="apply-a-policy-to-a-user-account"></a>Aplicar una directiva a una cuenta de usuario

Después de crear directivas, puede aplicarlas a una cuenta de usuario de la siguiente manera:
  
1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. En el **menú Inicio,** seleccione el Panel de control de Skype Empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.
    
3. En la barra de navegación izquierda, haga clic en  **Usuarios** y, a continuación, busque en la cuenta de usuario que desea configurar.
    
4. En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en  **Editar** y, a continuación, en  **Mostrar detalles**.
    
5. En **Editar usuario de Skype Empresarial Server** en la directiva de chat **persistente,** seleccione la directiva de usuario de chat persistente que desee aplicar.
    
    > [!NOTE]
    > La **\<Automatic\>** configuración aplica la directiva efectiva predeterminada. Esta configuración se aplica automáticamente por el servidor.
  
6. Haga clic en **Confirmar**.
    

