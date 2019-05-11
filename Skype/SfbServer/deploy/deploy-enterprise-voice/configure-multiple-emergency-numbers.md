---
title: Configurar varios números de emergencias en Skype para la empresa
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: Lea este tema para aprender a configurar varios números de emergencias en Skype para Business Server.
ms.openlocfilehash: cb4fbfcbcd1388c34a1babce4b2a5d122d711d2a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893066"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a><span data-ttu-id="fe8a9-103">Configurar varios números de emergencias en Skype para la empresa</span><span class="sxs-lookup"><span data-stu-id="fe8a9-103">Configure multiple emergency numbers in Skype for Business</span></span>

<span data-ttu-id="fe8a9-104">Lea este tema para aprender a configurar varios números de emergencias en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="fe8a9-104">Read this topic to learn how to configure multiple emergency numbers in Skype for Business Server.</span></span>

<span data-ttu-id="fe8a9-105">Skype para Business Server ahora admite varios números de emergencias para un cliente.</span><span class="sxs-lookup"><span data-stu-id="fe8a9-105">Skype for Business Server now supports multiple emergency numbers for a client.</span></span> <span data-ttu-id="fe8a9-106">Varios números de emergencia es una característica nueva que se introdujo en el de 2016 junio actualización acumulativa.</span><span class="sxs-lookup"><span data-stu-id="fe8a9-106">Multiple emergency numbers is a new feature introduced in the June 2016 Cumulative Update.</span></span> <span data-ttu-id="fe8a9-107">Antes de configurar su entorno para que admita varios números de emergencias, asegúrese de leer [planeación para varios números de emergencias en Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="fe8a9-107">Before you configure your environment to support multiple emergency numbers, be sure to read [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span></span>

> [!NOTE]
> <span data-ttu-id="fe8a9-108">Si aún no ha actualizado a la noviembre de 2016 actualización acumulativa, vea [actualizaciones de Skype para Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="fe8a9-108">If you have not yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span> <span data-ttu-id="fe8a9-109">Con la noviembre de 2016 actualización acumulativa, el número de números de emergencia de soporte aumenta comprendido entre 5 a 100.</span><span class="sxs-lookup"><span data-stu-id="fe8a9-109">With the November 2016 Cumulative Update, the number of support emergency numbers increases from 5 to 100.</span></span> 

## <a name="configure-multiple-emergency-numbers"></a><span data-ttu-id="fe8a9-110">Configurar varios números de emergencia</span><span class="sxs-lookup"><span data-stu-id="fe8a9-110">Configure multiple emergency numbers</span></span>

<span data-ttu-id="fe8a9-111">Para configurar varios números de emergencias, use el cmdlet New-CsEmergencyNumber y, a continuación, especifique el parámetro EmergencyNumbers con los cmdlets [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) y [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="fe8a9-111">To configure multiple emergency numbers, you use the New-CsEmergencyNumber cmdlet, and then you specify the EmergencyNumbers parameter with the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) and [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlets.</span></span> <span data-ttu-id="fe8a9-112">Para obtener una descripción completa de todos los ubicación directiva parámetros, como el uso de RTC y ubicación es necesario, vea [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="fe8a9-112">For a complete description of all the location policy parameters, such as PSTN usage and Location required, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span></span>

<span data-ttu-id="fe8a9-113">El siguiente comando crea un nuevo número de emergencia con la cadena de marcado 911 mediante el cmdlet New-CsEmergency:</span><span class="sxs-lookup"><span data-stu-id="fe8a9-113">The following command creates a new emergency number with dial string 911 by using the New-CsEmergency cmdlet:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 911 
```

<span data-ttu-id="fe8a9-114">El siguiente comando asocia el número con la directiva de ubicación indicada al especificar el parámetro EmergencyNumbers en el cmdlet Set-CsLocationPolicy:</span><span class="sxs-lookup"><span data-stu-id="fe8a9-114">The next command associates the number with the specified location policy by specifying the EmergencyNumbers parameter in the Set-CsLocationPolicy cmdlet:</span></span>

```
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a} 
```

<span data-ttu-id="fe8a9-115">En el siguiente ejemplo, el número de emergencia se crea con una sola máscara de marcado, 112:</span><span class="sxs-lookup"><span data-stu-id="fe8a9-115">In the next example, an emergency number is created with a single dial mask, 112:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112 
```

<span data-ttu-id="fe8a9-116">El comando siguiente crea un número de emergencia con varias máscaras de marcado:</span><span class="sxs-lookup"><span data-stu-id="fe8a9-116">The next command creates an emergency number with multiple dial masks:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
```

<span data-ttu-id="fe8a9-117">El siguiente ejemplo agrega varios números de emergencia con varias máscaras de marcado y, a continuación, asocia los números de emergencia con la directiva de ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="fe8a9-117">The next example adds multiple emergency numbers with multiple dial masks, and then associates the emergency numbers with the specified location policy:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b} 
```

<span data-ttu-id="fe8a9-118">El siguiente ejemplo configura varios números de emergencia de proveedores de servicios sanitarios que utilizan tanto 911 como 450: </span><span class="sxs-lookup"><span data-stu-id="fe8a9-118">The next example configures multiple emergency numbers for health care providers that use both 911 and 450:</span></span> 

```
> $a = New-CsEmergencyNumber -DialString 911 
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="fe8a9-119">El siguiente ejemplo configura varios números de emergencia de proveedores de servicios sanitarios en la ciudad de Londres:</span><span class="sxs-lookup"><span data-stu-id="fe8a9-119">The next example configures multiple emergency numbers for the city of London:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="fe8a9-120">El siguiente ejemplo configura varios números de emergencia de proveedores de servicios sanitarios en India:</span><span class="sxs-lookup"><span data-stu-id="fe8a9-120">The next example configures multiple emergency numbers for India:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101 
> $c = New-CsEmergencyNumber -DialString 102 
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

<span data-ttu-id="fe8a9-121">El siguiente ejemplo quita una entrada existente con la cadena de marcado 911 y las máscaras de marcado 112 y 999:</span><span class="sxs-lookup"><span data-stu-id="fe8a9-121">The next example removes an existing entry with Dial string 911 and Dial masks 112 and 999:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a} 
```


