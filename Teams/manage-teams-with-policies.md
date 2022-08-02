---
title: Administrar Teams con directivas
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Conozca las directivas de Teams.
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b56e617321cea25fe677b7d9a7a00afba0940b07
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2022
ms.locfileid: "67156538"
---
# <a name="manage-teams-with-policies"></a>Administrar Teams con directivas

Las directivas son una parte importante de la administración de Teams. Use este artículo para navegar por el modo de usar directivas para beneficiar a su organización.

## <a name="what-you-use-policies-for"></a>Para qué se usan las directivas

Las directivas se usan para realizar muchas tareas de su organización en diferentes áreas, como mensajería, reuniones y aplicaciones. Entre las cosas que puede hacer se incluye permitir a los usuarios programar reuniones en un canal de teams, permitir a los usuarios editar los mensajes enviados y controlar si los usuarios pueden anclar aplicaciones a la barra de aplicaciones de Teams.

## <a name="how-to-assign-policies"></a>Cómo asignar directivas

Las directivas se pueden asignar de varias maneras diferentes dependiendo de lo que su organización intenta lograr. Puede realizar y ver tareas en el Centro de administración de Teams.

![Captura de pantalla de asignación de directiva de grupo.](media/group-policy-assignment.png)

Obtenga más información sobre cómo asignar directivas [aquí](policy-assignment-overview.md).

> [!NOTE]
> Para anular la asignación de directivas, puede quitar las asignaciones de forma masiva para todos los usuarios asignados directamente a una directiva. Para obtener más información, lea [Anular la asignación masiva de directivas](assign-policies-users-and-groups.md#unassign-policies-in-bulk).

## <a name="how-to-manage-policies"></a>Cómo administrar directivas

Las directivas se administran con el Centro de administración de Microsoft Teams o [con PowerShell](./teams-powershell-managing-teams.md#manage-policies-via-powershell).

Por ejemplo, una directiva de configuración de aplicaciones puede permitirle a los usuarios cargar aplicaciones personalizadas, instalar aplicaciones en nombre de los usuarios y anclar aplicaciones a la barra de aplicaciones de Teams. Estas directivas se configuran en el Centro de administración de Teams.

![Captura de pantalla de la directiva de configuración de aplicaciones.](media/app-setup-policy.png)

Además, se puede usar una directiva de reunión para controlar la configuración de audio y vídeo en las reuniones de Teams, como las transcripciones, las grabaciones en la nube y el audio/vídeo IP.

![Captura de pantalla de la directiva de reunión.](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a>Teams para el ámbito educativo

También puede usar el [asistente para directivas de Teams para Educación](easy-policy-setup-edu.md) para configurar y administrar fácilmente directivas para su entorno de aprendizaje.

![Captura de pantalla del Asistente para directivas de Teams para Educación.](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a>Tipos de directivas

Las siguientes directivas se pueden administrar con Microsoft Teams.

Tipo de directiva | Descripción
------------|------------
[Paquetes de directivas](manage-policy-packages.md) | Un paquete de directivas en Microsoft Teams es una colección de directivas y configuraciones predefinidas que puede asignar a los usuarios que tienen roles similares en su organización.
[Directivas de reunión](meeting-policies-overview.md) | Una directiva de reunión se usa para controlar las características que están disponibles para los participantes de la reunión para las reuniones programadas por los usuarios de su organización. Las directivas de reunión incluyen los siguientes temas.<br> - Directivas de audio y vídeo<br> - Directivas de uso compartido de pantalla y contenido<br> - Participantes, invitados y directivas de acceso<br> - Directivas generales
[Directivas de voz y llamadas](voice-and-calling-policies.md)| Las directivas de voz y llamadas administran esta configuración a través de equipos, como las llamadas de emergencia, el enrutamiento de llamadas y el identificador de llamada.
[Directivas de aplicaciones](app-policies.md)| Las directivas de aplicaciones se usan para controlar las aplicaciones en Microsoft Teams. Los administradores pueden permitir o bloquear las aplicaciones que los usuarios pueden instalar, anclar aplicaciones a la barra de aplicaciones de Teams de un usuario e instalar aplicaciones en nombre de los usuarios.
[Directivas de mensajería](messaging-policies-in-teams.md)| Las directivas de mensajería controlan la disponibilidad de las características del canal y el chat.

## <a name="related-topics"></a>Temas relacionados

* [Asignar directivas en Teams: introducción](policy-assignment-overview.md)
* [Administrar directivas de comentarios en Microsoft Teams](manage-feedback-policies-in-teams.md)
* [Administrar directivas de equipos en Microsoft Teams](teams-policies.md)
* [Definir eventos en directo en Microsoft Teams](teams-live-events/set-up-for-teams-live-events.md)
* [Teams para Educación directivas y paquetes de directivas](policy-packages-edu.md)