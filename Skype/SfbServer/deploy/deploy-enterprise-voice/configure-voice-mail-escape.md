---
title: Configurar escape de correo de voz de Skype para la empresa
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Resumen: Obtenga información sobre cómo configurar escape de correo de voz de Skype para Business Server mediante el Skype para Shell de administración de servidor empresarial.'
ms.openlocfilehash: 4d93f188b137c3ecea014b8e407456e20195cbe1
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23261367"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a><span data-ttu-id="34e64-103">Configurar escape de correo de voz de Skype para la empresa</span><span class="sxs-lookup"><span data-stu-id="34e64-103">Configure voice mail escape in Skype for Business</span></span>

<span data-ttu-id="34e64-104">**Resumen:** Obtenga información sobre cómo configurar escape de correo de voz de Skype para Business Server mediante el Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="34e64-104">**Summary:** Learn how to configure voice mail escape in Skype for Business Server by using the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="34e64-105">Cuando un usuario configura las llamadas simultáneas a un teléfono móvil, un autor de la llamada normalmente se enrutan al correo de voz personal del usuario si el teléfono móvil está desactivado, fuera de la energía de la batería o fuera del intervalo.</span><span class="sxs-lookup"><span data-stu-id="34e64-105">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user's personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="34e64-106">Con Skype para Business Server, los usuarios pueden optar por hacer relacionados con el negocio llamadas enrutadas a su sistema de correo de voz corporativo.</span><span class="sxs-lookup"><span data-stu-id="34e64-106">With Skype for Business Server , users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="34e64-107">Específicamente, puede configurarse un temporizador, y si la llamada se ha atendido por correo de voz del proveedor dentro del intervalo de tiempo definido, Skype para Business Server se desconectará del sistema de correo de voz del proveedor (y correo de voz personal del usuario), mientras el usuario los extremos restantes en el sistema corporativo continuarán llamar a.</span><span class="sxs-lookup"><span data-stu-id="34e64-107">Specifically, a timer can be configured, and if the call is answered by the carrier's voice mail within the range of time defined, Skype for Business Server will disconnect from the carrier's voice mail system (and the user's personal voice mail), while the user's remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="34e64-108">De este modo, el autor de la llamada se enruta automáticamente al correo de voz corporativa del usuario.</span><span class="sxs-lookup"><span data-stu-id="34e64-108">This way, the caller is automatically routed to the user's corporate voice mail.</span></span>

<span data-ttu-id="34e64-109">Esta configuración se realiza mediante la Skype para cmdlet del Shell de administración de servidor empresarial, **Set-CsVoicePolicy**, en el nivel de directiva de voz, con los siguientes parámetros.</span><span class="sxs-lookup"><span data-stu-id="34e64-109">This configuration is performed using the Skype for Business Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

### <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="34e64-110">Para configurar el escape de correo de voz</span><span class="sxs-lookup"><span data-stu-id="34e64-110">To configure voice mail escape</span></span>

1. <span data-ttu-id="34e64-111">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="34e64-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="34e64-112">Especifique los siguientes parámetros en **Set-CsVoicePolicy**:</span><span class="sxs-lookup"><span data-stu-id="34e64-112">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>

   - <span data-ttu-id="34e64-113">**EnableVoicemailEscapeTimer**: habilita o deshabilita el temporizador de escape.</span><span class="sxs-lookup"><span data-stu-id="34e64-113">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>

   - <span data-ttu-id="34e64-p102">**PSTNVoicemailEscapeTimer**: especifica el valor de tiempo de espera en milisegundos. El valor predeterminado es 1500 milisegundos y puede variar de 0 a 8000 milisegundos.</span><span class="sxs-lookup"><span data-stu-id="34e64-p102">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds. The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

## <a name="example"></a><span data-ttu-id="34e64-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="34e64-116">Example</span></span>

```
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a><span data-ttu-id="34e64-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="34e64-117">See also</span></span>

[<span data-ttu-id="34e64-118">Configuración de directivas de voz y registros de uso de RTC para autorizar privilegios y características de llamada</span><span class="sxs-lookup"><span data-stu-id="34e64-118">Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges</span></span>](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

