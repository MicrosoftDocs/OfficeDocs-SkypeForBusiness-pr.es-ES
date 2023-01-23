---
title: Configurar seminarios web
ms.author: mabond
author: mkbond007
manager: serdars
ms.reviewer: sachung, emryan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
description: Obtenga información sobre cómo administrar directivas de registro de seminarios web y reuniones en Teams.
ms.openlocfilehash: 097f4c385261ba1aea96990751d208b99d4d8b93
ms.sourcegitcommit: 5e0900ed7a21ed4e854cc00dbfb4ae4ff2372262
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2023
ms.locfileid: "69950437"
---
# <a name="set-up-webinars-in-microsoft-teams"></a>Configurar seminarios web en Microsoft Teams

> [!NOTE]
> En este artículo se describen algunas características de seminarios web que están en versión preliminar y requieren una licencia de Teams Premium.

Microsoft ofrece ahora una nueva experiencia de seminario web; en este artículo se describe cómo actualizar la configuración para usar estas características.

Le recomendamos que use la nueva experiencia de seminario web si planea usar seminarios web.

El registro de reuniones incluye funcionalidad básica de seminario web, la capacidad de requerir registro para reuniones y un informe de asistencia. Al habilitar la nueva experiencia de seminario web, tiene la capacidad de usar el registro de reuniones y muchas características de seminario web nuevas, como:

- Página de registro y eventos dedicados para su seminario web
- Organizadores colaboradores
- Bios del moderador en la página del evento
- Información general y administración del estado de registro

Obtenga más información sobre las nuevas características disponibles para los usuarios finales en [Introducción a los seminarios web de Teams](https://support.microsoft.com/office/42f3f874-22dc-4289-b53f-bbc1a69013e3).

Si su organización tiene habilitado el registro de reuniones, todos los seminarios web recién creados tendrán la nueva experiencia. Los seminarios web programados anteriormente usarán la experiencia del seminario web anterior. La nueva experiencia usa TeamsEventsPolicy. Si tiene los seminarios web desactivados, permanecerán desactivados a medida que se implemente la nueva experiencia.

Actualmente, la experiencia básica del seminario web se controla mediante el registro de reuniones mediante la directiva de reunión de Teams (Set-CsTeamsMeetingPolicy). En el futuro, la configuración de registro de reuniones no controlará los seminarios web; Los seminarios web pasan a ser controlados por la directiva eventos de Teams (Set-CsTeamsEventsPolicy).

La nueva experiencia de seminario web está configurada en PowerShell. Vea ejemplos sobre [cómo configurar la nueva experiencia de seminario web](#set-up-new-webinar-experience).

Para obtener más información sobre las diferencias entre reuniones, seminarios web y eventos en directo, vea [Reuniones, seminarios web y eventos en directo](quick-start-meetings-live-events.md).

> [!NOTE]
> Para los usuarios locales, el nuevo seminario web aún no está disponible.
>
> La nueva experiencia de seminario web no está disponible para Microsoft 365 GCC, Microsoft 365 GCC High ni Microsoft 365 DoD. La experiencia de seminario web existente no está disponible para Microsoft 365 GCC High ni Microsoft 365 DoD.

> [!IMPORTANT]
> Para permitir a los usuarios configurar seminarios web, Listas Microsoft deben configurarse en SharePoint habilitando la creación de listas personales con fines de exhibición de documentos electrónicos. Para obtener más información, consulta [Configuración de control de Listas Microsoft](/sharepoint/control-lists).

## <a name="set-up-new-webinar-experience"></a>Configurar una nueva experiencia de seminario web

Debe usar PowerShell para configurar la nueva experiencia de seminario web para su organización. La capacidad para configurar la nueva experiencia de seminario web en el centro de administración de Teams aún no está disponible.

El registro de reuniones debe estar activado para usar la nueva experiencia de seminario web.

### <a name="configure-the-new-webinar-experience-with-powershell"></a>Configurar la nueva experiencia de seminario web con PowerShell

Para configurar la nueva experiencia de seminario web, use los siguientes atributos dentro del cmdlet Windows PowerShell **Set-CsTeamsEventsPolicy**.

|Parámetro|Valor predeterminado|Descripción|
|---------|-----------|---------------|
|AllowWebinars|Habilitado|Esta configuración determina si un usuario puede crear seminarios web.|
|EventAccessType|Todos|Esta configuración determina qué usuarios pueden acceder a la página de registro de eventos o al sitio de eventos que se va a registrar, así como qué tipo de usuario puede unirse a las sesiones del evento.|

Antes de poder ejecutar estos cmdlets, debe estar conectado a Microsoft Teams PowerShell. Para obtener más información, consulte [Administrar Teams con Microsoft Teams PowerShell](/microsoftteams/teams-powershell-managing-teams).

1. Active el registro de la reunión.

    ```powershell
    Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowMeetingRegistration $True
    ```

1. Active la nueva experiencia de seminario web.

    ```powershell
    Set-CsTeamsEventsPolicy -Identity <policy name> -AllowWebinars Enabled
    ```

1. Configure quién puede registrarse en seminarios web y reuniones.

    - **Permitir que **_only_* _ usuarios de su organización se registren en seminarios web y meetings_*

        ```powershell
        Set-CsTeamsEventsPolicy -Identity <policy name> -EventAccessType EveryoneInCompanyExcludingGuests
        ```

    - **Permitir que todos los usuarios, incluidos los usuarios anónimos, se registren en seminarios web y reuniones**

        ```powershell
        Set-CsTeamsEventsPolicy -Identity <policy name> -EventAccessType Everyone
        ```

> [!IMPORTANT]
> Si **la opción Usuarios anónimos puede unirse a una reunión** está desactivada en **Configuración de la reunión**, los usuarios anónimos no podrán unirse a seminarios web. Para obtener más información y habilitar esta configuración, consulte [Configuración de la reunión en Teams](meeting-settings-in-teams.md).

## <a name="configure-meeting-registration"></a>Configurar el registro de reuniones

Si desea usar seminarios web, el registro de reuniones debe estar activado.

Puede usar el Centro de administración de Teams en **Directivas** >  de **reunión** de reuniones para configurar el registro de reuniones y seminarios web.

### <a name="meeting-registration"></a>Registro de reunión

Si activa el **registro** de reuniones, los usuarios de su organización pueden programar seminarios web y reuniones que requieran registro. Esta configuración está activada de forma predeterminada. Si desea desactivar el registro de reuniones y los seminarios web, establezca esta directiva en **Desactivado**.

**La programación de reuniones privadas** debe estar activada para que funcione el registro de la reunión. Obtenga más información sobre la [programación de reuniones privadas](meeting-policies-in-teams-general.md).

Para los estudiantes de inquilinos educativos, esta directiva está desactivada de forma predeterminada. Para obtener más información sobre cómo habilitar la programación de reuniones privadas para los alumnos, vea [Teams para Educación directivas y paquetes de directivas](policy-packages-edu.md).

#### <a name="who-can-register"></a>Quién puede registrarse

> [!NOTE]
> Esta directiva no se aplica a la nueva experiencia de seminario web. Para configurar quién puede registrarse en la nueva experiencia de seminario web, use `Set-CsTeamsEventsPolicy -EventAccessType`, como se muestra en [Configurar la nueva experiencia de seminario web con PowerShell](#configure-the-new-webinar-experience-with-powershell).

Esta directiva controla qué usuarios pueden registrar y asistir a seminarios web solo con registro de reuniones. Esta directiva tiene dos opciones, que solo están disponibles si el **registro de la reunión** está activado. De forma predeterminada, **Quién puede registrarse** está establecido en **Todos**.

Si selecciona **Todos** los usuarios, todos los usuarios, incluidos los usuarios anónimos, pueden registrarse y asistir a seminarios web. Si selecciona **Todos los usuarios de la organización**, solo los usuarios de su organización pueden registrarse y asistir a seminarios web. Si el registro de reuniones está desactivado, la opción **Quién puede registrarse** no estará disponible y nadie podrá registrarse en seminarios web.

El valor predeterminado de **Quién puede registrarse** es **Todos los usuarios de la organización** en inquilinos educativos. Para obtener más información, consulte [Asistente para directivas de Teams para Educación](easy-policy-setup-edu.md).

## <a name="collect-webinar-and-meeting-registration-attendance"></a>Recopilar asistencia al seminario web y al registro de reuniones

Puede usar el Centro de administración de Teams en **Directivas** >  de **reunión** de reuniones para activar el **informe de interacción**.

Cuando esta configuración está activada, los organizadores pueden ver los informes de las personas que se registraron y asistieron a los seminarios web o las reuniones que configuraron. Esta directiva está activada de forma predeterminada. Para obtener más información, consulte [Directivas de reunión en Teams - Informe de interacción](meeting-policies-in-teams-general.md#engagement-report). Para obtener información sobre la experiencia del usuario final, vea [Ver y descargar informes de asistencia a reuniones](https://support.microsoft.com/office/ae7cf170-530c-47d3-84c1-3aedac74d310).

En PowerShell, el parámetro **AllowEngagementReport** se puede usar para activarlo. Esta directiva está activada de forma predeterminada. Para desactivarlo, ejecute el siguiente comando en PowerShell:

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowEngagementReport Disabled
```

Lea [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) para obtener más información sobre el cmdlet.

## <a name="turn-off-webinars"></a>Desactivar seminarios web

Puede desactivar seminarios web con PowerShell. Esto desactivará la nueva experiencia de seminario web, así como los seminarios web solo con registro de reuniones.

Use el siguiente script de PowerShell para desactivar seminarios web:

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowMeetingRegistration $False
Set-CSTeamsEventsPolicy -Identity <policy name> -AllowWebinars Disabled
```

## <a name="related-topics"></a>Temas relacionados

- [Directivas de reunión en Teams: General](meeting-policies-in-teams-general.md)
- [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Set-CsTeamsEventsPolicy](/powershell/module/teams/set-csteamseventspolicy)
