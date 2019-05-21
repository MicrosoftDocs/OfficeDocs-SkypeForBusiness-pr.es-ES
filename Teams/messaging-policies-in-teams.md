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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.messagingpolicies.overview
description: Descubra más cosas sobre las directivas de mensajería y cómo se pueden usar para controlar los mensajes de chats en Teams.
ms.openlocfilehash: 74baed2a51f1a03ee29238da1795c67601e30ae0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298061"
---
# <a name="manage-messaging-policies-in-teams"></a>Administrar directivas de mensajería de Teams

<!--- Add zone marker here--->

Las directivas de mensajería se utilizan para controlar qué características de mensajería en canales y chats tienen disponibles los usuarios en Microsoft Teams. Puede usar la directiva predeterminada que se crea automáticamente o crear una o más directivas de mensajería personalizadas para los usuarios de su organización. Después de crear una directiva, puede asignarla a un usuario o a un grupo de usuarios de su organización.

De forma predeterminada, se crea una directiva denominada global (opción predeterminada para toda la organización). A todos los usuarios de su organización se les asignará esta directiva de mensajería de forma predeterminada. Puede realizar cambios en esta Directiva o crear una o más directivas personalizadas y asignarles usuarios. Al crear una directiva personalizada, puede permitir o impedir que determinadas características estén disponibles para los usuarios y, después, asignarlas a uno o más usuarios que necesiten la configuración que se les aplicará. 

## <a name="change-or-create-a-messaging-policy"></a>Cambiar o crear una directiva de mensajería

Puede administrar fácilmente directivas de mensajería en el centro de administración de Microsofthttp://admin.teams.microsoft.com) Teams (iniciando sesión con credenciales de administrador y seleccionando **directivas de mensajería** en el panel de navegación izquierdo). Para editar la Directiva de mensajería predeterminada existente para su organización, seleccione la fila **global (predeterminada para toda** la organización) y, a continuación, realice los cambios. Para crear una nueva Directiva de mensajería personalizada, seleccione **nueva Directiva**, asigne un nombre a la nueva Directiva y, a continuación, seleccione la configuración. Elija **Guardar** cuando haya terminado.

Por ejemplo, supongamos que desea asegurarse de que los mensajes enviados no se eliminen ni modifiquen. Debería crear una nueva directiva personalizada denominada "retener mensajes enviados" y desactivar la configuración siguiente:

- Los propietarios pueden eliminar los mensajes enviados
- Los usuarios pueden eliminar mensajes enviados
- Los usuarios pueden editar mensajes enviados

A continuación, asigne la Directiva a los usuarios.

> [!NOTE] 
> Un usuario solo puede tener asignada una directiva de mensajería a la vez.
 
## <a name="assign-a-messaging-policy-to-a-user"></a>Asignar una directiva de mensajería a un usuario

Si crea una directiva de mensajería personalizada, solo estará activa para un usuario si la Directiva está asignada al usuario. Para asignar una directiva personalizada a un usuario, vaya al centro de administración de Microsoft Teams, elija **usuarios** en el panel de navegación izquierdo y seleccione el usuario al que desea asignar la Directiva. En la página del usuario, elija **Editar** junto a **directivas asignadas**. Después, en el panel **editar directivas de usuario** , en **Directiva de mensajería**, seleccione la Directiva de mensajería de la lista desplegable y, después, haga clic en **Guardar**. También puede editar la configuración de la lista de usuarios. Para ello, seleccione el usuario haciendo clic a la izquierda del nombre para mostrar del usuario. Seleccione **Editar configuración**. Después, en el panel **Editar configuración** , en **Directiva de mensajería**, seleccione la Directiva en la lista desplegable y, a continuación, seleccione **Guardar**.

Si está aplicando una directiva a más de un usuario, seleccione cada uno de los usuarios haciendo clic a la izquierda del nombre de usuario y, a continuación, seleccione **Editar configuración**. En el panel **Editar configuración** , en **Directiva de mensajería**, seleccione la Directiva en la lista desplegable y, a continuación, seleccione **Guardar**.

También puede asignar una directiva de mensajería a uno o más usuarios de la siguiente manera:

1. Vaya a > **las directivas de mensajería**del **centro de administración de Microsoft Teams**.
2. Seleccione la Directiva haciendo clic a la izquierda del nombre de la Directiva.
3. Seleccione **administrar usuarios**.
4. En el panel **administrar usuarios** , busque el usuario por nombre para mostrar o por nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**. Repita este paso para cada usuario que desee agregar.
5. Cuando haya terminado de agregar usuarios, seleccione **Guardar**.

> [!NOTE]
> No puede eliminar una Directiva si los usuarios están asignados a ella. Primero debe asignar una directiva diferente a todos los usuarios afectados y, después, puede eliminar la directiva original.

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a>Configuración de la Directiva de mensajería

Use la siguiente configuración para cambiar la Directiva de mensajería global o crear una nueva directiva personalizada:

- **Los propietarios pueden eliminar los mensajes enviados**  Use esta configuración para permitir a los propietarios eliminar los mensajes que los usuarios han enviado en el chat.
- **Los usuarios pueden eliminar mensajes enviados** Use esta configuración para permitir a los usuarios eliminar los mensajes que enviaron en la conversación.
- **Los usuarios pueden editar mensajes enviados** Use esta configuración para permitir a los usuarios editar los mensajes que enviaron en la conversación.
- **Confirmaciones de lectura** Use esta opción para especificar si las confirmaciones de lectura las controla el usuario, están habilitadas para todos o si, por el contrario, están deshabilitadas.
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
- **Permitir a los usuarios traducir mensajes** Active esta opción para que los usuarios pueden traducir automáticamente los mensajes de Teams en el idioma que se especifique en su configuración de idioma personal de Office 365.
- **Permitir el lector inmersivo para ver mensajes** Active esta opción para permitir a los usuarios ver los mensajes en Microsoft inmersivo Reader. El lector inmersivo es una herramienta de aprendizaje que proporciona una experiencia de lectura de pantalla completa para aumentar la legibilidad del texto.
- **Los usuarios pueden enviar notificaciones prioritarias** Si activa esta opción, los usuarios pueden enviar un mensaje que usa notificaciones de prioridad. Las notificaciones prioritarias notifican a los usuarios varias veces durante un período de 20 minutos o hasta que el destinatario recoja y lea los mensajes, maximizando la probabilidad de que el mensaje se recoja y esté accionado de manera oportuna.
- **Creación de mensajes de voz** 
    - **Permitido en chats y canales** Esto significa que los usuarios pueden dejar mensajes de voz en los chats y en los canales.
    - **Permitido solo en chats** Esto significa que los usuarios pueden dejar mensajes de voz en los chats, pero no en los canales.
    - **** Desactivado Esto significa que los usuarios no pueden crear mensajes de voz en los chats ni en los canales.  
- **En dispositivos móviles, Mostrar canales favoritos por encima de los chats recientes** Habilite esta opción para mover los canales favoritos a la parte superior de la pantalla del dispositivo móvil para que el usuario no tenga que desplazarse para encontrarlos. 
- **Permitir a un usuario quitar usuarios de un chat grupal** Activa esta opción para permitir a un usuario quitar a otros usuarios de un chat grupal. Esta característica te permite continuar con un chat con un grupo más pequeño de personas sin perder el historial de conversaciones.

### <a name="related-topics"></a>Temas relacionados
[Directivas de reuniones en Microsoft Teams](meeting-policies-in-teams.md)
