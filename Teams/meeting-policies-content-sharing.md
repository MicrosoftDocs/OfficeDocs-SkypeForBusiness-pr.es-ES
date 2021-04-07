---
title: Administrar directivas de reunión para compartir contenido
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
- ms.teamsadmincenter.meetingpolicies.contentsharing
- seo-marvel-apr2020
description: Aprenda a administrar la configuración de directiva de reunión en Teams para compartir contenido.
ms.openlocfilehash: 7b318ad0025d6c68b041c65d8fbb78cbfbc87723
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598772"
---
# <a name="meeting-policy-settings---content-sharing"></a>Configuración de la directiva de reunión. Uso compartido de contenido

<a name="bkcontentsharing"> </a>

En este artículo se describen las siguientes opciones de directiva de reunión relacionadas con el uso compartido de contenido:

- [Modo de uso compartido de pantalla](#screen-sharing-mode)
- [Permitir a un participante ceder o solicitar el control](#allow-a-participant-to-give-or-request-control)
- [Permitir a un participante externo ceder o solicitar el control](#allow-an-external-participant-to-give-or-request-control)
- [Permitir uso compartido en PowerPoint](#allow-powerpoint-sharing)
- [Permitir pizarra](#allow-whiteboard)
- [Permitir notas compartidas](#allow-shared-notes)

## <a name="screen-sharing-mode"></a>Modo de uso compartido de la pantalla

Esta configuración es una combinación de directivas por organizador y por usuario. Esta configuración controla si el escritorio y el uso compartido de ventanas están permitidos en la reunión del usuario. Los participantes de la reunión a los que no se les ha asignado ninguna directiva (por ejemplo, los participantes anónimos, invitados, B2B y federados) heredan la directiva del organizador de la reunión.

|Valor de configuración |Comportamiento  |
|---------|---------|
|**Toda la pantalla**    | Se permiten en la reunión el uso compartido de escritorio completo y de la aplicación |
|**Aplicación única**   | El uso compartido de aplicaciones se permite en la reunión        |
|**Deshabilitado**     |El uso compartido de la pantalla y el uso compartido de aplicaciones se desactivaron en la reunión.       |

Veamos el ejemplo siguiente.

|Usuario |Directiva de reuniones |Modo de uso compartido de la pantalla |
|---------|---------|---------|
|Daniela  | Global   | Toda la pantalla |
|Amanda   | Location1MeetingPolicy  | Deshabilitado |

Las reuniones hospedadas por Daniela permiten a los participantes de la reunión compartir toda la pantalla o una aplicación específica. Si Amanda se une a la reunión de Daniela, Amanda no puede compartir su pantalla ni una aplicación específica, ya que esta configuración de directiva está deshabilitada. En las reuniones hospedadas por Amanda no se permite a nadie compartir su pantalla o una sola aplicación, independientemente de la directiva de modo de uso compartido de la pantalla que se les asignó.  Por lo tanto, Daniela no puede compartir su pantalla ni una sola aplicación en las reuniones de Amanda.  

Actualmente, los usuarios no pueden reproducir vídeo ni compartir su pantalla en una reunión de Teams si usan Google Chrome.

## <a name="allow-a-participant-to-give-or-request-control"></a>Permitir a un participante ceder o solicitar el control

Esta configuración es una directiva por usuario. Esta configuración controla si el usuario puede ceder el control de la ventana o del escritorio compartido a otros participantes de la reunión. Para ceder el control, pase el cursor por la parte superior de la pantalla.

Si esta configuración está activada para el usuario, la opción **Ceder el control** se mostrará en la barra superior de una sesión compartida.

![Captura de pantalla que muestra la opción Ceder el control](media/meeting-policies-give-control.png)

Si la configuración está desactivada para el usuario, la **opción Dar control** no está disponible.

![Captura de pantalla que muestra que la opción Ceder el control no está disponible](media/meeting-policies-give-control-not-available.png)

Veamos el ejemplo siguiente.

|Usuario |Directiva de reuniones  |Permitir a un participante ceder o solicitar el control |
|---------|---------|---------|
|Daniela   | Global   | Activado       |
|Babek    | Location1MeetingPolicy        | Desactivado   |

Daniela puede dar el control del escritorio o ventana compartidos a otros participantes en una reunión organizada por Babek. Sin embargo, Babek no puede ceder el control a otros participantes.

Si desea usar PowerShell para controlar quién puede ceder el control o aceptar solicitudes de control, use el cmdlet AllowParticipantGiveRequestControl.

> [!NOTE]
> Para ceder y tomar el control del contenido compartido durante el uso compartido, ambas partes deben usar el cliente de escritorio de Teams. El control no es compatible cuando cualquiera de las partes ejecuta Teams en un explorador. Esto se debe a una limitación técnica que planeamos solucionar.

## <a name="allow-an-external-participant-to-give-or-request-control"></a>Permitir a un participante externo ceder o solicitar el control

Esta configuración es una directiva por usuario. Si una organización ha establecido esta directiva para un usuario no controla lo que los participantes externos pueden hacer, independientemente de lo que haya establecido el organizador de la reunión. Lo que controla este parámetro es si los participantes externos pueden recibir o solicitar el control de la pantalla que comparten, en función de lo que la persona que comparte haya establecido en las directivas de reuniones de su organización. Los participantes externos en reuniones de Teams se pueden categorizar de la siguiente forma:  

- Usuario anónimo
- Usuarios invitados  
- Usuario B2B
- Usuario federado  

Que los usuarios federados puedan ceder el control a los usuarios externos mientras realicen un uso compartido se controla mediante la configuración **Permitir a un participante externo ceder o solicitar el control** de su organización.

Si desea usar PowerShell para controlar si los participantes externos pueden ceder el control o aceptar solicitudes de control, use el cmdlet AllowExternalParticipantGiveRequestControl.

### <a name="allow-powerpoint-sharing"></a>Permitir uso compartido de PowerPoint

Esta es una directiva por usuario. Esta configuración controla si el usuario puede compartir diapositivas de PowerPoint en una reunión. Los usuarios externos, incluidos los usuarios anónimos, invitados y federados, heredan la directiva del organizador de la reunión.

Veamos el ejemplo siguiente.

|Usuario |Directiva de reuniones  |Permitir uso compartido de PowerPoint |
|---------|---------|---------|
|Daniela   | Global   | Activado       |
|Amanda   | Location1MeetingPolicy        | Desactivado   |

Amanda no puede compartir los conjuntos de diapositivas de PowerPoint en las reuniones aunque sea la organizadora. Daniela puede compartir conjuntos de diapositivas de PowerPoint incluso si la reunión está organizada por Amanda. Amanda puede ver los conjuntos de diapositivas de PowerPoint compartidos por otros usuarios de la reunión, aunque no pueda compartir conjuntos de diapositivas de PowerPoint.

## <a name="allow-whiteboard"></a>Permitir pizarra

Esta configuración es una directiva por usuario. Esta configuración controla si un usuario puede compartir la pizarra en una reunión. Los usuarios externos, incluidos los usuarios anónimos, B2B y federados, heredan la directiva del organizador de la reunión.

Veamos el ejemplo siguiente.

|Usuario |Directiva de reuniones  |Permitir pizarra|
|---------|---------|---------|
|Daniela   | Global   | Activado       |
|Amanda   | Location1MeetingPolicy        | Desactivado   |

Amanda no puede compartir la pizarra en una reunión, aunque sea la organizadora de la reunión. Daniela puede compartir la pizarra incluso si la reunión está organizada por Amanda.  

## <a name="allow-shared-notes"></a>Permitir notas compartidas

Esta configuración es una directiva por usuario. Esta configuración controla si un usuario puede crear y compartir notas en una reunión. Los usuarios externos, incluidos los usuarios anónimos, B2B y federados, heredan la directiva del organizador de la reunión. Actualmente, la pestaña **Notas de la reunión** solo es compatible con reuniones que tienen menos de 20 participantes.

Veamos el ejemplo siguiente.

|Usuario |Directiva de reuniones  |Permitir notas compartidas |
|---------|---------|---------|
|Daniela   | Global   | Activado       |
|Amanda   | Location1MeetingPolicy | Desactivado |

Daniela puede tomar notas en las reuniones de Amanda, pero Amanda no puede tomar notas en ninguna reunión.




## <a name="related-topics"></a>Temas relacionados

- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
- [Asignar directivas a los usuarios en Teams](assign-policies.md)
- [Quitar a los usuarios la directiva de reunión de Teams RestrictedAnonymousAccess](meeting-policies-restricted-anonymous-access.md)
