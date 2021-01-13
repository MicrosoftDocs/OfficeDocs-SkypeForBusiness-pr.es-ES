---
title: Administración de la configuración del grupo de respuesta en el nivel de aplicación en Skype Empresarial
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
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: Administrar la configuración de grupo de respuesta de nivel de aplicación, como la configuración de música en espera y devolución de llamada, en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: d41211b83e5ce0c27bb9efe1d3d15a6289ae38fe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830790"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a><span data-ttu-id="c5390-103">Administración de la configuración del grupo de respuesta en el nivel de aplicación en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="c5390-103">Managing application-level Response Group settings in Skype for Business</span></span>
 
<span data-ttu-id="c5390-104">Administrar la configuración de grupo de respuesta de nivel de aplicación, como la configuración de música en espera y devolución de llamada, en Skype Empresarial Server Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="c5390-104">Managing application-level Response Group settings, such as music-on-hold and ringback settings, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="c5390-105">La configuración de nivel de aplicación para la aplicación grupo de respuesta incluye la configuración de música en espera predeterminada, el archivo de audio de música en espera predeterminado, el período de gracia de devolución de llamada del agente y la configuración del contexto de llamada.</span><span class="sxs-lookup"><span data-stu-id="c5390-105">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="c5390-106">Solo puede definir un conjunto de opciones de configuración de nivel de aplicación por grupo.</span><span class="sxs-lookup"><span data-stu-id="c5390-106">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="c5390-107">Para ver la configuración de nivel de aplicación, use el cmdlet **Get-CsRgsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="c5390-107">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="c5390-108">Para modificar la configuración de nivel de aplicación, use el cmdlet **Set-CsRgsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="c5390-108">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="c5390-p102">La música en espera predeterminada se reproduce cuando se pone una llamada en espera solo si no se definió ninguna música en espera personalizada. El contexto de llamada está disponible solo para las colas asignadas a flujos de trabajo interactivos. Si se habilitó el contexto de llamada, un agente puede ver información como tiempo de espera del autor de la llamada, o preguntas y respuestas del flujo de trabajo, cuando se recibe la llamada.</span><span class="sxs-lookup"><span data-stu-id="c5390-p102">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined. Call context is available only for queues assigned to interactive workflows. If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>
  
### <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="c5390-112">Para modificar la configuración de nivel de aplicación de Grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="c5390-112">To modify Response Group application-level settings</span></span>

1. <span data-ttu-id="c5390-113">Inicie sesión como miembro del grupo RTCUniversalServerAdmins, o como miembro de un rol administrativo predefinido que admita el grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="c5390-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="c5390-114">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="c5390-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c5390-115">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="c5390-115">At the command line, run:</span></span>
    
   ```powershell
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    <span data-ttu-id="c5390-116">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c5390-116">For example:</span></span>
    
   ```powershell
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    <span data-ttu-id="c5390-p103">Para especificar un archivo de audio para usar como música en espera predeterminada, debe importar primero el archivo de audio. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c5390-p103">To specify an audio file to use as the default music on hold, you need to import the audio file first. For example:</span></span>
    
   ```powershell
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a><span data-ttu-id="c5390-119">Ver también</span><span class="sxs-lookup"><span data-stu-id="c5390-119">See also</span></span>

[<span data-ttu-id="c5390-120">Get-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="c5390-120">Get-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="c5390-121">Set-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="c5390-121">Set-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="c5390-122">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="c5390-122">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
