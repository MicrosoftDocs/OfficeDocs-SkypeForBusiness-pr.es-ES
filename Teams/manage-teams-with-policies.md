---
title: Administrar Teams con directivas
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Límese sobre Teams directivas.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 77afc1cbb71fff9cb54decbbf6e5cfd10d6c4e59
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574189"
---
# <a name="manage-teams-with-policies"></a>Administrar Teams con directivas

Las directivas son una parte importante de la administración de Teams. Use este artículo para navegar por cómo usar directivas para beneficiar a su organización.

## <a name="what-you-use-policies-for"></a>Para qué usa las directivas

Las directivas se usan para realizar muchas tareas de su organización en diferentes áreas, como mensajería, reuniones y aplicaciones. Algunas de las cosas que puede hacer incluyen permitir a los usuarios programar reuniones en un canal de teams, permitir a los usuarios editar mensajes enviados y controlar si los usuarios pueden anclar aplicaciones a la barra de aplicaciones de Teams.

## <a name="how-to-assign-policies"></a>Cómo asignar directivas

Las directivas se pueden asignar de varias maneras diferentes en función de lo que su organización esté intentando lograr. Puede realizar y ver tareas en el centro Teams administración.

![Captura de pantalla de la asignación de directivas de grupo.](media/group-policy-assignment.png)

Obtenga más información sobre cómo asignar directivas [aquí.](policy-assignment-overview.md)

## <a name="how-to-manage-policies"></a>Cómo administrar directivas

Las directivas se administran con el Microsoft Teams de administración o [con PowerShell.](./teams-powershell-managing-teams.md#manage-policies-via-powershell)

Por ejemplo, una directiva de configuración de aplicaciones puede permitirle a los usuarios cargar aplicaciones personalizadas, instalar aplicaciones en nombre de los usuarios y anclar aplicaciones a la barra de aplicaciones Teams aplicación. Estas directivas se configuran en el centro Teams administración.

![Captura de pantalla de la directiva de configuración de la aplicación.](media/app-setup-policy.png)

Además, se puede usar una directiva de reunión para controlar la configuración de audio y vídeo en reuniones Teams, como transcripciones, grabaciones en la nube y audio/vídeo IP.

![Captura de pantalla de la directiva de reunión.](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a>Teams para el ámbito educativo

También puede usar el asistente [Teams](easy-policy-setup-edu.md) directivas de educación para configurar y administrar fácilmente directivas para su entorno de aprendizaje.

![Captura de pantalla Teams asistente para directivas de educación.](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a>Tipos de directivas

Las siguientes directivas se pueden administrar con Microsoft Teams.

Tipo de directiva | Descripción
------------|------------
[Paquetes de directivas](manage-policy-packages.md) | Un paquete de directivas en Microsoft Teams es una colección de directivas y configuraciones predefinidas que puede asignar a usuarios que tienen roles similares en su organización.
[Directivas de reunión](meeting-policies-in-teams.md) | Una directiva de reunión se usa para controlar las características que están disponibles para los participantes de la reunión para las reuniones programadas por los usuarios de su organización. Las directivas de reunión incluyen los temas siguientes.<br> - Directivas de audio y vídeo<br> - Directivas de uso compartido de pantalla y contenido<br> - Participantes, invitados y directivas de acceso<br> - Directivas generales
[Directivas de voz y llamadas](voice-and-calling-policies.md)| Las directivas de llamadas y llamadas administran esta configuración a través de equipos como llamadas de emergencia, enrutamiento de llamadas e id. de llamada.
[Directivas de aplicaciones](app-policies.md)| Las directivas de aplicación se usan para controlar las aplicaciones en Microsoft Teams. Los administradores pueden permitir o bloquear las aplicaciones que los usuarios pueden instalar, anclar aplicaciones a la barra de aplicaciones de Teams de un usuario e instalar la aplicación en nombre de los usuarios.
[Directivas de mensajería](messaging-policies-in-teams.md)| Las directivas de mensajería controlan la disponibilidad de las características de chat y canal.

## <a name="related-topics"></a>Temas relacionados

* [Asignar directivas en Teams: introducción](policy-assignment-overview.md)
* [Administrar directivas de comentarios en Microsoft Teams](manage-feedback-policies-in-teams.md)
* [Administrar directivas de equipos en Microsoft Teams](teams-policies.md)
* [Definir eventos en directo en Microsoft Teams](teams-live-events/set-up-for-teams-live-events.md)
* [Teams directivas y paquetes de directivas para el sector educativo](policy-packages-edu.md)