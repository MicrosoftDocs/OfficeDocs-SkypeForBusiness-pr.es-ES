---
title: Información general sobre la pertenencia dinámica para los equipos
author: jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
description: Obtenga más información sobre la pertenencia a equipos dinámicos basadas en AAD.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8f48309b5816c61668d240087c1f2815fc94ebe4
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221439"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>Información general sobre la pertenencia dinámica para los equipos

Microsoft Teams es compatible con los equipos asociados con los grupos de Office 365 mediante la *pertenencia dinámica*. La pertenencia dinámica permite a la pertenencia de un equipo definirse por una o más reglas que comprueban determinados atributos de usuario en Azure Active Directory (Azure AD). Los usuarios se agregan o quitan automáticamente a los equipos correctos a medida que los atributos de usuario cambian o se unen y abandonan el inquilino.

Con la pertenencia dinámica puede configurar Teams para determinados cohorts de usuarios de su organización. Entre los posibles escenarios se incluyen:
- Un hospital puede crear equipos distintos para enfermeras, doctores y cirujanos para difundir las comunicaciones. Esto es especialmente importante si el hospital depende de empleados temporales.
- Una universidad puede crear un equipo para todos los profesores dentro de una universidad determinada, entre ellos un profesorado de Adjunct que cambia con frecuencia.
- Una línea aérea desea crear un equipo para cada vuelo (como un martes por la tarde sin detenerse en Chicago) y se les asigna o elimina un equipo de vuelo que cambia con frecuencia según sea necesario.

Con esta característica, los miembros de un equipo dado se actualizan automáticamente según un conjunto específico de criterios, en lugar de administrar la pertenencia de forma manual. Para ello, es necesario que [un administrador](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) de inquilinos pueda asignar licencias de Azure ad Premium P1 y la pertenencia al equipo a las propiedades de Azure ad de cualquier usuario siempre que tenga un inquilino y una cuenta de administrador.

Microsoft Teams puede tardar desde unos minutos hasta 2 horas en reflejar los cambios dinámicos de pertenencia, una vez que se aplican al grupo de Office 365 de un equipo.

> [!NOTE]
> - Las reglas pueden definir quién es un miembro del equipo, pero no quién es el propietario de un equipo.
> - Consulte [límites y especificaciones de Microsoft Teams](limits-specifications-teams.md) para obtener los límites actuales de los tamaños de equipo y de canal.
> - Los propietarios no podrán agregar o quitar usuarios como miembros del equipo, ya que los miembros se definen mediante reglas de grupo dinámicas.
> - Los miembros no podrán dejar equipos respaldados por grupos dinámicos.


## <a name="creating-and-managing-an-office-365-group-with-dynamic-membership"></a>Crear y administrar un grupo de Office 365 con pertenencia dinámica
Cuando haya iniciado sesión como administrador de inquilinos, siga las instrucciones de [crear un grupo dinámico y comprobar el estado](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule). Según sea necesario, consulte [reglas de pertenencia dinámica para grupos en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).

## <a name="create-a-new-team-with-your-o365-group"></a>Crear un equipo nuevo con el grupo de O365

Ahora deje que se apliquen los cambios de pertenencia y cree un equipo nuevo tal y como se describe en [mejorar los grupos existentes de Office 365 con Microsoft Teams](enhance-office-365-groups.md).

## <a name="apply-dynamic-membership-to-an-existing-team"></a>Aplicar pertenencia dinámica a un equipo existente

También puede tomar un equipo existente y cambiarlo para que tenga una pertenencia dinámica, tal y como se describe en [cambiar la pertenencia a grupos estáticos a dinámico en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).

## <a name="changes-in-client-behavior"></a>Cambios en el comportamiento del cliente

Una vez habilitada la pertenencia dinámica para un equipo, los clientes de equipos ya no permitirán la administración de miembros del equipo. Las opciones para agregar miembros, editar roles de miembro, enviar y aprobar solicitudes de participación, y dejar el equipo están ocultos.
