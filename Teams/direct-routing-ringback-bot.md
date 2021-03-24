---
title: Configurar el bot Devolución de llamada para enrutamiento directo
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo usar el bot Devolución de llamada para enrutamiento directo para evitar silencios inesperados que se pueden producir cuando se establece una llamada.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ec53f1d4f9cd21d3b28c87c07c1bc91d48b9b58
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098426"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a>Configurar el bot Devolución de llamada para enrutamiento directo

En este artículo se describe el bot Devolución de llamada, que puede usar para ayudar a evitar silencios inesperados que se pueden producir cuando se tarda más tiempo en establecerse las llamadas. El bot Devolución de llamada está disponible para enrutamiento directo en modo de omisión no multimedia.

A veces, las llamadas entrantes de la red telefónica conmutada (RTC) a los clientes de Teams pueden tardar más de lo esperado en establecerse. Esto puede ocurrir por varios motivos. Cuando esto sucede, es posible que el autor de la llamada no oiga nada, que el cliente de Teams no suene y que algunos proveedores de telecomunicaciones puedan cancelar la llamada.

El bot Devolución de llamada ayuda a evitar silencios inesperados que se pueden producir en este escenario. Para las llamadas entrantes desde la RTC a los clientes de Teams, el bot Devolución reproduce una señal de audio distinta al autor de la llamada para indicar que Teams está en el proceso de establecer la llamada.

> [!NOTE]
> El bot Devolución de llamada genera medios anticipados desde el back-end de Teams. En algunos países y regiones, es posible que se le cobrará por la llamada cuando los medios empiecen a fluir.

## <a name="configure-the-ringback-bot"></a>Configurar el bot Devolución de llamada

Use el cmdlet [Set-CsOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) para modificar una configuración definida previamente del Controlador de borde de sesión (SBC) o el cmdlet [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) para crear una nueva configuración de SBC, junto con el parámetro **GenerateRingingWhileLocatingUser** para configurar el bot Devolución de llamada:

- Para activar el bot Devolución de llamada, establezca el parámetro **GenerateRingingWhileLocatingUser** en **$True**. Este es el valor predeterminado. 

- Para desactivar el bot Devolución de llamada, establezca el parámetro **GenerateRingingWhileLocatingUser** **en $False**. 

## <a name="related-topics"></a>Temas relacionados

- [Descripción de PowerShell para Teams](teams-powershell-overview.md)