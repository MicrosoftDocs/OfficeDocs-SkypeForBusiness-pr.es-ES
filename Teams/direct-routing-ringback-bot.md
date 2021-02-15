---
title: Configurar el bot de llamada para enrutamiento directo
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: Aprenda a usar el bot de llamada para enrutamiento directo para evitar silencios inesperados que se pueden producir cuando se establece una llamada.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91cea9183a85a804ca43464aab08f417ccaff1e8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827520"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a>Configurar el bot de llamada para enrutamiento directo

En este artículo se describe el bot de llamada, que puede usar para evitar silencios inesperados que se pueden producir cuando tarda más tiempo en establecerse en llamadas. El bot de llamada está disponible para enrutamiento directo en modo de omisión que no sea multimedia.

A veces, las llamadas entrantes de la red telefónica conmutada (RTC) a clientes de Teams pueden tardar más de lo esperado en establecerse. Esto puede ocurrir por varias razones. Cuando esto sucede, es posible que el autor de la llamada no oiga nada, que el cliente de Teams no suene y que algunos proveedores de telecomunicaciones cancelen la llamada.

El bot de llamada le ayuda a evitar silencios inesperados que se pueden producir en este escenario. Para las llamadas entrantes desde la RTC a los clientes de Teams, el bot de llamada reproduce una señal de audio distintiva al autor de la llamada para indicar que Teams está en proceso de establecer la llamada.

> [!NOTE]
> El bot de llamada genera medios anticipados desde el back-end de Teams. En algunos países y regiones, es posible que se te a cobrara la llamada cuando empiece a fluir el contenido multimedia.

## <a name="configure-the-ringback-bot"></a>Configurar el bot de llamada

Use el cmdlet [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) para modificar una configuración del controlador de borde de sesión (SBC) definida anteriormente o el cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) para crear una nueva configuración de SBC, junto con el parámetro **GenerateRingingWhileLocatingUser** para configurar el bot ringback:

- Para activar el bot ringback, establezca el parámetro **GenerateRingingWhileLocatingUser** en **$True**. Este es el valor predeterminado. 

- Para desactivar el bot ringback, establezca el parámetro **GenerateRingingWhileLocatingUser** en **$False**. 

## <a name="related-topics"></a>Temas relacionados

- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
