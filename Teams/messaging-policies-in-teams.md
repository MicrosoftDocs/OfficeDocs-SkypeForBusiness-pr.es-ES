---
title: Administrar directivas de mensajería de Teams
ms.author: mabond
author: mkbond007
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
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.messagingpolicies.overview
- seo-marvel-apr2020
description: Descubra más cosas sobre las directivas de mensajería y cómo se pueden usar para controlar los mensajes de chats en Teams.
ms.openlocfilehash: 1975262b6fdd404d9314c3644ebba79b6cb5bd9a
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396521"
---
# <a name="manage-messaging-policies-in-teams"></a>Administrar directivas de mensajería de Teams

<!--- Add zone marker here--->

Las directivas de mensajería se usan para controlar qué características de mensajería de canal y chat están disponibles para [los usuarios (propietarios y miembros)](assign-roles-permissions.md) de Microsoft Teams. Puede usar la directiva global (predeterminada para toda la organización) que se crea automáticamente o crear y asignar directivas de mensajería personalizadas.

Los usuarios de su organización recibirán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada. Edite la configuración de la directiva global o cree y asigne una o más directivas personalizadas para activar o desactivar las características que desee.

> [!NOTE]
> Para garantizar la sincronización después de un cambio de directiva, puede ser necesario reiniciar algunos casos. 

## <a name="create-a-custom-messaging-policy"></a>Crear una directiva de mensajería personalizada

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Directivas de mensajería**.
2. Seleccione **Agregar**.
3. Escriba un nombre y una descripción para la directiva.
4. Seleccione la configuración que quiera usar.
5. Seleccione **Guardar**.

Por ejemplo, desea asegurarse de que los mensajes enviados no se eliminen ni modifiquen. Cree una nueva directiva personalizada denominada "Conservar mensajes enviados" y desactive la siguiente configuración:

- Los propietarios pueden eliminar mensajes enviados
- Los usuarios pueden eliminar mensajes enviados
- Los usuarios pueden editar mensajes enviados

Después, asigne la directiva a los usuarios.

## <a name="edit-a-messaging-policy"></a>Editar una directiva de mensajería

Puede editar la directiva global y las directivas personalizadas que cree.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Directivas de mensajería**.
2. Haga clic a la izquierda del nombre de la directiva para seleccionarla y, luego, seleccione **Editar**.
3. A partir de aquí, realice los cambios que desee.
4. Seleccione **Guardar**.

## <a name="assign-a-custom-messaging-policy-to-users"></a>Asignar una directiva de mensajería personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

A un usuario solo se le puede asignar una directiva de mensajería a la vez.

> [!NOTE]
> No puede eliminar una directiva si tiene usuarios asignados. Primero, debe asignar una directiva diferente a todos los usuarios afectados. Luego, podrá eliminar la directiva original.

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a>Configuración de directivas de mensajería

Estas son las opciones de directiva de mensajería que puede configurar.

- **Los propietarios pueden eliminar mensajes enviados**  Use esta opción para permitir que los propietarios eliminen los mensajes del canal o las publicaciones que enviaron los usuarios.
- **Eliminar mensajes enviados** Use esta opción para permitir a los usuarios eliminar los mensajes que enviaron en el chat.
- **Eliminar chat** Use esta opción para permitir a los usuarios eliminar los mensajes que enviaron en el chat.
- **Editar mensajes enviados** Use esta opción para permitir a los usuarios editar los mensajes que enviaron en el chat.
- **Confirmaciones de lectura** Las confirmaciones de lectura permiten que el remitente de un mensaje de chat reciba una notificación cuando el destinatario leyó su mensaje en un momento determinado y chats grupales de 20 personas o menos. Las confirmaciones de lectura de mensajes quitan dudas sobre si un mensaje se ha leído y mejoran la comunicación del equipo. Las confirmaciones de lectura no se capturan en los informes de exhibición de documentos electrónicos.  
    - **Controlado por el usuario** Esto significa que los usuarios pueden decidir si quieren que las confirmaciones de lectura estén activadas o desactivadas. La configuración predeterminada dentro de la aplicación está activada. Los usuarios pueden desactivarlo.
    - **Activado para todos los usuarios** Esto significa que todos los usuarios del espacio empresarial tendrán la característica ACTIVADA sin ninguna opción para desactivarla. Al usar la opción **Activada para todos los usuarios** , la única manera de establecer recibos para todo el espacio empresarial es tener solo una directiva de mensajería para todo el inquilino (la directiva predeterminada denominada "Global (valor predeterminado para toda la organización"), o bien tener todas las directivas de mensajería en el inquilino que usen la misma configuración para los recibos. Las característica de confirmaciones de lectura es más efectiva cuando se encuentra activa como **Habilitadas para todos**.
    - **Desactivado para todos los usuarios** Esto significa que la característica está deshabilitada y nadie en el inquilino tiene confirmaciones de lectura ni puede activarla.
<a name="bkchat"> </a>

- **Chat** Active esta opción si desea que los usuarios de su organización puedan chatear con otras personas con la aplicación de Teams.
- *Usar Giphy en conversaciones** Si activa Giphy, los usuarios pueden incluir imágenes de Giphy en conversaciones de chat con otras personas. Giphy es una base de datos en línea y un motor de búsqueda que permite a los usuarios buscar y compartir archivos GIF animados. A cada Giphy se le asigna una clasificación de contenido. Además de activar esta configuración, debe habilitar [experiencias conectadas opcionales](/deployoffice/privacy/manage-privacy-controls#policy-setting-for-optional-connected-experiences) para permitir a Giphys en conversaciones.
- **Clasificación de contenido de Giphy**
  - **Sin restricción** Esto significa que los usuarios podrán insertar cualquier Giphy en los chats, independientemente de la clasificación del contenido.
  - **Moderado**  Esto significa que los usuarios podrán insertar imágenes de Giphy en los chats, pero se restringirán moderadamente al contenido para adultos.
  - **Estricto**  Esto significa que los usuarios podrán insertar Imágenes de Giphy en los chats, pero se restringirá estrictamente al contenido para adultos.
- **Memes en conversaciones** Si activa Memes, los usuarios pueden incluir memes en conversaciones de chat con otras personas.
- **Adhesivos en conversaciones** Si activa esta opción, los usuarios pueden incluir adhesivos en conversaciones de chat con otras personas.
- **Vistas previas de url** Use esta opción para activar o desactivar la vista previa automática de direcciones URL en los mensajes.
- **Traducir mensajes** Active esta opción para permitir que los usuarios traduzcan automáticamente los mensajes de Teams al idioma especificado por su configuración de idioma personal para Microsoft 365 o Office 365.
- **Lector inmersivo para mensajes** Active esta opción para permitir que los usuarios vean los mensajes en Microsoft Lector inmersivo. Lector inmersivo es una herramienta de aprendizaje que proporciona una experiencia de lectura en pantalla completa para aumentar la legibilidad del texto.
- **Enviar mensajes urgentes con notificaciones de prioridad** Si lo activa, los usuarios pueden enviar mensajes con [notificaciones de prioridad](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462). Las notificaciones de prioridad notifican a los usuarios cada 2 minutos durante 20 minutos o hasta que el destinatario recogió y lee los mensajes marcados como *urgentes* . Esta característica aumenta la probabilidad de que el mensaje se actúe de forma oportuna. No puede editar un mensaje urgente después de enviarlo.
- **Crear mensajes de voz**
  > [!Important]
  > Los mensajes de audio no se capturan en los informes de exhibición de documentos electrónicos.
  - **Permitido en chats y canales** Esto significa que los usuarios pueden dejar mensajes de audio en chats y canales.
  - **Solo se permite en chats** Esto significa que los usuarios pueden dejar mensajes de audio en chats, pero no en canales.
  - **No habilitado** Esto significa que los usuarios no pueden crear mensajes de audio en chats o canales.  
- **En dispositivos móviles, mostrar los canales favoritos encima de los chats recientes** Habilite esta configuración para mover los canales favoritos a la parte superior de la pantalla del dispositivo móvil para que un usuario no tenga que desplazarse para encontrarlos.
- **Quitar usuarios de chats grupales** Active esta opción para permitir que un usuario quite a otros usuarios de un chat grupal. Esta característica le permite continuar un chat con un grupo más pequeño de personas sin perder el historial de chats.
- **Predicciones de texto** Activa esta opción para permitir que un usuario obtenga predicciones de texto para los mensajes de chat.
- **Respuestas sugeridas**  Active esta opción para habilitar las respuestas sugeridas para los mensajes de chat.
- **Rol de permisos de chat** Use esta configuración para definir el rol de chat supervisado del usuario. Obtenga más información acerca del [chat supervisado](supervise-chats-edu.md).
- **Los usuarios con permisos de chat completos pueden eliminar cualquier mensaje** Use esta configuración para permitir que los usuarios con permisos completos eliminen cualquier mensaje de chat de grupo o reunión.
- **Mensajes de vídeo** Active esta opción si quiere que los usuarios de su organización puedan usar la aplicación Teams para enviar mensajes de vídeo a otras personas en chat.

> [!NOTE]
> Algunos de estos ajustes, como el uso de Giphys, también pueden configurarse en el nivel de equipo los propietarios del equipo y a nivel de canal privado o compartido por los propietarios de canal.

### <a name="related-topics"></a>Temas relacionados

- [Asignar directivas a usuarios y grupos en Teams](assign-policies-users-and-groups.md)
- [Asignar miembros y propietarios de equipo en Microsoft Teams](assign-roles-permissions.md)
