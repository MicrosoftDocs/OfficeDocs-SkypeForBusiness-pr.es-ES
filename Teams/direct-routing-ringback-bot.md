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
ms.openlocfilehash: ec1500d9e7d5896d1b4cd2414355602d7400591a
ms.sourcegitcommit: 207c58563b7b2aba274b067cf64242abd7a33c2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2020
ms.locfileid: "47405787"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a><span data-ttu-id="7df1a-103">Configurar el bot de timbre para el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="7df1a-103">Set up the Ringback bot for Direct Routing</span></span>

<span data-ttu-id="7df1a-104">En este artículo se describe el bot de timbre, que puede usar para evitar que se produzcan silencios inesperados cuando se tarda más tiempo en que se establezcan las llamadas.</span><span class="sxs-lookup"><span data-stu-id="7df1a-104">This article describes the Ringback bot, which you can use to help avoid unexpected silences that can occur when it takes a longer time for calls to be established.</span></span> <span data-ttu-id="7df1a-105">El bot de timbre está disponible para el enrutamiento directo en el modo de omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="7df1a-105">The Ringback bot is available for Direct Routing in non-media bypass mode.</span></span>

<span data-ttu-id="7df1a-106">A veces, las llamadas entrantes de la red de telefonía pública conmutada (RTC) a clientes de equipos pueden tardar más de lo esperado en establecerse.</span><span class="sxs-lookup"><span data-stu-id="7df1a-106">Sometimes inbound calls from the public switched telephone network (PSTN) to Teams clients can take longer than expected to be established.</span></span> <span data-ttu-id="7df1a-107">Esto puede ocurrir por varias razones.</span><span class="sxs-lookup"><span data-stu-id="7df1a-107">This can occur for various reasons.</span></span> <span data-ttu-id="7df1a-108">Cuando esto sucede, es posible que el autor de la llamada no oiga nada, el cliente de Teams no suene y la llamada puede ser cancelada por algunos proveedores de telecomunicaciones.</span><span class="sxs-lookup"><span data-stu-id="7df1a-108">When this happens, the caller might not hear anything, the Teams client doesn't ring, and the call might be canceled by some telecommunications providers.</span></span>

<span data-ttu-id="7df1a-109">El bot de timbre ayuda a evitar los silencios inesperados que se pueden producir en este escenario.</span><span class="sxs-lookup"><span data-stu-id="7df1a-109">The Ringback bot helps to avoid unexpected silences that can occur in this scenario.</span></span> <span data-ttu-id="7df1a-110">Para las llamadas entrantes desde la RTC a los clientes de Teams, el bot de timbre reproduce una señal de audio distintiva al autor de la llamada para indicar que Teams se encuentra en proceso de establecer la llamada.</span><span class="sxs-lookup"><span data-stu-id="7df1a-110">For inbound calls from the PSTN to Teams clients, the Ringback bot plays a distinctive audio signal to the caller to indicate that Teams is in the process of establishing the call.</span></span>

> [!NOTE]
> <span data-ttu-id="7df1a-111">El bot de timbre genera medios tempranos desde el back-end de Teams.</span><span class="sxs-lookup"><span data-stu-id="7df1a-111">The Ringback bot generates early media from the Teams backend.</span></span> <span data-ttu-id="7df1a-112">En algunos países y regiones, es posible que se te cobre la llamada cuando se inicia el flujo de medios.</span><span class="sxs-lookup"><span data-stu-id="7df1a-112">In some countries and regions, you might be charged for the call when the media starts flowing.</span></span>

## <a name="configure-the-ringback-bot"></a><span data-ttu-id="7df1a-113">Configurar el bot de timbre</span><span class="sxs-lookup"><span data-stu-id="7df1a-113">Configure the Ringback bot</span></span>

<span data-ttu-id="7df1a-114">Use los cmdlets [set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) y [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) junto con el parámetro **GenerateRingingWhileLocatingUser** para configurar el bot de timbre.</span><span class="sxs-lookup"><span data-stu-id="7df1a-114">Use the [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) and [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlets together with the **GenerateRingingWhileLocatingUser** parameter to configure the Ringback bot.</span></span>

<span data-ttu-id="7df1a-115">Para activar el bot de timbre, establezca el parámetro **GenerateRingingWhileLocatingUser** en **$true**.</span><span class="sxs-lookup"><span data-stu-id="7df1a-115">To turn on the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$True**.</span></span> <span data-ttu-id="7df1a-116">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7df1a-116">This is the default value.</span></span> 

<span data-ttu-id="7df1a-117">Para desactivar el bot de timbre, establezca el parámetro **GenerateRingingWhileLocatingUser** en **$false**.</span><span class="sxs-lookup"><span data-stu-id="7df1a-117">To turn off the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$False**.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="7df1a-118">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="7df1a-118">Related topics</span></span>

- [<span data-ttu-id="7df1a-119">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="7df1a-119">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
