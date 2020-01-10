---
title: Configurar el escape del correo de voz en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Resumen: Aprenda a configurar el escape del correo de voz en Skype empresarial Server mediante el shell de administración de Skype empresarial Server.'
ms.openlocfilehash: 27f283f4bfb64aa950bd9e72a9d6fdc17df91ba0
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001220"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a><span data-ttu-id="fe715-103">Configurar el escape del correo de voz en Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="fe715-103">Configure voice mail escape in Skype for Business</span></span>

<span data-ttu-id="fe715-104">**Resumen:** Obtenga información sobre cómo configurar el escape del correo de voz en Skype empresarial Server mediante el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="fe715-104">**Summary:** Learn how to configure voice mail escape in Skype for Business Server by using the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="fe715-105">Cuando un usuario configura la llamada simultánea a un teléfono móvil, normalmente se redirigirá al correo de voz personal del usuario si el teléfono móvil está apagado, agotado la batería o está fuera de alcance.</span><span class="sxs-lookup"><span data-stu-id="fe715-105">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user's personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="fe715-106">Con Skype empresarial Server, los usuarios pueden optar por hacer que las llamadas relacionadas con el negocio se dirijan a su sistema de correo de voz empresarial.</span><span class="sxs-lookup"><span data-stu-id="fe715-106">With Skype for Business Server , users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="fe715-107">En concreto, se puede configurar un temporizador y, si el correo de voz del transportista responde a la llamada dentro del intervalo de tiempo definido, Skype empresarial Server se desconectará del sistema de correo de voz del transportista (y del correo de voz personal del usuario) mientras el usuario los puntos de conexión restantes en el sistema corporativo continúan sonando.</span><span class="sxs-lookup"><span data-stu-id="fe715-107">Specifically, a timer can be configured, and if the call is answered by the carrier's voice mail within the range of time defined, Skype for Business Server will disconnect from the carrier's voice mail system (and the user's personal voice mail), while the user's remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="fe715-108">De esta manera, la persona que llama se dirige automáticamente al correo de voz corporativo del usuario.</span><span class="sxs-lookup"><span data-stu-id="fe715-108">This way, the caller is automatically routed to the user's corporate voice mail.</span></span>

<span data-ttu-id="fe715-109">Esta configuración se realiza con el cmdlet del shell de administración de Skype empresarial, **set-CsVoicePolicy**, en el nivel de la Directiva de voz, con los siguientes parámetros.</span><span class="sxs-lookup"><span data-stu-id="fe715-109">This configuration is performed using the Skype for Business Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

### <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="fe715-110">Para configurar el escape de correo de voz</span><span class="sxs-lookup"><span data-stu-id="fe715-110">To configure voice mail escape</span></span>

1. <span data-ttu-id="fe715-111">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="fe715-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="fe715-112">Especifique los siguientes parámetros en **Set-CsVoicePolicy**:</span><span class="sxs-lookup"><span data-stu-id="fe715-112">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>

   - <span data-ttu-id="fe715-113">**EnableVoicemailEscapeTimer**: habilita o deshabilita el temporizador de escape.</span><span class="sxs-lookup"><span data-stu-id="fe715-113">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>

   - <span data-ttu-id="fe715-p102">**PSTNVoicemailEscapeTimer**: especifica el valor de tiempo de espera en milisegundos. El valor predeterminado es 1500 milisegundos y puede variar de 0 a 8000 milisegundos.</span><span class="sxs-lookup"><span data-stu-id="fe715-p102">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds. The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

## <a name="example"></a><span data-ttu-id="fe715-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fe715-116">Example</span></span>

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a><span data-ttu-id="fe715-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe715-117">See also</span></span>

[<span data-ttu-id="fe715-118">Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges</span><span class="sxs-lookup"><span data-stu-id="fe715-118">Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges</span></span>](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

