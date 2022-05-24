---
title: Administrar Teams con directivas
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Mejore las directivas de Teams.
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 932fed6b2a735aabee0511b6f1c6b863e01e403c
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646489"
---
# <a name="manage-teams-with-policies"></a>Administrar Teams con directivas

Las directivas son una parte importante de la administración de Teams. Use este artículo para navegar por el modo de usar directivas para beneficiar a su organización.

## <a name="what-you-use-policies-for"></a>Para qué se usan las directivas

Las directivas se usan para realizar muchas tareas de su organización en diferentes áreas, como mensajería, reuniones y aplicaciones. Entre algunas de las cosas que puede hacer se incluyen permitir a los usuarios programar reuniones en un canal de teams, permitir a los usuarios editar los mensajes enviados y controlar si los usuarios pueden anclar aplicaciones a la Teams barra de aplicaciones.

## <a name="how-to-assign-policies"></a>Cómo asignar directivas

Las directivas se pueden asignar de varias maneras diferentes dependiendo de lo que su organización intenta lograr. Puede realizar y ver tareas en el centro de administración de Teams.

![Captura de pantalla de asignación de directiva de grupo.](media/group-policy-assignment.png)

Obtenga más información sobre cómo asignar directivas [aquí](policy-assignment-overview.md).

## <a name="how-to-manage-policies"></a>Cómo administrar directivas

Las directivas se administran con el centro de administración de Microsoft Teams o [mediante PowerShell](./teams-powershell-managing-teams.md#manage-policies-via-powershell).

Por ejemplo, una directiva de configuración de aplicaciones puede permitirle a los usuarios cargar aplicaciones personalizadas, instalar aplicaciones en nombre de los usuarios y anclar aplicaciones a la barra de aplicaciones Teams. Estas directivas se configuran en el centro de administración de Teams.

![Captura de pantalla de la directiva de configuración de aplicaciones.](media/app-setup-policy.png)

Además, se puede usar una directiva de reunión para controlar la configuración de audio y vídeo en Teams reuniones, como transcripciones, grabaciones en la nube y audio/vídeo IP.

![Captura de pantalla de la directiva de reunión.](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a>Teams para el ámbito educativo

También puede usar el [asistente para directivas de Teams para Educación](easy-policy-setup-edu.md) para configurar y administrar fácilmente directivas para su entorno de aprendizaje.

![Captura de pantalla del Asistente para directivas de Teams para Educación.](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a>Tipos de directivas

Las siguientes directivas se pueden administrar con Microsoft Teams.

Tipo de directiva | Descripción
------------|------------
[Paquetes de directivas](manage-policy-packages.md) | Un paquete de directivas de Microsoft Teams es una colección de directivas y configuraciones predefinidas que puede asignar a usuarios que tienen roles similares en su organización.
[Directivas de reunión](meeting-policies-overview.md) | Una directiva de reunión se usa para controlar las características que están disponibles para los participantes de la reunión para las reuniones programadas por los usuarios de su organización. Las directivas de reunión incluyen los siguientes temas.<br> - Directivas de audio y vídeo<br> - Directivas de uso compartido de pantalla y contenido<br> - Participantes, invitados y directivas de acceso<br> - Directivas generales
[Directivas de voz y llamadas](voice-and-calling-policies.md)| Las directivas de voz y llamadas administran esta configuración a través de equipos, como las llamadas de emergencia, el enrutamiento de llamadas y el identificador de llamada.
[Directivas de aplicaciones](app-policies.md)| Las directivas de aplicaciones se usan para controlar las aplicaciones en Microsoft Teams. Los administradores pueden permitir o bloquear las aplicaciones que los usuarios pueden instalar, anclar aplicaciones a la barra de aplicaciones Teams de un usuario e instalar aplicaciones en nombre de los usuarios.
[Directivas de mensajería](messaging-policies-in-teams.md)| Las directivas de mensajería controlan la disponibilidad de las características del canal y el chat.

## <a name="related-topics"></a>Temas relacionados

* [Asignar directivas en Teams: introducción](policy-assignment-overview.md)
* [Administrar directivas de comentarios en Microsoft Teams](manage-feedback-policies-in-teams.md)
* [Administrar directivas de equipos en Microsoft Teams](teams-policies.md)
* [Definir eventos en directo en Microsoft Teams](teams-live-events/set-up-for-teams-live-events.md)
* [Teams para Educación directivas y paquetes de directivas](policy-packages-edu.md)