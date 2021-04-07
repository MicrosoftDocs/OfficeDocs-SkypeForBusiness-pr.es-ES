---
title: Administrar directivas de reunión
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.overview
- seo-marvel-apr2020
description: Descubra cómo administrar la configuración de una directiva de reunión en Teams con el fin de controlar las características disponibles para sus participantes en reuniones programadas por usuarios.
ms.openlocfilehash: d9f403625225711cb21245ca01262d3c0140063f
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598763"
---
# <a name="manage-meeting-policies-in-teams"></a>Administrar directivas de reunión en Teams

<a name="bkautomatically-admit-people"> </a>

<a name="bkallow-a-participant-to-give-or-request-control"> </a>

<a name="bkallow-transcription"> </a>

Las Directivas de reunión se usan para controlar las características disponibles para sus participantes en reuniones programadas por usuarios de la organización. Puede usar la directiva global (predeterminada para toda la organización) o crear directivas personalizadas y asignarlas a los usuarios. Puede administrar las directivas de reuniones en el Centro de administración de Microsoft Teams o mediante [PowerShell](teams-powershell-overview.md).

> [!NOTE]
> Para obtener información sobre el uso de los roles para administrar los permisos de los moderadores y los asistentes de reuniones, consulte [Roles en una reunión de Teams](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).

Puede implementar directivas en las formas que se indican a continuación. Esto afectará a la experiencia de los usuarios antes de que se inicie la reunión, durante una reunión o después de una reunión.

|Tipo de implementación  |Descripción  |
|---------|---------|
|Por organizador    |Al implementar una directiva por organizador, todos los participantes de la reunión heredan la directiva del organizador. Ejemplo: **Admitir automáticamente personas** es una directiva por organizador y controla si los usuarios pueden unirse a la reunión directamente o esperar en la sala de espera para reuniones programadas por el usuario al que se ha asignado la directiva.          |
|Por usuario    |Cuando implementa una directiva por usuario, solo la directiva por usuario se aplica para restringir determinadas características para el organizador o los participantes de la reunión. Por ejemplo, **Permitir Reunirse ahora en los canales** es una directiva por usuario.     |
|Por organizador y por usuario     |Cuando implementa una combinación de una directiva por organizador y por usuario, se restringen determinadas características a los participantes de la reunión en función de las directivas de los usuarios y del organizador. Por ejemplo, **Permitir la grabación en la nube** es una directiva por organizador y por usuario. Active esta opción para permitir que el organizador de la reunión y los participantes inicien y detengan una grabación.

Puede editar la configuración en la directiva global o crear y asignar una o más directivas personalizadas. Los usuarios obtendrán la directiva global, a menos que usted cree y asigne una directiva personalizada.

> [!NOTE]
> El botón Detalles de la reunión estará disponible si un usuario tiene habilitadas las licencias de conferencia de audio o si el usuario admite las conferencias de audio. Si no, los detalles de la reunión no estarán disponibles.

## <a name="create-a-custom-meeting-policy"></a>Crear una directiva de reuniones personalizada

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Reuniones** > **Directivas de reunión**.
2. Haga clic en **Agregar**.
3. Escriba un nombre y una descripción para la directiva. El nombre no puede contener caracteres especiales ni tener más de 64 caracteres.
4. Seleccione la configuración que quiera usar.
5. Haga clic en **Guardar**.

Por ejemplo, supongamos que tiene un grupo de usuarios y quiere limitar el ancho de banda que necesitaría la reunión. Cree una nueva directiva personalizada denominada "ancho de banda limitado" y deshabilite las opciones siguientes:

En **Audio y vídeo**:

- Desactive Permitir la grabación en la nube.
- Desactive Permitir vídeo IP.

En **Uso compartido de contenido**:

- Desactive el modo de uso compartido de la pantalla.
- Desactive Permitir pizarra.
- Desactive Permitir notas compartidas.

Luego asigne la directiva a los usuarios:

## <a name="edit-a-meeting-policy"></a>Editar una directiva de reunión

Puede editar la directiva global y las directivas personalizadas que cree.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Reuniones** > **Directivas de reunión**.
2. Haga clic a la izquierda del nombre de la directiva para seleccionarla y, luego, en **Editar**.
3. A partir de aquí, realice los cambios que desee.
4. Haga clic en **Guardar**.

> [!NOTE]
> Un usuario solo puede tener asignada una directiva de reuniones cada vez.

## <a name="assign-a-meeting-policy-to-users"></a>Asignar una directiva de reunión a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> No puede eliminar una directiva si tiene usuarios asignados. Primero, debe asignar una directiva diferente a todos los usuarios afectados. Luego, podrá eliminar la directiva original.

## <a name="meeting-policy-settings"></a>Configuración de la directiva de reunión

Al seleccionar una directiva existente en la página **Directivas de reunión** o seleccionar **Agregar** para agregar una nueva directiva, puede establecer la configuración para lo siguiente.

- [General](meeting-policies-in-teams-general.md)
- [Audio y vídeo](meeting-policies-audio-and-video.md)
- [Uso compartido de contenido](meeting-policies-content-sharing.md)
- [Participantes e invitados](meeting-policies-participants-and-guests.md)


## <a name="related-topics"></a>Temas relacionados

- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
- [Asignar directivas a los usuarios en Teams](assign-policies.md)
- [Quitar a los usuarios la directiva de reunión de Teams RestrictedAnonymousAccess](meeting-policies-restricted-anonymous-access.md)