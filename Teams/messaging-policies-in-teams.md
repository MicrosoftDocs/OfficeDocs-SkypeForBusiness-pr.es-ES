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
description: Descubra más cosas sobre las directivas de mensajería y cómo se pueden usar para controlar los mensajes de chats en Teams.
ms.openlocfilehash: 203acb58113d162e6752ca5d327b8575c58a7133
ms.sourcegitcommit: f091c351bec56219a8c91b8c12b9c1f5c5983c95
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2019
ms.locfileid: "29530939"
---
# <a name="what-are-messaging-policies-in-teams"></a>¿Cuáles son las directivas de mensajería de Teams?

Las directivas de mensajería se utilizan para controlar qué características de mensajería en canales y chats tienen disponibles los usuarios en Microsoft Teams. Se puede usar la directiva predeterminada que ya hay o bien crear una nueva o más directivas de mensajería personalizadas para los miembros de su organización. Después de crear una directiva, tendrá que asignarla a un usuario o grupos de usuarios de la organización.

Las directivas se administran fácilmente en el Centro de administración de Teams (http://admin.teams.microsoft.com) iniciando sesión con las credenciales de administrador y haciendo clic en **Directivas de mensajería** en el panel de navegación izquierdo). Para editar la directiva predeterminada actual de su organización, seleccione la fila **Global (configuración predeterminada para toda la organización)** y haga clic en **Editar**. Para crear una directiva de mensajería nueva, haga clic en **Nueva directiva**.

![Directivas de mensajería en Teams](media/messaging-policies.png)

A continuación se describe la configuración disponible para la directiva: 

- **Los propietarios pueden eliminar los mensajes enviados** Use esta opción para permitir que los propietarios eliminen los mensajes que envían los usuarios en un chat.
- **Los usuarios pueden eliminar los mensajes enviados** Use esta opción para permitir que los usuarios eliminen los mensajes que envían en un chat.
- **Los usuarios pueden editar los mensajes enviados** Use esta opción para permitir que los usuarios editen los mensajes que envían en un chat.
- **Confirmaciones de lectura** Use esta opción para especificar si las confirmaciones de lectura las controla el usuario, están habilitadas para todos o si, por el contrario, están deshabilitadas.
<a name="bkchat"> </a>

- **Chat** Active esta opción si desea que los usuarios de su organización puedan chatear con otras personas con la aplicación de Teams.
- **Usar imágenes Giphy en las conversaciones** Si activa esta opción, los usuarios podrán incluir imágenes Giphy en las conversaciones de chat que mantengan con otras personas. Giphy es una base de datos en línea y un motor de búsqueda que permite a los usuarios buscar y compartir archivos GIF animados. A cada Giphy se le asigna una clasificación de contenido.
- **Clasificación de contenido de Giphy** 
    - **Sin restricción** Indica que los usuarios pueden insertar todas las imágenes Giphy en los chats, independientemente de la clasificación de contenido que tengan.
    - **Moderado** Indica que los usuarios pueden insertar imágenes Giphy en los chats, pero el contenido para adultos estará restringido de forma moderada.
    - **Estricto** Indica que los usuarios pueden insertar imágenes Giphy en los chats, pero el contenido para adultos estará restringido de forma estricta.
- **Usar Memes en las conversaciones** Si activa esta opción, los usuarios podrán incluir Memes en las conversaciones de chat que mantengan con otras personas. 
- **Usar adhesivos en las conversaciones** Si activa esta opción, los usuarios podrán incluir adhesivos en las conversaciones de chat que mantengan con otras personas.
- **Permitir vistas previas de URL** Use esta opción si desea activar o desactivar la visualización previa automática de direcciones URL en los mensajes.
- **Permitir a los usuarios traducir mensajes** Active esta opción para que los usuarios pueden traducir automáticamente los mensajes de Teams en el idioma que se especifique en su configuración de idioma personal de Office 365.

Si ha creado una directiva de mensajería personalizada, solo estará activa para un usuario cuando esa directiva se asigna al usuario.  Para asignar una directiva personalizada a un usuario en el Centro de administración de Teams, haga clic en **Usuarios** en el panel de navegación izquierdo, seleccione el usuario al que quiere asignar la directiva y, a continuación, elija **Editar** en **Directivas asignadas**.

### <a name="related-topics"></a>Temas relacionados
[Directivas de reuniones en Microsoft Teams](meeting-policies-in-teams.md)