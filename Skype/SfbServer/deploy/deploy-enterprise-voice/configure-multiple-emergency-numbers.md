---
title: Configurar varios números de emergencia en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Lea este tema para obtener información sobre cómo configurar varios números de emergencia en Skype empresarial Server.
ms.openlocfilehash: 81d3dbed919c936eb8a656d123f5c44e445044d7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027801"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a><span data-ttu-id="fce24-103">Configurar varios números de emergencia en Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="fce24-103">Configure multiple emergency numbers in Skype for Business</span></span>

<span data-ttu-id="fce24-104">Lea este tema para obtener información sobre cómo configurar varios números de emergencia en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="fce24-104">Read this topic to learn how to configure multiple emergency numbers in Skype for Business Server.</span></span>

<span data-ttu-id="fce24-105">Skype empresarial Server ahora admite varios números de emergencia para un cliente.</span><span class="sxs-lookup"><span data-stu-id="fce24-105">Skype for Business Server now supports multiple emergency numbers for a client.</span></span> <span data-ttu-id="fce24-106">Varios números de emergencia son una nueva característica que se presenta en la actualización acumulativa de junio de 2016.</span><span class="sxs-lookup"><span data-stu-id="fce24-106">Multiple emergency numbers is a new feature introduced in the June 2016 Cumulative Update.</span></span> <span data-ttu-id="fce24-107">Antes de configurar el entorno para que admita varios números de emergencia, asegúrese de leer [plan de varios números de emergencia en Skype empresarial Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="fce24-107">Before you configure your environment to support multiple emergency numbers, be sure to read [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span></span>

> [!NOTE]
> <span data-ttu-id="fce24-108">Si aún no ha actualizado a la actualización acumulativa de noviembre de 2016, consulte [actualizaciones para Skype empresarial Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="fce24-108">If you have not yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span> <span data-ttu-id="fce24-109">Con la actualización acumulativa de noviembre de 2016, el número de números de emergencia de soporte aumenta de 5 a 100.</span><span class="sxs-lookup"><span data-stu-id="fce24-109">With the November 2016 Cumulative Update, the number of support emergency numbers increases from 5 to 100.</span></span>

## <a name="configure-multiple-emergency-numbers"></a><span data-ttu-id="fce24-110">Configurar varios números de emergencia</span><span class="sxs-lookup"><span data-stu-id="fce24-110">Configure multiple emergency numbers</span></span>

<span data-ttu-id="fce24-111">Para configurar varios números de emergencia, use el cmdlet New-CsEmergencyNumber y, a continuación, especifique el parámetro EmergencyNumbers con los cmdlets [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) y [set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="fce24-111">To configure multiple emergency numbers, you use the New-CsEmergencyNumber cmdlet, and then you specify the EmergencyNumbers parameter with the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) and [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlets.</span></span> <span data-ttu-id="fce24-112">Para obtener una descripción completa de todos los parámetros de la Directiva de ubicación, como uso de RTC y ubicación necesaria, consulte [set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="fce24-112">For a complete description of all the location policy parameters, such as PSTN usage and Location required, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span></span>

<span data-ttu-id="fce24-113">El siguiente comando crea un nuevo número de emergencia con la cadena de marcado 911 mediante el cmdlet New-CsEmergency:</span><span class="sxs-lookup"><span data-stu-id="fce24-113">The following command creates a new emergency number with dial string 911 by using the New-CsEmergency cmdlet:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

<span data-ttu-id="fce24-114">El comando siguiente asocia el número con la Directiva de ubicación especificada especificando el parámetro EmergencyNumbers en el cmdlet Set-CsLocationPolicy:</span><span class="sxs-lookup"><span data-stu-id="fce24-114">The next command associates the number with the specified location policy by specifying the EmergencyNumbers parameter in the Set-CsLocationPolicy cmdlet:</span></span>

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

<span data-ttu-id="fce24-115">En el siguiente ejemplo, se crea un número de emergencia con una sola máscara de marcado, 112:</span><span class="sxs-lookup"><span data-stu-id="fce24-115">In the next example, an emergency number is created with a single dial mask, 112:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

<span data-ttu-id="fce24-116">El siguiente comando crea un número de emergencia con varias máscaras de marcado:</span><span class="sxs-lookup"><span data-stu-id="fce24-116">The next command creates an emergency number with multiple dial masks:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

<span data-ttu-id="fce24-117">En el siguiente ejemplo se agregan varios números de emergencia con varias máscaras de marcado y, a continuación, se asocian los números de emergencia con la Directiva de ubicación especificada:</span><span class="sxs-lookup"><span data-stu-id="fce24-117">The next example adds multiple emergency numbers with multiple dial masks, and then associates the emergency numbers with the specified location policy:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="fce24-118">El siguiente ejemplo configura varios números de emergencia para proveedores de servicios de salud que usan tanto 911 como 450:</span><span class="sxs-lookup"><span data-stu-id="fce24-118">The next example configures multiple emergency numbers for health care providers that use both 911 and 450:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="fce24-119">El siguiente ejemplo configura varios números de emergencia para la ciudad de Londres:</span><span class="sxs-lookup"><span data-stu-id="fce24-119">The next example configures multiple emergency numbers for the city of London:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="fce24-120">El siguiente ejemplo configura varios números de emergencia para la India:</span><span class="sxs-lookup"><span data-stu-id="fce24-120">The next example configures multiple emergency numbers for India:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

<span data-ttu-id="fce24-121">El siguiente ejemplo quita una entrada existente con la cadena de marcado 911 y las máscaras de marcado 112 y 999:</span><span class="sxs-lookup"><span data-stu-id="fce24-121">The next example removes an existing entry with Dial string 911 and Dial masks 112 and 999:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```
