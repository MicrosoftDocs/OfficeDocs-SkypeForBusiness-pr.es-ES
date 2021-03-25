---
title: Configurar varios números de emergencia en Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: Lea este tema para obtener información sobre cómo configurar varios números de emergencia en Skype Empresarial Server.
ms.openlocfilehash: dc05e94e88b371bb9ee22568eff567e758311233
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111896"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a><span data-ttu-id="3833d-103">Configurar varios números de emergencia en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="3833d-103">Configure multiple emergency numbers in Skype for Business</span></span>

<span data-ttu-id="3833d-104">Lea este tema para obtener información sobre cómo configurar varios números de emergencia en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="3833d-104">Read this topic to learn how to configure multiple emergency numbers in Skype for Business Server.</span></span>

<span data-ttu-id="3833d-105">Skype Empresarial Server ahora admite varios números de emergencia para un cliente.</span><span class="sxs-lookup"><span data-stu-id="3833d-105">Skype for Business Server now supports multiple emergency numbers for a client.</span></span> <span data-ttu-id="3833d-106">Varios números de emergencia es una nueva característica que se introdujo en la actualización acumulativa de junio de 2016.</span><span class="sxs-lookup"><span data-stu-id="3833d-106">Multiple emergency numbers is a new feature introduced in the June 2016 Cumulative Update.</span></span> <span data-ttu-id="3833d-107">Antes de configurar el entorno para admitir varios números de emergencia, asegúrese de leer [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="3833d-107">Before you configure your environment to support multiple emergency numbers, be sure to read [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3833d-108">Si aún no ha actualizado a la actualización acumulativa de noviembre de 2016, vea Actualizaciones de [Skype Empresarial Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="3833d-108">If you have not yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span> <span data-ttu-id="3833d-109">Con la actualización acumulativa de noviembre de 2016, el número de números de emergencia de soporte aumenta de 5 a 100.</span><span class="sxs-lookup"><span data-stu-id="3833d-109">With the November 2016 Cumulative Update, the number of support emergency numbers increases from 5 to 100.</span></span>

## <a name="configure-multiple-emergency-numbers"></a><span data-ttu-id="3833d-110">Configurar varios números de emergencia</span><span class="sxs-lookup"><span data-stu-id="3833d-110">Configure multiple emergency numbers</span></span>

<span data-ttu-id="3833d-111">Para configurar varios números de emergencia, use el cmdlet New-CsEmergencyNumber y, a continuación, especifique el parámetro EmergencyNumbers con los [cmdlets New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) y [Set-CsLocationPolicy.](/powershell/module/skype/set-cslocationpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="3833d-111">To configure multiple emergency numbers, you use the New-CsEmergencyNumber cmdlet, and then you specify the EmergencyNumbers parameter with the [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) and [Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlets.</span></span> <span data-ttu-id="3833d-112">Para obtener una descripción completa de todos los parámetros de directiva de ubicación, como el uso de RTC y la ubicación necesaria, vea [Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="3833d-112">For a complete description of all the location policy parameters, such as PSTN usage and Location required, see [Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span></span>

<span data-ttu-id="3833d-113">El siguiente comando crea un nuevo número de emergencia con la cadena de marcado 911 mediante el cmdlet New-CsEmergency llamada:</span><span class="sxs-lookup"><span data-stu-id="3833d-113">The following command creates a new emergency number with dial string 911 by using the New-CsEmergency cmdlet:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

<span data-ttu-id="3833d-114">El siguiente comando asocia el número con la directiva de ubicación especificada especificando el parámetro EmergencyNumbers en el cmdlet Set-CsLocationPolicy datos:</span><span class="sxs-lookup"><span data-stu-id="3833d-114">The next command associates the number with the specified location policy by specifying the EmergencyNumbers parameter in the Set-CsLocationPolicy cmdlet:</span></span>

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

<span data-ttu-id="3833d-115">En el siguiente ejemplo, se crea un número de emergencia con una sola máscara de marcado, 112:</span><span class="sxs-lookup"><span data-stu-id="3833d-115">In the next example, an emergency number is created with a single dial mask, 112:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

<span data-ttu-id="3833d-116">El siguiente comando crea un número de emergencia con varias máscaras de marcado:</span><span class="sxs-lookup"><span data-stu-id="3833d-116">The next command creates an emergency number with multiple dial masks:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

<span data-ttu-id="3833d-117">En el siguiente ejemplo se agregan varios números de emergencia con varias máscaras de marcado y, a continuación, se asocian los números de emergencia con la directiva de ubicación especificada:</span><span class="sxs-lookup"><span data-stu-id="3833d-117">The next example adds multiple emergency numbers with multiple dial masks, and then associates the emergency numbers with the specified location policy:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="3833d-118">En el siguiente ejemplo se configuran varios números de emergencia para los proveedores de atención médica que usan 911 y 450:</span><span class="sxs-lookup"><span data-stu-id="3833d-118">The next example configures multiple emergency numbers for health care providers that use both 911 and 450:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="3833d-119">En el siguiente ejemplo se configuran varios números de emergencia para la ciudad de Londres:</span><span class="sxs-lookup"><span data-stu-id="3833d-119">The next example configures multiple emergency numbers for the city of London:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="3833d-120">En el siguiente ejemplo se configuran varios números de emergencia para India:</span><span class="sxs-lookup"><span data-stu-id="3833d-120">The next example configures multiple emergency numbers for India:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

<span data-ttu-id="3833d-121">En el siguiente ejemplo se quita una entrada existente con la cadena de marcado 911 y las máscaras de marcado 112 y 999:</span><span class="sxs-lookup"><span data-stu-id="3833d-121">The next example removes an existing entry with Dial string 911 and Dial masks 112 and 999:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```