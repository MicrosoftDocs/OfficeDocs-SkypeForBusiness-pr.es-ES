---
title: Administrar directivas de reunión
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.date: 03/22/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
f1keywords:
- ms.teamsadmincenter.meetingpolicies.overview
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- ms.teamsadmincenter.meetingpolicies.contentsharing
- ms.teamsadmincenter.meetingpolicies.general
- ms.teamsadmincenter.meetingpolicies.participantandguests
description: Obtenga información sobre cómo administrar la configuración de directivas en los equipos de la reunión.
ms.openlocfilehash: dc2870786c586715164dde94fdd6795f04f567bc
ms.sourcegitcommit: 5ed00e911a151d3ab834528f121db8653c25dc12
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2019
ms.locfileid: "30747673"
---
# <a name="manage-meeting-policies-in-teams"></a>Administrar las directivas de reunión en los equipos

::: zone target="docs"
Las directivas de reunión se usan para controlar las características que están disponibles para los participantes de las reuniones programadas por los usuarios de la organización de la reunión. Después de crear una directiva y realice los cambios, se puede, a continuación, asignar se usa para la directiva. 

De forma predeterminada, se crea una directiva con nombre Global (valor predeterminado de toda la organización). Todos los usuarios de su organización se asignará esta directiva de reunión de forma predeterminada. Puede realizar cambios en esta directiva o crear una o varias directivas personalizadas y asignar a usuarios a ellos. Cuando se crea una directiva personalizada, puede permitir o impedir que determinadas características que están disponibles para los usuarios y, a continuación, asignarla a uno o varios usuarios que tendrán las opciones que se aplican a ellos. 

## <a name="change-or-create-a-meeting-policy"></a>Cambiar o crear una directiva de reunión

Para cambiar o crear una directiva de reunión, vaya al **Centro de administración de equipos de Microsoft** > **reuniones** > **las directivas de reunión**. Seleccione una directiva de la lista, o seleccione **nueva directiva**. Elija la configuración y, a continuación, seleccione **Guardar**.

Por ejemplo, supongamos que tiene un montón de usuarios y desea limitar la cantidad de ancho de banda que requieran sus reuniones. Debe crear una nueva directiva personalizada denominada "Ancho de banda limitado" y deshabilite a las siguientes opciones:

En **Audio & vídeo**:
- Desactivar la nube grabación
- Desactivar la opción permitir IP vídeo

En el **uso compartido de contenido**:
- Deshabilitar el modo de uso compartido de pantalla
- Desactivar la Pizarra
- Desactivar notas compartidas

A continuación, asigne la directiva a los usuarios.

> [!NOTE] 
> Un usuario puede asignar la directiva de reunión sólo una a la vez. 

## <a name="assign-a-meeting-policy-to-users"></a>Asignar una directiva de reunión a los usuarios

Si va a aplicar la directiva a un usuario, seleccione **los usuarios** en el panel de navegación izquierdo y, a continuación, haga clic en nombre para mostrar del usuario. En la página del usuario, junto a **las directivas asignadas**, seleccione **Editar**. A continuación, en el panel **Editar las directivas de usuario** , en **la directiva de reunión**, en la lista desplegable, seleccione la directiva de reunión y, a continuación, seleccione **Guardar**. También puede asignar directivas desde la lista de usuarios. Para ello, seleccione el usuario al hacer clic en a la izquierda del nombre para mostrar del usuario. Seleccione **Editar la configuración**. A continuación, en el panel **Editar configuración** , en **Directiva de reunión**, seleccione la directiva de la lista desplegable y, a continuación, seleccione **Guardar**. 
 
Si va a aplicar una directiva a más de un usuario, seleccione **los usuarios** en el panel de navegación izquierdo y, a continuación, seleccione cada usuario haciendo clic en a la izquierda del nombre de usuario y, a continuación, haga clic en **Editar configuración**. En el panel **Editar configuración** , en **Directiva de reunión**, seleccione la directiva de la lista desplegable y, a continuación, seleccione **Guardar**.
 
También puede asignar una directiva de reunión a uno o varios usuarios como sigue:

1. Vaya al **Centro de administración de equipos de Microsoft** > **reuniones** > **las directivas de reunión**.
2. Seleccione la directiva, haga clic en a la izquierda del nombre de la directiva.
3. Seleccione **Administrar usuarios**.
4. En el panel **Administrar usuarios** , buscar el usuario por nombre para mostrar o por su nombre de usuario, seleccione el nombre y, a continuación, seleccione **Agregar**. Repita este paso para cada usuario que desee agregar.
5. Cuando haya terminado de agregar usuarios, seleccione **Guardar**.
 
> [!NOTE] 
> No se puede eliminar una directiva si los usuarios se asignan a él. En primer lugar debe asignar una directiva diferente a todos los usuarios afectados y, a continuación, puede eliminar la directiva original.
 
 
## <a name="user-policy-settings"></a>Configuración de la directiva de usuario

Cuando seleccione una directiva existente en la página de **directivas de reunión** o seleccione **nueva directiva** para agregar una nueva directiva, puede configurar los valores siguientes.

### <a name="new-meeting-policy-name-and-description"></a>Nueva reunión nombre de directiva y descripción
   - **Nombre** Esto es el nombre de la directiva que aparecerá en la página de **directivas de reunión** . No puede contener caracteres especiales ni tener más de 64 caracteres. Tenga en cuenta que no se puede cambiar el nombre de la directiva existente.
   - **Descripción** Puede colocar en una descripción simplificada de la directiva que se crea. Esto va a ser útil si desea asignar una directiva a un grupo de usuarios.
::: zone-end 

<a name="bkgeneral"> </a>
### <a name="general"></a>General
   - **Permitir Reunirse ahora** Activar esto le permitirá la característica Reunirse ahora para que esté disponible para los usuarios que se unen a las reuniones.
   - **Permitir que el complemento de Outlook** Activar esto le permitirá a los usuarios asignados a la directiva de tener el complemento de Outlook disponible al programar reuniones.
   - **Programación de reuniones de canal de permitir** Activar esto le permitirá programar reuniones de canal.
   - **Permitir programar reuniones privadas** Activar Esto permitirá a los usuarios que se unen a una reunión para programar reuniones privadas.

<a name="bkaudioandvideo"> </a>

### <a name="audio--video"></a>Audio & de vídeo
   - **Permitir transcripción** Si desactiva esta, transcripción de la reunión estará disponible para los usuarios.
   - **Grabación de permitir en la nube** Activar esto le permitirá grabaciones que se guarde en la nube.
   - **Permitir IP vídeo** Activar esto le permitirá vídeos IP durante las reuniones.
   - **(KB) de velocidad de bits de medios** Puede establecer la velocidad de bits para las reuniones. El valor predeterminado es 50 MB.

<a name="bkcontentsharing"> </a>

### <a name="content-sharing"></a>Uso compartido de contenido
   - **Modo de uso compartido de pantalla** Puede seleccionar el modo de uso compartido de pantalla. Se trata el tamaño de la pantalla que se va a usar durante una reunión que se puede usar un usuario asignado con la directiva.
   - **Permitir que un participante dar o solicitar el control** Esto permite que todos los participantes de una reunión ofrecer y solicitar el control del uso compartido de la pantalla.
   - **Permitir que un participante externo a proporcionar o solicitar el control** Esto permite que un participante externo (alguien no forma parte de su organización buscan una solución) conceder y solicitar el control de una reunión cuando se está compartiendo la pantalla.
   - **Uso compartido de PowerPoint permitir** Si desactiva esta, los usuarios que programación reuniones pueden compartir diapositivas de PowerPoint durante una reunión.
   - **Permitir Pizarra** Si desactiva esta la Pizarra estarán disponible para los participantes de la reunión durante una reunión.
   - **Permitir notas compartidas** Si desactiva esta, notas compartidas estarán disponibles para los participantes de la reunión durante una reunión.

<a name="bkparticipantsandguests"> </a>

### <a name="participants--guests"></a>Invitados de & de los participantes
   - **Permitir a las personas que acceso telefónico para iniciar una reunión** Puede activar o desactivar si desea permitir que las personas que aún no se ha autenticado porque ha marcado en usar su teléfono para iniciar una reunión.
   - **Admitir automáticamente las personas** Determina qué tipos de participantes establece automáticamente agregarse a las reuniones organizadas por este usuario. Debe establecer en "Todos los usuarios de la organización" si le gustaría que las reuniones para colocar todos los usuarios externos en la sala de espera, pero permitir que a todos los usuarios de la compañía para unirse a la reunión inmediatamente. Debe establecer en "Todos" Si desea que admiten a usuarios anónimos de forma predeterminada. Debe establecer en "Todas las personas de su organización y de organizaciones federadas" si le gustaría que las reuniones para permitir que los usuarios federados puedan unirse al igual que los usuarios de su compañía, pero colocar todos los demás usuarios externos en una sala de espera.

[Artículo completo](meeting-policies-in-teams.md)

### <a name="related-topics"></a>Temas relacionados
[Directivas de mensajería de los equipos](messaging-policies-in-teams.md)