---
title: Administrar quién puede iniciar reuniones instantáneas y programar reuniones
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: nej, brgussin
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: Aprenda a usar la configuración de directivas de reuniones de Teams para controlar quién puede iniciar reuniones instantáneas y programar reuniones.
ms.openlocfilehash: 6736ecd20ef4b0e9eb082e83bd8212597da5f7ab
ms.sourcegitcommit: 7a1fb6e15c21368afa34cd212865437781f721e2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466298"
---
# <a name="manage-who-can-start-instant-meetings-and-schedule-meetings"></a>Administrar quién puede iniciar reuniones instantáneas y programar reuniones

Como administrador, puede restringir qué usuarios pueden iniciar reuniones instantáneas y programar reuniones en Teams. Esto puede ser especialmente útil por motivos de privacidad y seguridad, en los que es posible que no quiera que determinados usuarios configuren reuniones.

La configuración de la directiva de reunión está activada de forma predeterminada. Esta configuración puede encontrarse en el Centro de administración de Teams, en **Directivas** > **de reunión de reuniones**.

- **Reunirse ahora en canales**: controla si un usuario puede iniciar una reunión instantánea en un canal.
- **Programación de reuniones** de canal: controla si un usuario puede programar una reunión en un canal.
- **Programación de reuniones privadas**: controla si un usuario puede programar una reunión privada en Teams. Una reunión es privada cuando no se publica en un canal de un equipo.
- **Complemento de Outlook**: controla si un usuario puede programar una reunión privada desde Outlook. Una reunión es privada cuando no se publica en un canal de un equipo.
- **Reunirse ahora en reuniones privadas**: controla si un usuario puede iniciar una reunión privada instantánea.

> [!NOTE]
> Si la reunión la envió un delegado, al que se le dio permiso para enviar invitaciones a reuniones en nombre de otra persona, como un jefe, la configuración de la directiva de reunión se aplicará a la persona que le concedió permiso (el jefe).

## <a name="channel-meetings"></a>Reuniones de canal

Si tiene requisitos de cumplimiento que exigen que solo personas específicas inicien reuniones de canal instantáneo y programen reuniones de canal, puede crear o actualizar la directiva de reuniones para restringir esta configuración. Después, puede crear una directiva independiente a los usuarios a los que desea iniciar reuniones de canal instantáneo y programar reuniones de canal.

1. En el Centro de administración de Teams, vaya a **Directivas** >  de **reunión** de reuniones y elija la directiva que desea actualizar. Para crear una directiva, haga clic en **Agregar**.
1. En **General**, active o desactive esta opción:
    1. Si quiere restringir quién puede iniciar reuniones instantáneas en un canal, cambie **Reunirse ahora en canales** a **Desactivado**.
    1. Si quiere restringir quién puede programar reuniones en un canal, cambie **Programación** de reuniones del canal a **Desactivado**.
1. Pulse **Guardar** en la parte inferior de la página.

## <a name="private-meetings"></a>Reuniones privadas

Si tiene requisitos de cumplimiento que exigen que solo personas específicas inicien reuniones privadas instantáneas y programen reuniones privadas, puede crear o actualizar las directivas de reuniones para restringir esta configuración. A continuación, puede crear una directiva independiente que se atribuye a los usuarios a los que desea iniciar reuniones instantáneas y programar reuniones privadas.

1. En el Centro de administración de Teams, vaya a **Directivas** >  de **reunión** de reuniones y elija la directiva que desea actualizar. Para crear una directiva, haga clic en **Agregar**.
1. En **General**, active o desactive esta opción:
    1. Si quiere restringir quién puede iniciar reuniones privadas instantáneas, cambie **Reunirse ahora en reuniones privadas** a **Desactivado**.
    1. Si quiere restringir quién puede programar reuniones privadas en un canal, cambie la programación de **reuniones privadas** y el **complemento de Outlook** a **Desactivado**.
1. Pulse **Guardar** en la parte inferior de la página.

## <a name="turning-off-meeting-policy-settings"></a>Desactivar la configuración de la directiva de reunión

Después de desactivar cualquiera de estas opciones de directiva de reunión, los usuarios asignados a la directiva no podrán iniciar ni programar reuniones de ese tipo. Los vínculos para unirse a la reunión y los identificadores de conferencia de todas las reuniones existentes de ese tipo que el usuario había iniciado o programado no funcionarán. (Las conversaciones, archivos, pizarras, grabaciones, transcripciones y otro contenido relacionado con la reunión se conservan y los usuarios pueden seguir accediendo a ellas).

Si se desactiva una configuración de directiva de reunión y se vuelve a activar para un usuario, todas las reuniones programadas previamente organizadas por el usuario se activarán y las personas podrán unirse a ellas mediante el vínculo para unirse a la reunión o por teléfono.

## <a name="related-topics"></a>Temas relacionados

[Cambiar la fecha de expiración de la reunión: controles del usuario final](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24#bkmk_view_change_expiration_date)

[Administración de directivas de reunión en Teams](meeting-policies-overview.md)

[Asignar directivas a los usuarios en Teams](policy-assignment-overview.md)

[Descripción de PowerShell para Teams](teams-powershell-overview.md)

[Límites y especificaciones para Microsoft Teams](/microsoftteams/limits-specifications-teams)
