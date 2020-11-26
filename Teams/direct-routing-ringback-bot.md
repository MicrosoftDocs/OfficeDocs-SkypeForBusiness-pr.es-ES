---
title: Configurar el bot de timbre para el enrutamiento directo
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: Aprenda a usar el bot de timbre para el enrutamiento directo para evitar que se produzcan silencios inesperados cuando se establezca una llamada.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 26738002ab333d2490ef0dac5674a1f7cdc19efd
ms.sourcegitcommit: 8974cd7a693bc879fed8222f551fd7ce3205dd65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "49420960"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a>Configurar el bot de timbre para el enrutamiento directo

En este artículo se describe el bot de timbre, que puede usar para evitar que se produzcan silencios inesperados cuando se tarda más tiempo en que se establezcan las llamadas. El bot de timbre está disponible para el enrutamiento directo en el modo de omisión de medios.

A veces, las llamadas entrantes de la red de telefonía pública conmutada (RTC) a clientes de equipos pueden tardar más de lo esperado en establecerse. Esto puede ocurrir por varias razones. Cuando esto sucede, es posible que la persona que llama no oiga nada, el cliente de su equipo no suene y algunos proveedores de telecomunicaciones podrían cancelar la llamada.

El bot de timbre ayuda a evitar los silencios inesperados que se pueden producir en este escenario. Para las llamadas entrantes desde la RTC a los clientes de Teams, el bot de timbre reproduce una señal de audio distintiva al autor de la llamada para indicar que Teams se encuentra en proceso de establecer la llamada.

> [!NOTE]
> El bot de timbre genera medios tempranos desde el back-end de Teams. En algunos países y regiones, es posible que se te cobre la llamada cuando se inicia el flujo de medios.

## <a name="configure-the-ringback-bot"></a>Configurar el bot de timbre

Use el cmdlet [set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) para modificar una configuración de controlador de borde de sesión (SBC) definida previamente, o el cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) para crear una nueva configuración de SBC, junto con el parámetro **GenerateRingingWhileLocatingUser** para configurar el bot de timbre:

- Para activar el bot de timbre, establezca el parámetro **GenerateRingingWhileLocatingUser** en **$true**. Este es el valor predeterminado. 

- Para desactivar el bot de timbre, establezca el parámetro **GenerateRingingWhileLocatingUser** en **$false**. 

## <a name="related-topics"></a>Temas relacionados

- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
