---
title: Administrar directivas de mensajería de Teams
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
ms.openlocfilehash: 20c1354f168b5476733c95b49d3344364b8a6008
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231786"
---
# <a name="manage-messaging-policies-in-teams"></a>Administrar directivas de mensajería de Teams

<!--- Add zone marker here--->

Las directivas de mensajería se utilizan para controlar qué características de mensajería en canales y chats tienen disponibles los usuarios en Microsoft Teams. Puede usar la directiva predeterminada que se crea automáticamente o cree una o varias directivas de mensajería personalizadas para las personas de su organización. Después de crear una directiva, puede asignar a un usuario o grupo de usuarios de la organización.

De forma predeterminada, se crea una directiva con nombre Global (valor predeterminado de toda la organización). Todos los usuarios de su organización se asignará esta directiva de mensajería de forma predeterminada. Puede realizar cambios en esta directiva o crear una o varias directivas personalizadas y asignar a usuarios a ellos. Cuando se crea una directiva personalizada, puede permitir o impedir que determinadas características que están disponibles para los usuarios y, a continuación, asignarla a uno o varios usuarios que se necesitan las opciones que se aplican a ellos. 

## <a name="change-or-create-a-messaging-policy"></a>Cambiar o crear una directiva de mensajería

Puede administrar fácilmente las directivas de mensajería en el centro de administración de Microsoft Teams (http://admin.teams.microsoft.com) , inicie sesión con credenciales de administrador y selección de **las directivas de mensajería** en el panel de navegación izquierdo. Para editar el valor predeterminado existente mensajería directiva de su organización, seleccione la fila **Global (valor predeterminado de toda la organización)** y, a continuación, realice los cambios. Para crear una nueva directiva personalizada de mensajería, seleccione **nueva directiva**, dar un nombre a la nueva directiva y, a continuación, seleccione la configuración. Cuando haya terminado, elija **Guardar** .

Por ejemplo, supongamos que desea para asegurarse de que envían los mensajes no se elimina o se modifica. Debe crear una nueva directiva personalizada denominada "Conservar los mensajes enviado" y desactivar la siguiente configuración:

- Los propietarios pueden eliminar los mensajes enviados
- Los usuarios pueden eliminar los mensajes enviados
- Los usuarios pueden editar los mensajes enviados

A continuación, asigne la directiva a los usuarios.

> [!NOTE] 
> Un usuario solo se puede asignar una directiva de mensajería a la vez.
 
## <a name="assign-a-messaging-policy-to-a-user"></a>Asignar una directiva de mensajería a un usuario

Si crea una directiva personalizada de mensajería, sólo será activo para un usuario si la directiva se asigna al usuario. Para asignar una directiva personalizada a un usuario, vaya al centro de administración de Microsoft Teams, elija **los usuarios** en el panel de navegación izquierdo y seleccione el usuario que desea asignar la directiva. En la página del usuario, elija **Editar** junto a **las directivas asignadas**. A continuación, en el panel **Editar las directivas de usuario** , en **Directiva de mensajería**, seleccione la directiva de mensajería de la lista desplegable y seleccione **Guardar**. También puede editar la configuración de la lista de usuarios. Para ello, seleccione el usuario al hacer clic en a la izquierda del nombre para mostrar del usuario. Seleccione **Editar la configuración**. A continuación, en el panel **Editar configuración** , en **Directiva de mensajería**, seleccione la directiva de la lista desplegable y, a continuación, seleccione **Guardar**.

Si va a aplicar una directiva a más de un usuario, seleccione cada uno de los usuarios, haga clic en a la izquierda del nombre de usuario y, a continuación, seleccione **Editar la configuración**. En el panel **Editar configuración** , en **Directiva de mensajería**, seleccione la directiva de la lista desplegable y, a continuación, seleccione **Guardar**.

También puede asignar una directiva de mensajería a uno o varios usuarios como sigue:

1. Vaya al **Centro de administración de equipos de Microsoft** > **las directivas de mensajería**.
2. Seleccione la directiva, haga clic en a la izquierda del nombre de la directiva.
3. Seleccione **Administrar usuarios**.
4. En el panel **Administrar usuarios** , buscar el usuario por nombre para mostrar o por su nombre de usuario, seleccione el nombre y, a continuación, seleccione **Agregar**. Repita este paso para cada usuario que desee agregar.
5. Cuando haya terminado de agregar usuarios, seleccione **Guardar**.

> [!NOTE]
> No se puede eliminar una directiva si los usuarios se asignan a él. En primer lugar debe asignar una directiva diferente a todos los usuarios afectados y, a continuación, puede eliminar la directiva original.

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a>Configuración de la directiva de mensajería

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
- **Permitir a envolvente lector para la visualización de mensajes** Activar esta opción sesión en permiten a los usuarios ver los mensajes en Microsoft Reader envolvente. Lector envolvente es una herramienta de aprendizaje que proporciona una experiencia para aumentar la legibilidad del texto de lectura a pantalla completa.
- **Los usuarios pueden enviar las notificaciones de prioridad** Si desactiva esta, los usuarios pueden indicar la prioridad del mensaje.
- **Creación del mensaje de voz** 
    - **Permitido en chats y canales** Esto significa que los usuarios pueden dejar mensajes de voz en chats y canales.
    - **Permitido en chats sólo** Esto significa que los usuarios pueden dejar mensajes de voz en los chats, pero no en los canales.
    - **Deshabilitado** Esto significa que los usuarios no pueden crear mensajes de voz en chats o canales.  
- **En dispositivos móviles, Mostrar canales favoritos por encima de chats recientes** Habilite esta opción para mover canales favoritos a la parte superior de la pantalla del dispositivo móvil para que un usuario no tenga que desplazarse para encontrarlos. 
- **Permitir que un usuario para quitar usuarios de una conversación en grupo** Activar esta opción para permitir que un usuario quitar otros usuarios de una conversación en grupo. Esta característica permite continuar una conversación con un grupo más pequeño de personas sin perder el historial de chat.

### <a name="related-topics"></a>Temas relacionados
[Directivas de reuniones en Microsoft Teams](meeting-policies-in-teams.md)
