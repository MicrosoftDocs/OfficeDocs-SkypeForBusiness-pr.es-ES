---
title: Administrar directivas de mensajería de Teams
ms.author: lolaj
author: lolajacobsen
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
description: En este artículo, obtendrá información sobre las directivas de mensajería y sobre cómo se pueden usar para controlar la mensajería de chat en Teams.
ms.openlocfilehash: c29697c8ec4d235ed232616e34590351bea59e9e
ms.sourcegitcommit: 2467ece95e100a3a3cc2be3538d8eb7d878b3663
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2020
ms.locfileid: "45042982"
---
# <a name="manage-messaging-policies-in-teams"></a>Administrar directivas de mensajería de Teams

<!--- Add zone marker here--->

Las directivas de mensajería se utilizan para controlar qué características de mensajería en canales y chats tienen disponibles los usuarios en Microsoft Teams. Puede usar la directiva global (predeterminada para toda la organización) que se crea automáticamente o crear y asignar directivas de mensajería personalizadas.

Los usuarios de su organización obtendrán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada. Puede editar la configuración en la directiva global o crear y asignar una o más directivas personalizadas para activar o desactivar las características que desee.

## <a name="create-a-custom-messaging-policy"></a>Crear una directiva de mensajería personalizada

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **directivas de mensajería**.
2. Haga clic en **Agregar**.
3. Escriba un nombre y una descripción para la directiva.
4. Elija la configuración que desee.
5. Haga clic en **Guardar **.

Por ejemplo, supongamos que desea asegurarse de que los mensajes enviados no se eliminen ni modifiquen. Cree una nueva directiva personalizada denominada "reenviar mensajes enviados" y desactive la configuración siguiente:

- Los propietarios pueden eliminar los mensajes enviados
- Los usuarios pueden eliminar mensajes enviados
- Los usuarios pueden editar mensajes enviados

A continuación, asigne la Directiva a los usuarios.

## <a name="edit-a-messaging-policy"></a>Editar una directiva de mensajería

Puede editar la directiva global en cualquier directiva personalizada que cree. 

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **directivas de mensajería**.
2. Seleccione la Directiva haciendo clic a la izquierda del nombre de la Directiva y, a continuación, haga clic en **Editar**.
3. Desde aquí, realice los cambios que desee.
4. Haga clic en **Guardar **.

## <a name="assign-a-custom-messaging-policy-to-users"></a>Asignar una directiva de mensajería personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Un usuario solo puede tener asignada una directiva de mensajería a la vez.

> [!NOTE]
> No puede eliminar una Directiva si los usuarios están asignados a ella. Primero debe asignar una directiva diferente a todos los usuarios afectados y, después, puede eliminar la directiva original.

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a>Configuración de la Directiva de mensajería

Estos son los valores de configuración de la Directiva de mensajería que puede configurar.

- **Los propietarios pueden eliminar los mensajes enviados**  Use esta configuración para permitir a los propietarios eliminar los mensajes que los usuarios han enviado en el chat.
- **Los usuarios pueden eliminar mensajes enviados** Use esta configuración para permitir a los usuarios eliminar los mensajes que enviaron en la conversación.
- **Los usuarios pueden editar mensajes enviados** Use esta configuración para permitir a los usuarios editar los mensajes que enviaron en la conversación.
- **Confirmaciones de lectura** Las confirmaciones de lectura permiten notificar al remitente de un mensaje de chat cuando el destinatario ha leído su mensaje en 1:1 y los chats grupales son de 20 personas o menos. Las confirmaciones de lectura de mensajes no eliminan con certeza si se leyó un mensaje y mejoran la comunicación entre equipos. Tenga en cuenta que las confirmaciones de lectura no se capturan en informes de eDiscovery.  
    - **Controlado** por el usuario Esto significa que los usuarios pueden decidir si desean activar o desactivar las confirmaciones de lectura. La configuración predeterminada dentro de la aplicación está activada. Los usuarios pueden desactivarlo.
    - **Activado para todos** Esto significa que todos los miembros del inquilino tendrán la característica activada, sin opción para desactivarla. Tenga en cuenta que al usar la configuración **activado para todos** , la única forma de establecer confirmaciones para todo el inquilino es que solo tenga una directiva de mensajería para todo el inquilino (la directiva predeterminada denominada "global (valor predeterminado de toda la organización)") o para que todas las directivas de mensajería del inquilino usen la misma configuración para las confirmaciones. La característica confirmaciones de lectura es más eficaz cuando la característica está habilitada para **todos los usuarios**.
    - **Deshabilitado para todos** Esto significa que la característica está deshabilitada y que nadie en el inquilino tiene confirmaciones de lectura, ni puede activarlas.
<a name="bkchat"> </a>

- **Chat** Active esta opción si desea que los usuarios de su organización puedan chatear con otras personas con la aplicación de Teams.
- **Usar imágenes Giphy en las conversaciones** Si activa esta opción, los usuarios podrán incluir imágenes Giphy en las conversaciones de chat que mantengan con otras personas. Giphy es una base de datos en línea y un motor de búsqueda que permite a los usuarios buscar y compartir archivos GIF animados. A cada Giphy se le asigna una clasificación de contenido.
- **Clasificación de contenido de Giphy**
    - **Sin restricción** Esto significa que tus usuarios podrán insertar cualquier Giphy en los chats, independientemente de la clasificación de contenido.
    - **Moderado**  Esto significa que tus usuarios podrán insertar imágenes giphy en los chats, pero estarán moderadamente restringidos de contenido para adultos.
    - **Estricto**  Esto significa que tus usuarios podrán insertar imágenes giphy en los chats, pero estarán estrictamente restringidos de contenido para adultos.
- **Usar Memes en las conversaciones** Si activa esta opción, los usuarios podrán incluir Memes en las conversaciones de chat que mantengan con otras personas.
- **Usar adhesivos en las conversaciones** Si activa esta opción, los usuarios podrán incluir adhesivos en las conversaciones de chat que mantengan con otras personas.
- **Permitir vistas previas de URL** Use esta opción si desea activar o desactivar la visualización previa automática de direcciones URL en los mensajes.
- **Permitir que los usuarios traduzcan mensajes** Active esta opción para permitir que los usuarios traduzcan automáticamente los mensajes de los equipos al idioma especificado por la configuración de Idioma personal de Microsoft 365 u Office 365.
- **Permitir el lector inmersivo para ver mensajes** Active esta opción para permitir a los usuarios ver los mensajes en Microsoft inmersivo Reader. El lector inmersivo es una herramienta de aprendizaje que proporciona una experiencia de lectura de pantalla completa para aumentar la legibilidad del texto.
- **Enviar mensajes urgentes con notificaciones prioritarias** Si activa esta opción, los usuarios pueden enviar mensajes con las [notificaciones de prioridad](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462). Las notificaciones prioritarias notifican a los usuarios cada 2 minutos por un período de 20 minutos o hasta que el destinatario retoma y Lee los mensajes marcados como *urgentes* , lo que maximiza la probabilidad de que el mensaje se encuentre en forma oportuna.
- **Creación de mensajes de audio** 
  > [!Important]
  > Los mensajes de audio no se capturan en informes de eDiscovery.
    - **Permitido en chats y canales** Esto significa que los usuarios pueden dejar mensajes de audio en los chats y en los canales.
    - **Permitido solo en chats** Esto significa que los usuarios pueden dejar mensajes de audio en los chats, pero no en los canales.
    - **Desactivado** Esto significa que los usuarios no pueden crear mensajes de audio en los chats o canales.  
- **En dispositivos móviles, Mostrar canales favoritos por encima de los chats recientes** Habilite esta opción para mover los canales favoritos a la parte superior de la pantalla del dispositivo móvil para que el usuario no tenga que desplazarse para encontrarlos.
- **Permitir a un usuario quitar usuarios de un chat grupal** Activa esta opción para permitir a un usuario quitar a otros usuarios de un chat grupal. Esta característica te permite continuar con un chat con un grupo más pequeño de personas sin perder el historial de conversaciones.
- **Habilitar las respuestas sugeridas**  Activa esta opción para habilitar las respuestas sugeridas para los mensajes instantáneos.

> [!NOTE]
> Algunas de estas opciones de configuración, como imágenes giphy, también se pueden configurar en el nivel de equipo por parte de los propietarios del equipo y en el nivel del canal privado por los propietarios del canal privado.

### <a name="related-topics"></a>Temas relacionados

- [Asignar directivas a los usuarios de Teams](assign-policies.md)
