---
title: Administrar propietarios de programación para la administración de turnos
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Obtenga información sobre cómo administrar los propietarios de turnos para la administración de programación. Puede establecer una directiva para elevar el permiso de un miembro del equipo a un propietario de programación.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9c0bc75e15439cf5fa7c3989bb0854521a1c45b8
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "58235755"
---
# <a name="schedule-owner-for-shift-management"></a>Propietario de la programación para la administración de turnos

## <a name="overview"></a>Información general

Propietario de programación es una característica que le permite elevar los permisos de un miembro del equipo a un propietario de programación sin convertir al empleado en propietario del equipo. Esto significa que el empleado está autorizado a administrar la programación de su equipo sin poder modificar otras propiedades del equipo, como actualizar, editar o eliminar canales de equipo.

¿Qué puede hacer un usuario con permisos de propietario de programación?

- Cree, edite y publique programaciones para administrar las asignaciones de turnos de su equipo.
- Ver y aprobar solicitudes de turno, incluidas las solicitudes para intercambiar turnos y realizar turnos abiertos.
- Administre la configuración en Turnos para habilitar determinadas características para el equipo.
- Ver y modificar el parte de horas de su equipo para procesar nóminas de empleados.

## <a name="why-schedule-owner"></a>¿Por qué programar propietario?

Sin la característica Propietario de programación, las funciones empresariales del día a día podrían interrumpirse. Aunque el propietario del equipo ayuda a ejecutar el equipo, es posible que no sea necesariamente la persona encargada de la programación diaria. En este caso, transferir solo la responsabilidad de administración de programación a otro miembro del equipo simplifica las operaciones diarias dentro del equipo y elimina la confusión de dos miembros del equipo que tienen los mismos privilegios de acceso.

## <a name="scenario"></a>Escenario

Este es un ejemplo de cómo su organización puede usar la característica Programar propietario.

Trabaja en una organización grande en la que los jefes de departamento informen directamente al administrador de la tienda. El administrador de la tienda tiene más autoridad dentro de su empresa y es el propietario del equipo en Turnos. Los jefes de departamento, por otro lado, solo se agregan a Turnos como miembros del equipo. Aunque los jefes de tienda tienen más antigüedad que los jefes de departamento, tiene más sentido que los jefes de departamento se encargan de la programación diaria de los empleados de su equipo.

*Sin el propietario de la programación,* los jefes de departamento deben tener exactamente los mismos privilegios que el propietario del equipo. Recientemente, los jefes de departamento han estado moviendo información y cambiando el nombre de los canales, y ha causado complicaciones con el trabajo del administrador de la tienda. El administrador de la tienda quiere que los jefes de departamento puedan organizar sus programaciones, pero no quiere que puedan cambiar nada más en el equipo, fuera de Turnos.

*Con Propietario de programación,* los jefes de departamento pueden tener privilegios de programación, sin ningún otro privilegio de propietario del equipo.

## <a name="manage-schedule-ownership"></a>Administrar la propiedad de la programación

Como administrador, usa directivas para controlar la propiedad de la administración de programación en su organización. Puede administrar estas directivas mediante los siguientes cmdlets de PowerShell:

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy?view=teams-ps)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy?view=teams-ps)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy?view=teams-ps)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy?view=teams-ps)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy?view=teams-ps)

### <a name="example-1"></a>Ejemplo 1

Aquí, creamos una nueva directiva denominada ScheduleOwnerPolicy con la característica Propietario de programación activada.

```powershell
New-CsTeamsShiftsPolicy –Identity ScheduleOwnerPolicy  -EnableScheduleOwnerPermissions $true -AccessType UnrestrictedAccess_TeamsApp
```

### <a name="example-2"></a>Ejemplo 2

En este ejemplo, asignamos una directiva denominada ScheduleOwnerPolicy a un usuario denominado remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName ScheduleOwnerPolicy
```

## <a name="related-articles"></a>Artículos relacionados

- [Administrar la aplicación Turnos para su organización en Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Administrar el acceso basado en turnos para los trabajadores de primera línea en Teams](manage-shift-based-access-flw.md) 
