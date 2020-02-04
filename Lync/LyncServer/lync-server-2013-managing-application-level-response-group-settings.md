---
title: 'Lync Server 2013: administración de la configuración de grupo de respuesta de nivel de aplicación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing application-level Response Group settings
ms:assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721843(v=OCS.15)
ms:contentKeyID: 49733776
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffce659c2c4dc6c91ba4e4935b72c15e4cef4da5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733250"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-application-level-response-group-settings-in-lync-server-2013"></a><span data-ttu-id="cf1a6-102">Administrar la configuración de grupo de respuesta de nivel de aplicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf1a6-102">Managing application-level Response Group settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf1a6-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="cf1a6-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="cf1a6-104">La configuración de nivel de aplicación para la aplicación de grupo de respuesta incluye la configuración predeterminada de música en espera, el archivo de audio de música activada predeterminada, el período de gracia de timbre de agente y la configuración de contexto de llamada.</span><span class="sxs-lookup"><span data-stu-id="cf1a6-104">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="cf1a6-105">Solo puede definir un conjunto de opciones de configuración de la aplicación por grupo.</span><span class="sxs-lookup"><span data-stu-id="cf1a6-105">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="cf1a6-106">Para ver la configuración de la aplicación, use el cmdlet **Get-CsRgsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="cf1a6-106">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="cf1a6-107">Para modificar la configuración de la aplicación, use el cmdlet **Set-CsRgsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="cf1a6-107">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>

<span data-ttu-id="cf1a6-p102">La música en espera predeterminada se reproduce cuando se pone una llamada en espera solo si no se definió ninguna música en espera personalizada. El contexto de llamada está disponible solo para las colas asignadas a flujos de trabajo interactivos. Si se habilitó el contexto de llamada, un agente puede ver información como tiempo de espera del autor de la llamada, o preguntas y respuestas del flujo de trabajo, cuando se recibe la llamada.</span><span class="sxs-lookup"><span data-stu-id="cf1a6-p102">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined. Call context is available only for queues assigned to interactive workflows. If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>

<div>

## <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="cf1a6-111">Para modificar la configuración del nivel de aplicación de un grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="cf1a6-111">To modify Response Group application-level settings</span></span>

1.  <span data-ttu-id="cf1a6-112">Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="cf1a6-112">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="cf1a6-113">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="cf1a6-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="cf1a6-114">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="cf1a6-114">At the command line, run:</span></span>
    
        Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
    
    <span data-ttu-id="cf1a6-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cf1a6-115">For example:</span></span>
    
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
    
    <span data-ttu-id="cf1a6-p103">Para especificar un archivo de audio para usar como música en espera predeterminada, debe importar primero el archivo de audio. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cf1a6-p103">To specify an audio file to use as the default music on hold, you need to import the audio file first. For example:</span></span>
    
        $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cf1a6-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf1a6-118">See Also</span></span>


[<span data-ttu-id="cf1a6-119">Get-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="cf1a6-119">Get-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)  
[<span data-ttu-id="cf1a6-120">Set-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="cf1a6-120">Set-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsConfiguration)  
[<span data-ttu-id="cf1a6-121">Importar-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="cf1a6-121">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

