---
title: Hacer streaming Teams reuniones
author: mkbond007
ms.author: mabond
manager: serdars
ms.reviewer: suchakr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Obtenga información sobre cómo configurar y administrar el streaming para sus reuniones de Teams.
ms.openlocfilehash: 352a0c2e7a0584640e466b5e46456906e4912d00
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646349"
---
# <a name="stream-teams-meetings"></a>Hacer streaming Teams reuniones

Este artículo le ayudará a configurar el streaming para las reuniones de Teams.

## <a name="what-is-streaming-and-how-does-it-work"></a>¿Qué es el streaming y cómo funciona?

El streaming permite a su organización ampliar su alcance y ofrece a los asistentes a la reunión más opciones de reunión. Al habilitar la transmisión por secuencias, los organizadores pueden hacer streaming de reuniones y seminarios web a puntos de conexión externos proporcionando una dirección URL de protocolo de mensajería Real-Time (RTMP) y una clave para la aplicación de streaming personalizado integrada en Teams.

> [!NOTE]
> No puede transmitir eventos en directo.

## <a name="set-up-streaming-with-powershell"></a>Configurar el streaming con PowerShell

Puede configurar su organización para el streaming con PowerShell. Actualmente, esta directiva no está disponible en el centro de administración de Teams. La directiva por usuario se usa para especificar **quién** puede habilitar el streaming en directo. Está desactivado por defecto.

Puede usar el siguiente atributo en el cmdlet de Windows PowerShell **Set-CsTeamsMeetingPolicy** para configurar el streaming. Para obtener más información sobre el cmdlet, vea [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

- LiveStreamingMode

Establezca **LiveStreamingMode** en **Habilitado** para activar las capacidades de streaming para uno o más usuarios.

> [!IMPORTANT]
> Tiene que activar el registro de reuniones para que los organizadores puedan hacer streaming de seminarios web. Para obtener más información, vea [Configurar seminarios web](set-up-webinars.md).

### <a name="assign-the-policy"></a>Asignar la directiva

Para obtener más información sobre cómo asignar directivas con PowerShell, vea [Asignar directivas en Teams](policy-assignment-overview.md).

## <a name="related-topics"></a>Temas relacionados

- [Asignar directivas en Teams](policy-assignment-overview.md)
- [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Inicio rápido: reuniones, seminarios web y eventos en vivo](quick-start-meetings-live-events.md)