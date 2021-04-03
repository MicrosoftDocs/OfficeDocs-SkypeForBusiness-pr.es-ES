---
title: Administrar directivas de mensajería de Teams
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.messagingpolicies.overview
- seo-marvel-apr2020
description: Descubra más cosas sobre las directivas de mensajería y cómo se pueden usar para controlar los mensajes de chats en Teams.
ms.openlocfilehash: 800bc37ee25c073d0702c519196620faa1faf92e
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574169"
---
# <a name="manage-messaging-policies-in-teams"></a>Administrar directivas de mensajería de Teams

<!--- Add zone marker here--->

Las directivas de mensajería se usan para controlar qué características de mensajería de chat y canal están disponibles para los usuarios [(propietarios y miembros)](assign-roles-permissions.md) en Microsoft Teams. Puede usar la directiva global (predeterminada para toda la organización) que se crea automáticamente o crear y asignar directivas de mensajería personalizadas.

Los usuarios de su organización recibirán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada. Edite la configuración de la directiva global o cree y asigne una o varias directivas personalizadas para activar o desactivar las características que desee.

## <a name="create-a-custom-messaging-policy"></a>Crear una directiva de mensajería personalizada

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Directivas de mensajería.**
2. Seleccione **Agregar**.
3. Escriba un nombre y una descripción para la directiva.
4. Seleccione la configuración que quiera usar.
5. Seleccione **Guardar**.

Por ejemplo, quiere asegurarse de que los mensajes enviados no se eliminan ni se modifican. Cree una nueva directiva personalizada denominada "Conservar mensajes enviados" y desactive la siguiente configuración:

- Los propietarios pueden eliminar los mensajes enviados
- Los usuarios pueden eliminar mensajes enviados
- Los usuarios pueden editar mensajes enviados

A continuación, asigne la directiva a los usuarios.

## <a name="edit-a-messaging-policy"></a>Editar una directiva de mensajería

Puede editar la directiva global y las directivas personalizadas que cree.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Directivas de mensajería.**
2. Haga clic a la izquierda del nombre de la directiva para seleccionarla y, luego, seleccione **Editar**.
3. A partir de aquí, realice los cambios que desee.
4. Seleccione **Guardar**.

## <a name="assign-a-custom-messaging-policy-to-users"></a>Asignar una directiva de mensajería personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Solo se puede asignar una directiva de mensajería a un usuario a la vez.

> [!NOTE]
> No puede eliminar una directiva si tiene usuarios asignados. Primero, debe asignar una directiva diferente a todos los usuarios afectados. Luego, podrá eliminar la directiva original.

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a>Configuración de directiva de mensajería

Estas son las opciones de configuración de directiva de mensajería que puede configurar.

- **Los propietarios pueden eliminar los mensajes enviados**  Use esta configuración para permitir que los propietarios eliminen los mensajes que los usuarios enviaron en el chat.
- **Los usuarios pueden eliminar mensajes enviados** Use esta configuración para permitir que los usuarios eliminen los mensajes que enviaron en el chat.
- **Los usuarios pueden editar mensajes enviados** Use esta configuración para permitir a los usuarios editar los mensajes que enviaron en el chat.
- **Confirmaciones de lectura** Las confirmaciones de lectura permiten que el remitente de un mensaje de chat reciba una notificación cuando el destinatario lee el mensaje en 1:1 y los chats grupales de 20 personas o menos. Las confirmaciones de lectura de mensajes quitan de forma incierta si se ha leído un mensaje y mejoran la comunicación del equipo. Las confirmaciones de lectura no se capturan en los informes de exhibición de documentos electrónicos.  
    - **Controlado por el usuario** Esto significa que los usuarios pueden decidir si quieren recibir confirmaciones de lectura on o OFF. La configuración predeterminada dentro de la aplicación está EN. A continuación, los usuarios pueden desactivarlo.
    - **En para todos los usuarios** Esto significa que todos los usuarios del espacio empresarial tendrán la característica ON sin opción de desactivarla. Al usar  la configuración De para todos los usuarios, la única forma de establecer confirmaciones para todo el espacio empresarial es tener solo una directiva de mensajería para todo el espacio empresarial (la directiva predeterminada denominada "Global (org-wide Default)") o que todas las directivas de mensajería del inquilino usen la misma configuración para las confirmaciones. Las característica de confirmaciones de lectura es más efectiva cuando se encuentra activa como **Habilitadas para todos**.
    - **Desactivado para todos los usuarios** Esto significa que la característica está deshabilitada y que nadie del inquilino tiene confirmaciones de lectura ni puede activarla.
<a name="bkchat"> </a>

- **Chat** Active esta opción si desea que los usuarios de su organización puedan chatear con otras personas con la aplicación de Teams.
- **Usar Giphys en conversaciones**  Si activa Giphys, los usuarios pueden incluir Giphys en conversaciones de chat con otras personas. Giphy es una base de datos en línea y un motor de búsqueda que permite a los usuarios buscar y compartir archivos GIF animados. A cada Giphy se le asigna una clasificación de contenido. Además de activar esta configuración, debe habilitar [Las](/deployoffice/privacy/manage-privacy-controls#policy-setting-for-optional-connected-experiences) experiencias conectadas opcionales para permitir giphys en las conversaciones.
- **Clasificación de contenido gipsy**
    - **Sin restricciones** Esto significa que los usuarios podrán insertar cualquier giphy en los chats independientemente de la clasificación de contenido.
    - **Moderado**  Esto significa que los usuarios podrán insertar Giphys en chats, pero estarán moderadamente restringidos del contenido adulto.
    - **Estricto**  Esto significa que los usuarios podrán insertar Giphys en chats, pero estarán estrictamente restringidos al contenido de adultos.
- **Usar memes en conversaciones** Si activa Memes, los usuarios pueden incluir Memes en conversaciones de chat con otras personas.
- **Usar adhesivos en conversaciones. Si activa esta opción, los usuarios pueden incluir adhesivos en conversaciones de chat con otras personas.
- **Permitir vistas previas de URL** Use esta opción si desea activar o desactivar la visualización previa automática de direcciones URL en los mensajes.
- **Permitir que los usuarios traduzcan mensajes** Active esta configuración para permitir que los usuarios traduzcan automáticamente los mensajes de Teams al idioma especificado por su configuración de idioma personal para Microsoft 365 u Office 365.
- **Permitir lector inmersivo para ver mensajes** Active esta configuración para permitir que los usuarios puedan ver mensajes en Microsoft Immersive Reader. Lector inmersivo es una herramienta de aprendizaje que proporciona una experiencia de lectura en pantalla completa para aumentar la legibilidad del texto.
- **Enviar mensajes urgentes con notificaciones de prioridad** Si activa esta opción, los usuarios pueden enviar mensajes con notificaciones [de prioridad.](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462) Las notificaciones de prioridad notifican a los usuarios cada 2  minutos durante 20 minutos o hasta que los mensajes marcados como urgentes sean recogidos y leídos por el destinatario. Esta característica aumenta la probabilidad de que el mensaje se actúe de forma oportuna.
- **Creación de mensajes de audio**
  > [!Important]
  > Los mensajes de audio no se capturan en los informes de exhibición de documentos electrónicos.
    - **Permitido en chats y canales** Esto significa que los usuarios pueden dejar mensajes de audio en chats y canales.
    - **Permitido solo en chats** Esto significa que los usuarios pueden dejar mensajes de audio en chats, pero no en canales.
    - **Deshabilitado** Esto significa que los usuarios no pueden crear mensajes de audio en chats o canales.  
- **En dispositivos móviles, mostrar canales favoritos por encima de chats recientes** Habilite esta configuración para mover los canales favoritos a la parte superior de la pantalla del dispositivo móvil para que un usuario no tenga que desplazarse para encontrarlos.
- **Permitir que un usuario quite usuarios de un chat grupal** Active esta configuración para permitir que un usuario quite otros usuarios de un chat grupal. Esta característica te permite continuar un chat con un grupo más pequeño de personas sin perder el historial de chats.
- **Habilitar respuestas sugeridas**  Active esta configuración para habilitar las respuestas sugeridas para los mensajes de chat.
- **Rol de permisos de chat** Use esta configuración para definir el rol de chat supervisado del usuario.  Obtenga más información sobre [el chat supervisado.](supervise-chats-edu.md)

> [!NOTE]
> Algunos de estos ajustes, como giphys, también se pueden configurar en el nivel de equipo por los propietarios del equipo y en el nivel de canal privado por los propietarios de canales privados.

### <a name="related-topics"></a>Temas relacionados

- [Asignar directivas a usuarios y grupos en Teams](assign-policies-users-and-groups.md)
- [Asignar miembros y propietarios de equipo en Microsoft Teams](assign-roles-permissions.md)
