---
title: Configurar el escape de correo de voz en Skype Empresarial
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
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Resumen: obtenga información sobre cómo configurar el escape de correo de voz en Skype Empresarial Server mediante el Shell de administración de Skype Empresarial Server.'
ms.openlocfilehash: c6326360a0e49715feb7e9f9c3c123ec42b9c330
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824930"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a><span data-ttu-id="3c2c7-103">Configurar el escape de correo de voz en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="3c2c7-103">Configure voice mail escape in Skype for Business</span></span>

<span data-ttu-id="3c2c7-104">**Resumen:** Obtenga información sobre cómo configurar el escape de correo de voz en Skype Empresarial Server mediante el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="3c2c7-104">**Summary:** Learn how to configure voice mail escape in Skype for Business Server by using the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="3c2c7-105">Cuando un usuario configura llamadas simultáneas a un teléfono móvil, el autor de la llamada normalmente se enruta al correo de voz personal del usuario si el teléfono móvil está apagado, sin batería o fuera del alcance.</span><span class="sxs-lookup"><span data-stu-id="3c2c7-105">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user's personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="3c2c7-106">Con Skype Empresarial Server, los usuarios pueden optar por que las llamadas relacionadas con la empresa se enruten a su sistema de correo de voz corporativo.</span><span class="sxs-lookup"><span data-stu-id="3c2c7-106">With Skype for Business Server , users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="3c2c7-107">Específicamente, se puede configurar un temporizador y, si el correo de voz del operador responde a la llamada dentro del intervalo de tiempo definido, Skype Empresarial Server se desconectará del sistema de correo de voz del operador (y del correo de voz personal del usuario), mientras que los extremos restantes del usuario en el sistema corporativo seguirán sonando.</span><span class="sxs-lookup"><span data-stu-id="3c2c7-107">Specifically, a timer can be configured, and if the call is answered by the carrier's voice mail within the range of time defined, Skype for Business Server will disconnect from the carrier's voice mail system (and the user's personal voice mail), while the user's remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="3c2c7-108">De este modo, el autor de la llamada se enruta automáticamente al correo de voz corporativo del usuario.</span><span class="sxs-lookup"><span data-stu-id="3c2c7-108">This way, the caller is automatically routed to the user's corporate voice mail.</span></span>

<span data-ttu-id="3c2c7-109">Esta configuración se realiza con el cmdlet del Shell de administración de Skype Empresarial Server, **Set-CsVoicePolicy,** en el nivel de directiva de voz, con los siguientes parámetros.</span><span class="sxs-lookup"><span data-stu-id="3c2c7-109">This configuration is performed using the Skype for Business Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

### <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="3c2c7-110">Para configurar el escape de correo de voz</span><span class="sxs-lookup"><span data-stu-id="3c2c7-110">To configure voice mail escape</span></span>

1. <span data-ttu-id="3c2c7-111">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** en Skype Empresarial **2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="3c2c7-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="3c2c7-112">Especificar los siguientes parámetros en **Set-CsVoicePolicy**:</span><span class="sxs-lookup"><span data-stu-id="3c2c7-112">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>

   - <span data-ttu-id="3c2c7-113">**EnableVoicemailEscapeTimer**: habilita o deshabilita el temporizador de escape.</span><span class="sxs-lookup"><span data-stu-id="3c2c7-113">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>

   - <span data-ttu-id="3c2c7-p102">**PSTNVoicemailEscapeTimer**: especifica el valor de tiempo de espera en milisegundos. El valor predeterminado es 1500 milisegundos y puede variar de 0 a 8000 milisegundos.</span><span class="sxs-lookup"><span data-stu-id="3c2c7-p102">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds. The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

## <a name="example"></a><span data-ttu-id="3c2c7-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3c2c7-116">Example</span></span>

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a><span data-ttu-id="3c2c7-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c2c7-117">See also</span></span>

[<span data-ttu-id="3c2c7-118">Configuración de directivas de voz y registros de uso de RTC para autorizar características y privilegios de llamada</span><span class="sxs-lookup"><span data-stu-id="3c2c7-118">Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges</span></span>](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

