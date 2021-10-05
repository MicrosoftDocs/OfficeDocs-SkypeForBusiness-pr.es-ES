---
title: Transmitir Teams reuniones
author: KarliStites
ms.author: kastites
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
description: Obtenga información sobre cómo configurar y administrar el streaming para sus Teams reuniones.
ms.openlocfilehash: d5cc83e1ea75d1c28ea4c30bac7cdabc4e60143d
ms.sourcegitcommit: 99503baa8b5183972caa8fe61e92a362213599d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2021
ms.locfileid: "60127554"
---
# <a name="stream-teams-meetings"></a>Transmitir Teams reuniones

Este artículo le ayudará a configurar el streaming para Teams reuniones.

## <a name="what-is-streaming-and-how-does-it-work"></a>¿Qué es el streaming y cómo funciona?

El streaming permite a su organización expandir su alcance y ofrece a los asistentes a la reunión más opciones de reunión. Al habilitar el streaming, los organizadores pueden transmitir reuniones y seminarios web a puntos de conexión externos proporcionando una dirección URL del Protocolo de mensajería de Real-Time (RTMP) y una clave para la aplicación de streaming personalizada integrada en Teams.

> [!NOTE]
> No puede transmitir eventos en directo.

## <a name="set-up-streaming-with-powershell"></a>Configurar el streaming con PowerShell

Puede configurar su organización para el streaming con PowerShell. Actualmente, esta directiva no está disponible en el centro Teams administración. La directiva por usuario se usa para especificar **quién** puede habilitar la transmisión en directo. Está desactivado por defecto.

Puede usar el siguiente atributo dentro del cmdlet **Set-CsTeamsMeetingPolicy Windows PowerShell set-CsTeamsMeetingPolicy** para configurar la transmisión por secuencias. Para obtener más información sobre el cmdlet, vea [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

- LiveStreamingMode

Establezca **LiveStreamingMode** en **Habilitado** para activar las capacidades de streaming para uno o varios usuarios.

> [!IMPORTANT]
> Debe activar el registro de la reunión para que los organizadores puedan transmitir seminarios web. Para obtener más información, vea [Configurar seminarios web.](set-up-webinars.md)

### <a name="assign-the-policy"></a>Asignar la directiva

Para obtener más información sobre cómo asignar directivas con PowerShell, vea Asignar [directivas en Teams](policy-assignment-overview.md).

## <a name="related-topics"></a>Temas relacionados

- [Asignar directivas en Teams](policy-assignment-overview.md)
- [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Inicio rápido: reuniones, seminarios web y eventos en vivo](quick-start-meetings-live-events.md)