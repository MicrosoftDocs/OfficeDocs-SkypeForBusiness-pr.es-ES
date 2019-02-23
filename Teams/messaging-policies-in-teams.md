---
title: Administrar directivas de mensajería
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.messagingpolicies.overview
description: Descubra más cosas sobre las directivas de mensajería y cómo se pueden usar para controlar los mensajes de chats en Teams.
ms.openlocfilehash: f1dd0fdae137e0a2a5f0baeb5b7bed08067833bf
ms.sourcegitcommit: ad126165b6440b98e550ab48e6b3491aeba9402b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "30205758"
---
# <a name="what-are-messaging-policies-in-teams"></a>¿Cuáles son las directivas de mensajería de Teams?

Messaging policies are used to control which chat and channel messaging features are available to users in Microsoft Teams. You can use the default policy that is created or create one or more custom messaging policies for people in your organization. After you create a policy, you will assign it a user or groups of users in your organization.

Las directivas se pueden administrar fácilmente en el centro de administración de Microsoft Teams (http://admin.teams.microsoft.com) , iniciar sesión con credenciales de administrador y elija **Las directivas de mensajería** en el panel de navegación izquierdo. 

![Directivas de mensajería de los equipos](media/messaging-policies-image1.png)

Para editar la directiva de mensajería predeterminado existente para su organización, haga clic en la fila **Global (valor predeterminado de toda la organización)** y, a continuación, realice los cambios. Para crear una nueva directiva personalizada de mensajería, haga clic en **nueva directiva** y seleccione su configuración. Cuando haya terminado, elija **Guardar** .

![Configuración de directiva en los equipos de mensajería](media/messaging-policies-image2.png)

<!--- Add zone marker here--->

Para cambiar la directiva de mensajería global o crear una nueva directiva personalizada, use la siguiente configuración:

- **Los propietarios pueden eliminar los mensajes enviados**  Use esta opción para permitir que los propietarios de eliminar los mensajes a los usuarios que envían en chat.
- **Los usuarios pueden eliminar los mensajes enviados** Use esta opción para permitir a los usuarios eliminar los mensajes que se envían en la conversación.
- **Los usuarios pueden editar los mensajes enviados** Use esta opción para permitir a los usuarios editar los mensajes que se envían en la conversación.
- **Confirmaciones de lectura** Use esta opción para especificar si las confirmaciones de lectura las controla el usuario, están habilitadas para todos o si, por el contrario, están deshabilitadas.
<a name="bkchat"> </a>

- **Chat** Active esta opción si desea que los usuarios de su organización puedan chatear con otras personas con la aplicación de Teams.
- **Usar imágenes Giphy en las conversaciones** Si activa esta opción, los usuarios podrán incluir imágenes Giphy en las conversaciones de chat que mantengan con otras personas. Giphy es una base de datos en línea y un motor de búsqueda que permite a los usuarios buscar y compartir archivos GIF animados. A cada Giphy se le asigna una clasificación de contenido.
- **Clasificación de contenido de Giphy** 
    - **Sin restricción** Esto significa que los usuarios podrán insertar cualquier Giphy en los chats, independientemente de la clasificación del contenido.
    - **Moderado**  Esto significa que los usuarios podrán insertar Giphys en los chats, pero se limitará moderadamente de contenido para adultos.
    - **Estricto**  Esto significa que los usuarios podrán insertar Giphys en los chats, pero se limitará estrictamente de contenido para adultos.
- **Usar Memes en las conversaciones** Si activa esta opción, los usuarios podrán incluir Memes en las conversaciones de chat que mantengan con otras personas. 
- **Usar adhesivos en las conversaciones** Si activa esta opción, los usuarios podrán incluir adhesivos en las conversaciones de chat que mantengan con otras personas.
- **Permitir vistas previas de URL** Use esta opción si desea activar o desactivar la visualización previa automática de direcciones URL en los mensajes.
- **Permitir a los usuarios traducir mensajes** Active esta opción para que los usuarios pueden traducir automáticamente los mensajes de Teams en el idioma que se especifique en su configuración de idioma personal de Office 365.

Si ha creado una directiva de mensajería personalizada, solo estará activa para un usuario cuando esa directiva se asigna al usuario. Para asignar una directiva personalizada a un usuario en el centro de administración de Microsoft Teams, elija **los usuarios** en el panel de navegación izquierdo y seleccione el usuario que desea asignar la directiva. En la página del usuario, elija **Editar** junto a **Directivas asignadas**.

<!--- End zone marker here--->

### <a name="related-topics"></a>Temas relacionados
[Directivas de reuniones en Microsoft Teams](meeting-policies-in-teams.md)
