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
# <a name="set-up-the-ringback-bot-for-direct-routing"></a><span data-ttu-id="53e8a-103">Configurar el bot de llamada para enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="53e8a-103">Set up the Ringback bot for Direct Routing</span></span>

<span data-ttu-id="53e8a-104">En este artículo se describe el bot de llamada, que puede usar para evitar silencios inesperados que se pueden producir cuando tarda más tiempo en establecerse en llamadas.</span><span class="sxs-lookup"><span data-stu-id="53e8a-104">This article describes the Ringback bot, which you can use to help avoid unexpected silences that can occur when it takes a longer time for calls to be established.</span></span> <span data-ttu-id="53e8a-105">El bot de llamada está disponible para enrutamiento directo en modo de omisión que no sea multimedia.</span><span class="sxs-lookup"><span data-stu-id="53e8a-105">The Ringback bot is available for Direct Routing in non-media bypass mode.</span></span>

<span data-ttu-id="53e8a-106">A veces, las llamadas entrantes de la red telefónica conmutada (RTC) a clientes de Teams pueden tardar más de lo esperado en establecerse.</span><span class="sxs-lookup"><span data-stu-id="53e8a-106">Sometimes inbound calls from the public switched telephone network (PSTN) to Teams clients can take longer than expected to be established.</span></span> <span data-ttu-id="53e8a-107">Esto puede ocurrir por varias razones.</span><span class="sxs-lookup"><span data-stu-id="53e8a-107">This can occur for various reasons.</span></span> <span data-ttu-id="53e8a-108">Cuando esto sucede, es posible que el autor de la llamada no oiga nada, que el cliente de Teams no suene y que algunos proveedores de telecomunicaciones cancelen la llamada.</span><span class="sxs-lookup"><span data-stu-id="53e8a-108">When this happens, the caller might not hear anything, the Teams client doesn't ring, and some telecommunications providers might cancel the call.</span></span>

<span data-ttu-id="53e8a-109">El bot de llamada le ayuda a evitar silencios inesperados que se pueden producir en este escenario.</span><span class="sxs-lookup"><span data-stu-id="53e8a-109">The Ringback bot helps to avoid unexpected silences that can occur in this scenario.</span></span> <span data-ttu-id="53e8a-110">Para las llamadas entrantes desde la RTC a los clientes de Teams, el bot de llamada reproduce una señal de audio distintiva al autor de la llamada para indicar que Teams está en proceso de establecer la llamada.</span><span class="sxs-lookup"><span data-stu-id="53e8a-110">For inbound calls from the PSTN to Teams clients, the Ringback bot plays a distinctive audio signal to the caller to indicate that Teams is in the process of establishing the call.</span></span>

> [!NOTE]
> <span data-ttu-id="53e8a-111">El bot de llamada genera medios anticipados desde el back-end de Teams.</span><span class="sxs-lookup"><span data-stu-id="53e8a-111">The Ringback bot generates early media from the Teams backend.</span></span> <span data-ttu-id="53e8a-112">En algunos países y regiones, es posible que se te a cobrara la llamada cuando empiece a fluir el contenido multimedia.</span><span class="sxs-lookup"><span data-stu-id="53e8a-112">In some countries and regions, you might be charged for the call when the media starts flowing.</span></span>

## <a name="configure-the-ringback-bot"></a><span data-ttu-id="53e8a-113">Configurar el bot de llamada</span><span class="sxs-lookup"><span data-stu-id="53e8a-113">Configure the Ringback bot</span></span>

<span data-ttu-id="53e8a-114">Use el cmdlet [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) para modificar una configuración del controlador de borde de sesión (SBC) definida anteriormente o el cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) para crear una nueva configuración de SBC, junto con el parámetro **GenerateRingingWhileLocatingUser** para configurar el bot ringback:</span><span class="sxs-lookup"><span data-stu-id="53e8a-114">Use the [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) cmdlet to modify a previously defined Session Border Controller (SBC) configuration, or the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlet to create a new SBC configuration, together with the **GenerateRingingWhileLocatingUser** parameter to configure the Ringback bot:</span></span>

- <span data-ttu-id="53e8a-115">Para activar el bot ringback, establezca el parámetro **GenerateRingingWhileLocatingUser** en **$True**.</span><span class="sxs-lookup"><span data-stu-id="53e8a-115">To turn on the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$True**.</span></span> <span data-ttu-id="53e8a-116">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="53e8a-116">This is the default value.</span></span> 

- <span data-ttu-id="53e8a-117">Para desactivar el bot ringback, establezca el parámetro **GenerateRingingWhileLocatingUser** en **$False**.</span><span class="sxs-lookup"><span data-stu-id="53e8a-117">To turn off the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$False**.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="53e8a-118">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="53e8a-118">Related topics</span></span>

- [<span data-ttu-id="53e8a-119">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="53e8a-119">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
