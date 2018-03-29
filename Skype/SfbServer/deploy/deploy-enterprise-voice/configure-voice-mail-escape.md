---
title: Configurar escape de buzón de voz en Skype Empresarial 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Resumen: Conozca cómo configurar escape del correo de voz de Skype para Business Server 2015 utilizando el Skype para el Shell de administración de servidor empresarial.'
ms.openlocfilehash: 07586f38127b2831ecdb2900f005ff43b4184292
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-voice-mail-escape-in-skype-for-business-2015"></a><span data-ttu-id="942d9-103">Configurar escape de buzón de voz en Skype Empresarial 2015</span><span class="sxs-lookup"><span data-stu-id="942d9-103">Configure voice mail escape in Skype for Business 2015</span></span>
 
<span data-ttu-id="942d9-104">**Resumen:** Aprenda a configurar escape del correo de voz de Skype para Business Server 2015 utilizando el Skype para el Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="942d9-104">**Summary:** Learn how to configure voice mail escape in Skype for Business Server 2015 by using the Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="942d9-105">Cuando un usuario configura las llamadas simultáneas a un teléfono móvil, un llamador normalmente se enrutarán al correo de voz personal del usuario si el teléfono móvil está apagado, sin batería o fuera del intervalo.</span><span class="sxs-lookup"><span data-stu-id="942d9-105">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user's personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="942d9-106">Con Skype para Business Server, los usuarios pueden optar por tener laboral llamadas enrutadas a su sistema de correo de voz corporativa.</span><span class="sxs-lookup"><span data-stu-id="942d9-106">With Skype for Business Server , users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="942d9-107">Específicamente, puede configurarse un temporizador, y si la llamada sea contestada por correo de voz del transportista en el intervalo de tiempo definido, Skype para Business Server se desconectará del sistema de correo de voz del transportista (y correo de voz personal del usuario), mientras el usuario los extremos restantes del sistema corporativo continuarán al anillo.</span><span class="sxs-lookup"><span data-stu-id="942d9-107">Specifically, a timer can be configured, and if the call is answered by the carrier's voice mail within the range of time defined, Skype for Business Server will disconnect from the carrier's voice mail system (and the user's personal voice mail), while the user's remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="942d9-108">De este modo, el autor de la llamada se enruta automáticamente al correo de voz corporativa del usuario.</span><span class="sxs-lookup"><span data-stu-id="942d9-108">This way, the caller is automatically routed to the user's corporate voice mail.</span></span>
  
<span data-ttu-id="942d9-109">Esta configuración se realiza mediante el Skype cmdlet del Shell de administración de servidor de Business, **Conjunto CsVoicePolicy**, en el nivel de directiva de voz, con los siguientes parámetros.</span><span class="sxs-lookup"><span data-stu-id="942d9-109">This configuration is performed using the Skype for Business Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>
  
### <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="942d9-110">Para configurar el escape de correo de voz</span><span class="sxs-lookup"><span data-stu-id="942d9-110">To configure voice mail escape</span></span>

1. <span data-ttu-id="942d9-111">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="942d9-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="942d9-112">Especifique los siguientes parámetros en **Set-CsVoicePolicy**:</span><span class="sxs-lookup"><span data-stu-id="942d9-112">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>
    
   - <span data-ttu-id="942d9-113">**EnableVoicemailEscapeTimer**: habilita o deshabilita el temporizador de escape.</span><span class="sxs-lookup"><span data-stu-id="942d9-113">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>
    
   - <span data-ttu-id="942d9-p102">**PSTNVoicemailEscapeTimer**: especifica el valor de tiempo de espera en milisegundos. El valor predeterminado es 1500 milisegundos y puede variar de 0 a 8000 milisegundos.</span><span class="sxs-lookup"><span data-stu-id="942d9-p102">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds. The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>
    
## <a name="example"></a><span data-ttu-id="942d9-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="942d9-116">Example</span></span>

```
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000

Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

```

## <a name="see-also"></a><span data-ttu-id="942d9-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="942d9-117">See also</span></span>

#### 

[<span data-ttu-id="942d9-118">Configuración de directivas de voz y los registros de uso PSTN para autorizar los privilegios y las funciones de llamada</span><span class="sxs-lookup"><span data-stu-id="942d9-118">Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges</span></span>](http://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

