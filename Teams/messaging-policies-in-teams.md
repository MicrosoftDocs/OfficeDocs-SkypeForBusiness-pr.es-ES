---
title: ¿Cuáles son las directivas de mensajería de Teams?
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
description: Obtenga información sobre las directivas de mensajería y cómo se pueden usar para controlar el chat de mensajería en los equipos.
ms.openlocfilehash: 203acb58113d162e6752ca5d327b8575c58a7133
ms.sourcegitcommit: f091c351bec56219a8c91b8c12b9c1f5c5983c95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2019
ms.locfileid: "29530939"
---
# <a name="what-are-messaging-policies-in-teams"></a>¿Cuáles son las directivas de mensajería de Teams?

Las directivas de mensajería se usan para controlar qué chat y canal de características de mensajería están disponibles para los usuarios de Microsoft Teams. Puede usar la directiva predeterminada que se crea o cree una o varias directivas de mensajería personalizadas para las personas de su organización. Después de crear una directiva, se le asignará un usuario o grupos de usuarios en la organización.

Las directivas se pueden administrar fácilmente en el centro de administración de equipos (http://admin.teams.microsoft.com) iniciar sesión con credenciales de administrador y haciendo clic en **Las directivas de mensajería** en el panel de navegación izquierdo. Para editar la directiva predeterminada existente para su organización, seleccione la fila **Global (valor predeterminado de toda la organización)** y haga clic en **Editar**. Para crear una nueva directiva de mensajería, haga clic en **nueva directiva**.

![Directivas de mensajería de los equipos](media/messaging-policies.png)

La configuración disponible para la directiva se describe a continuación: 

- **Los propietarios pueden eliminar los mensajes enviados**  Use esta opción para permitir que los propietarios de eliminar los mensajes que envían los usuarios de chat.
- **Los usuarios pueden eliminar los mensajes enviados** Use esta opción para permitir a los usuarios eliminar los mensajes que envían de chat.
- **Los usuarios pueden editar los mensajes enviados** Use esta opción para permitir a los usuarios editar los mensajes que se envían en la conversación.
- **Confirmaciones de lectura** Utilice esta opción para especificar si confirmaciones de lectura se usuario controlado, habilitado para todos los usuarios o deshabilitado.
<a name="bkchat"> </a>

- **Conversaciones**  Activar esta opción si desea que los usuarios de la organización puedan usar la aplicación de los equipos para charlar con otras personas.
- **Uso de Giphys en las conversaciones**  Si desactiva esta, los usuarios pueden incluir Giphys en las conversaciones de chat con otras personas. Giphy es una base de datos en línea y el motor de búsqueda que permite a los usuarios buscar y compartir los archivos GIF animados. Cada Giphy se le asigna una clasificación de contenido.
- **Clasificación de contenido Giphy** 
    - **Sin restricción** Esto significa que los usuarios podrán insertar todos los Giphys en los chats, independientemente de la clasificación del contenido.
    - **Moderado**  Esto significa que los usuarios podrán insertar Giphys en chats pero restringirá moderadamente de contenido para adultos.
    - **Estricto**  Esto significa que los usuarios podrán insertar Giphys en chats pero se limitará estrictamente de contenido para adultos.
- **Uso de Memes en las conversaciones** Si desactiva esta, los usuarios pueden incluir Memes en las conversaciones de chat con otras personas. 
- **Pegatinas de uso en las conversaciones** Si desactiva esta, los usuarios pueden incluir pegatinas en las conversaciones de chat con otras personas.
- **Vistas previas de permitir la dirección URL** Use esta opción para activar automática dirección URL obtener una vista previa o desactiva en los mensajes.
- **Permitir a los usuarios para traducir los mensajes** Activar esta opción para permitir que los usuarios traducir automáticamente los mensajes de los equipos en el idioma especificado por su configuración personal de idioma para Office 365.

Si ha creado una directiva personalizada de mensajería, sólo estará activo para un usuario si esa directiva se asigna a un usuario.  Para asignar una directiva personalizada a un usuario en el centro de administración de equipos, haga clic en **usuarios** en el panel de navegación izquierdo, seleccione el usuario que desea asignar la directiva y, a continuación, elija **Editar** bajo **Directivas asignadas**.

### <a name="related-topics"></a>Temas relacionados
[Directivas de reuniones en Microsoft Teams](meeting-policies-in-teams.md)