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
description: En este artículo, aprenderá sobre las directivas de mensajería y cómo se pueden usar para controlar la mensajería de chat en Teams.
ms.openlocfilehash: 050f072a2148be909dbaabd4ac8ab53c1e5bb298
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611664"
---
# <a name="manage-messaging-policies-in-teams"></a>Administrar directivas de mensajería de Teams

<!--- Add zone marker here--->

Las directivas de mensajería se usan para controlar qué características de mensajería de canal y chat están disponibles para los usuarios [(propietarios y miembros)](assign-roles-permissions.md) de Microsoft Teams. Puede usar la directiva global (predeterminada para toda la organización) que se crea automáticamente o crear y asignar directivas de mensajería personalizadas.

Los usuarios de su organización obtendrán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada. Puede editar la configuración de la directiva global o crear y asignar una o varias directivas personalizadas para activar o desactivar las características que desee.

## <a name="create-a-custom-messaging-policy"></a>Crear una directiva de mensajería personalizada

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Directivas **de mensajería.**
2. Haga clic en **Agregar**.
3. Escriba un nombre y una descripción para la directiva.
4. Seleccione la configuración que quiera usar.
5. Haga clic en **Guardar**.

Por ejemplo, digamos que quiere asegurarse de que los mensajes enviados no se eliminan o se modifican. Cree una nueva directiva personalizada denominada "Conservar mensajes enviados" y desactive la siguiente configuración:

- Los propietarios pueden eliminar los mensajes enviados
- Los usuarios pueden eliminar los mensajes enviados
- Los usuarios pueden editar los mensajes enviados

Después, asigne la directiva a los usuarios.

## <a name="edit-a-messaging-policy"></a>Editar una directiva de mensajería

Puede editar la directiva global y las directivas personalizadas que cree. 

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Directivas de mensajería.**
2. Haga clic a la izquierda del nombre de la directiva para seleccionarla y, luego, en **Editar**.
3. A partir de aquí, realice los cambios que desee.
4. Haga clic en **Guardar**.

## <a name="assign-a-custom-messaging-policy-to-users"></a>Asignar una directiva de mensajería personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

A un usuario solo se le puede asignar una directiva de mensajería a la vez.

> [!NOTE]
> No puede eliminar una directiva si tiene usuarios asignados. Primero, debe asignar una directiva diferente a todos los usuarios afectados. Luego, podrá eliminar la directiva original.

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a>Configuración de directiva de mensajería

Estas son las opciones de configuración de directivas de mensajería que puede configurar.

- **Los propietarios pueden eliminar los mensajes enviados**  Use esta opción para permitir que los propietarios eliminen los mensajes enviados por los usuarios en un chat.
- **Los usuarios pueden eliminar los mensajes enviados** Use esta opción para permitir que los usuarios eliminen los mensajes que enviaron en un chat.
- **Los usuarios pueden editar los mensajes enviados** Use esta opción para permitir a los usuarios editar los mensajes que enviaron en un chat.
- **Confirmaciones de lectura** Las confirmaciones de lectura permiten al remitente de un mensaje de chat recibir una notificación cuando el destinatario lee su mensaje en chats grupales de 20 personas o menos. Las confirmaciones de lectura de mensajes quitan de forma no segura si un mensaje se ha leído y mejoran la comunicación del equipo. Tenga en cuenta que las confirmaciones de lectura no se capturan en los informes de exhibición de documentos electrónicos.  
    - **Controlado por el usuario** Esto significa que los usuarios deciden si quieren tener confirmaciones de lectura o desactivadas. La configuración predeterminada dentro de la aplicación está on. Los usuarios pueden desactivarlo.
    - **En uso para todos los usuarios** Esto significa que todos los usuarios del inquilino tendrán la característica on sin opción para desactivarla. Tenga en cuenta  que, al usar la configuración "On" para todos los usuarios, la única forma de establecer confirmaciones para todo el espacio empresarial es tener una sola directiva de mensajería para todo el inquilino (la directiva predeterminada denominada "Global (predeterminado para toda la organización)" o que todas las directivas de mensajería del inquilino usen la misma configuración para los recibos. La característica de confirmaciones de lectura es más eficaz cuando la característica está habilitada para **activarse para todos los usuarios.**
    - **Desactivado para todos los usuarios** Esto significa que la característica está deshabilitada y nadie en el inquilino tiene confirmaciones de lectura ni pueden activarla.
<a name="bkchat"> </a>

- **Chat** Active esta opción si desea que los usuarios de su organización puedan chatear con otras personas con la aplicación de Teams.
- **Usar imágenes Giphy en las conversaciones** Si activa esta opción, los usuarios podrán incluir imágenes Giphy en las conversaciones de chat que mantengan con otras personas. Giphy es una base de datos en línea y un motor de búsqueda que permite a los usuarios buscar y compartir archivos GIF animados. A cada Giphy se le asigna una clasificación de contenido. Tenga en cuenta que, además de activar esta [](https://docs.microsoft.com/deployoffice/privacy/manage-privacy-controls#policy-setting-for-optional-connected-experiences) configuración, también debe habilitar las experiencias conectadas opcionales para permitir imágenes de Giphy en conversaciones.
- **Clasificación de contenido de Giphy**
    - **Sin restricciones** Esto significa que los usuarios podrán insertar imágenes de Giphy en los chats independientemente de la clasificación de contenido.
    - **Moderada**  Esto significa que los usuarios podrán insertar imágenes de Giphy en los chats, pero se restringirá de forma moderada al contenido para adultos.
    - **Estricto**  Esto significa que los usuarios podrán insertar imágenes de Giphy en los chats, pero se restringirá estrictamente al contenido para adultos.
- **Usar Memes en las conversaciones** Si activa esta opción, los usuarios podrán incluir Memes en las conversaciones de chat que mantengan con otras personas.
- **Usar adhesivos en las conversaciones** Si activa esta opción, los usuarios podrán incluir adhesivos en las conversaciones de chat que mantengan con otras personas.
- **Permitir vistas previas de URL** Use esta opción si desea activar o desactivar la visualización previa automática de direcciones URL en los mensajes.
- **Permitir que los usuarios traduzcan mensajes** Active esta configuración para permitir que los usuarios traduzcan automáticamente los mensajes de Teams al idioma especificado en su configuración de idioma personal para Microsoft 365 u Office 365.
- **Permitir que el lector inmersivo pueda ver mensajes** Active esta configuración para permitir que los usuarios puedan ver los mensajes en Lector inmersivo de Microsoft. Lector inmersivo es una herramienta de aprendizaje que ofrece una experiencia de lectura en pantalla completa para aumentar la legibilidad del texto.
- **Enviar mensajes urgentes con notificaciones de prioridad** Si activa esta opción, los usuarios pueden enviar mensajes con [notificaciones de prioridad.](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462) Las notificaciones de prioridad notifican a los usuarios cada 2 minutos  durante un período de 20 minutos o hasta que el destinatario resalte y lea los mensajes marcados como urgentes, lo que aumenta la probabilidad de que el mensaje se ate parte de su tiempo.
- **Creación de mensajes de audio** 
  > [!Important]
  > Los mensajes de audio no se capturan en los informes de exhibición de documentos electrónicos.
    - **Permitido en chats y canales** Esto significa que los usuarios pueden dejar mensajes de audio tanto en chats como en canales.
    - **Permitido solo en chats** Esto significa que los usuarios pueden dejar mensajes de audio en chats, pero no en canales.
    - **Deshabilitado** Esto significa que los usuarios no pueden crear mensajes de audio en chats o canales.  
- **En dispositivos móviles, mostrar canales favoritos encima de chats recientes** Habilite esta opción para mover los canales favoritos a la parte superior de la pantalla del dispositivo móvil para que un usuario no tenga que desplazarse para encontrarlos.
- **Permitir que un usuario quite usuarios de un chat grupal** Active esta opción para permitir que un usuario quite a otros usuarios de un chat grupal. Esta característica le permite continuar un chat con un grupo más reducido de personas sin perder el historial de chats.
- **Habilitar respuestas sugeridas**  Active esta opción para habilitar las respuestas sugeridas para los mensajes de chat.

> [!NOTE]
> Algunos de estos parámetros, como giphy, también se pueden configurar en el nivel del equipo por los propietarios de equipos y en el nivel de canal privado por los propietarios de canal privado.

### <a name="related-topics"></a>Temas relacionados

- [Asignar directivas a los usuarios en Teams](assign-policies.md)
- [Asignar miembros y propietarios de equipo en Microsoft Teams](assign-roles-permissions.md)
