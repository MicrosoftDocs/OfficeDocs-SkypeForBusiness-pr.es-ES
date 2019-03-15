---
title: Información general sobre la pertenencia dinámica para los equipos
author: jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre pertenencia dinámica de equipos en función de AAD.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 45e9da5b5bc9c1bb5800634d727bd6c9218812ab
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2019
ms.locfileid: "30569833"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>Información general sobre la pertenencia dinámica para los equipos

Microsoft Teams es compatible con los equipos asociados con grupos de Office 365 mediante pertenencia dinámica. Pertenencia dinámica permite la pertenencia de un equipo a definirse por una o varias reglas que comprobación ciertos atributos de usuario en Azure Active Directory (AAD). Los usuarios automáticamente se agregan o quitan a los equipos de la correctos como cambian atributos de usuario o los usuarios al unirse y abandonar al inquilino.

Con pertenencia dinámica que se puede el programa de instalación para determinados equipos a las cohortes de los usuarios de su organización. Los escenarios posibles son:
- Un hospital puede crear distintos equipos para enfermeras, médicos y cirujanos difundir communications. Esto es especialmente importante si el hospital se basa en los empleados temporales.
- Una universidad puede crear un equipo para todos los profesores dentro de un determinado universitario, incluido un profesor adjuntos que cambia con frecuencia.
- Un compañías aéreas desea crear un equipo para cada vuelo (al igual que un martes por la tarde sin interrupciones de Chicago a Atlanta) y tienen un crew vuelo que cambia con frecuencia asignada automáticamente o quitan según sea necesario.

Uso de esta característica, actualización de los miembros de un equipo determinado automáticamente según un conjunto específico de criterios, en lugar de administrar manualmente pertenencia. Esta acción requiere licencias de Azure AD Premium P1 y los miembros del equipo pueden ser [asignado por un administrador de inquilinos](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) a las propiedades AAD de cualquier usuario siempre y que cuando disponga de un inquilino y una cuenta de administrador. 

Microsoft Teams puede durar desde unos minutos hasta 2 horas para reflejar los cambios de pertenencia dinámica una vez que surtan efecto en el grupo de Office 365 para un equipo. 

> [!NOTE]
> - Pueden definir reglas que es un miembro del equipo, pero no que es un equipo propietario.
> - Vea [los límites y las especificaciones de los equipos de Microsoft](limits-specifications-teams.md) para conocer los límites actuales en los tamaños de canal y el equipo.
> - Los propietarios no podrá agregar o quitar usuarios como miembros del equipo, ya que los miembros se definen por las reglas de grupo dinámico.
> - Los miembros no podrá dejar los equipos respaldados por grupos dinámicos.


## <a name="creating-and-managing-an-office-365-group-with-dynamic-membership"></a>Creación y administración de un grupo de Office 365 con pertenencia dinámica
Cuando haya iniciado sesión como el Administrador de inquilinos, siga las instrucciones de [crear un grupo dinámico y compruebe el estado](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule). Según sea necesario, hacer referencia a [las reglas de pertenencia dinámica para los grupos en Active Directory de Azure](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).

## <a name="create-a-new-team-with-your-o365-group"></a>Crear un nuevo equipo con su grupo de O365

Ahora Permitir tiempo para que surtan efecto los cambios de pertenencia y crear un nuevo equipo tal como se describe en [grupos de mejorar existente Office 365 con los equipos de Microsoft](enhance-office-365-groups.md).

## <a name="apply-dynamic-membership-to-an-existing-team"></a>Aplicar pertenencia dinámica a un equipo existente

También puede tomar un equipo existente y cámbiela para que tenga una pertenencia dinámica, tal como se describe en [cambiar la pertenencia a grupo estático a dinámico en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).

## <a name="changes-in-client-behavior"></a>Cambios en el comportamiento del cliente

Una vez habilitada la pertenencia dinámica para un equipo, los clientes de equipos ya no le permitirá la gestión de miembros para el equipo. Todas las opciones para agregar a miembros, editar funciones miembro, enviar y aprobar las solicitudes de participación y deje el equipo están ocultos.
