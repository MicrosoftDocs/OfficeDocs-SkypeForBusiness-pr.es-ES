---
title: Valorar mi llamada en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/13/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: 'Resumen: Conozca la función tasa mi llamar en Skype para Business Server 2015.'
ms.openlocfilehash: 1e0088c563f38be59bda0fad10dbd367ea0646e9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="rate-my-call-in-skype-for-business-server-2015"></a><span data-ttu-id="8a38f-103">Valorar mi llamada en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="8a38f-103">Rate my Call in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8a38f-104">**Resumen:** Obtenga información sobre la función tasa mi llamar en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8a38f-104">**Summary:** Learn about the Rate My Call feature in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="8a38f-105">Llame a Mi velocidad es una nueva característica de Skype para negocios 2015 y 2016 clientes Windows que proporciona a las empresas una forma para obtener comentarios de los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="8a38f-105">Rate My Call is a new feature in Skype for Business 2015 and 2016 clients on Windows that provides enterprises a way to get feedback from their end-users.</span></span>
  
<span data-ttu-id="8a38f-106">La ventana tasa Mis llamadas ofrece un sistema de clasificación "estrella" y símbolos predefinidos para llamadas de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="8a38f-106">The Rate My Call window offers a "star" rating system and predefined tokens for audio and video calls.</span></span> <span data-ttu-id="8a38f-107">Además, los administradores pueden habilitar un campo personalizado proporcionar comentarios.</span><span class="sxs-lookup"><span data-stu-id="8a38f-107">In addition, administrators can enable a custom field to provide feedback.</span></span>
  
<span data-ttu-id="8a38f-108">Actualmente, los datos recopilados de Valorar mi llamada no se incluyen en ningún informe de supervisión existente, aunque dispone de un informe de supervisión independiente.</span><span class="sxs-lookup"><span data-stu-id="8a38f-108">Collected Rate My Call data is not currently included in any existing monitoring report, but it has a separate monitoring report.</span></span> <span data-ttu-id="8a38f-109">Se recopilan datos en tablas SQL que se pueden tener acceso mediante la ejecución de consultas SQL.</span><span class="sxs-lookup"><span data-stu-id="8a38f-109">Data is collected in SQL tables that can be accessed by running SQL queries.</span></span>
  
## <a name="rate-my-call-prerequisites"></a><span data-ttu-id="8a38f-110">Valorar mis requisitos previos de la llamada</span><span class="sxs-lookup"><span data-stu-id="8a38f-110">Rate my Call Prerequisites</span></span>

<span data-ttu-id="8a38f-111">Antes de que los usuarios de su Skype para la implementación de Business Server pueden obtener acceso a la funcionalidad de llame a Mi velocidad, se debe implementar y configurar el siguiente conjunto de componentes:</span><span class="sxs-lookup"><span data-stu-id="8a38f-111">Before the users in your Skype for Business Server deployment can access Rate My Call functionality, the following set of components must be deployed and configured:</span></span>
  
-  <span data-ttu-id="8a38f-112">Debe tener Skype para Business Server instalado (versión 9160 o superior).</span><span class="sxs-lookup"><span data-stu-id="8a38f-112">You must have Skype for Business Server installed (version 9160 or higher).</span></span>
    
- <span data-ttu-id="8a38f-113">Hacer que los usuarios instalar y actualizar a la versión más reciente de Skype para empresas y también les pedimos que utilice el Skype para la interfaz de usuario de negocio.</span><span class="sxs-lookup"><span data-stu-id="8a38f-113">Have your users install and update to the latest version of Skype for Business and also ask them to use the Skype for Business UI.</span></span>
    
- <span data-ttu-id="8a38f-114">Los usuarios deben estar alojados en el Skype para el grupo de negocio de servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="8a38f-114">Users must be homed on the Skype for Business Server Front End pool.</span></span>
    
- <span data-ttu-id="8a38f-115">Debe tener un Skype para base de datos supervisión Business Server implementado y asociado a su Skype para grupos de servidores empresariales.</span><span class="sxs-lookup"><span data-stu-id="8a38f-115">You must have a Skype for Business Server monitoring database deployed and associated to your Skype for Business Server pools.</span></span>
    
- <span data-ttu-id="8a38f-116">Le recomendamos que implemente el Panel de calidad de llamadas (CQD).</span><span class="sxs-lookup"><span data-stu-id="8a38f-116">We recommend deploying Call Quality Dashboard (CQD).</span></span>
    
## <a name="configure-rate-my-call"></a><span data-ttu-id="8a38f-117">Configurar la velocidad de mi llamada</span><span class="sxs-lookup"><span data-stu-id="8a38f-117">Configure Rate my Call</span></span>

<span data-ttu-id="8a38f-118">La función de tasa mi llamada está habilitada de forma predeterminada en la directiva de cliente con la configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="8a38f-118">The Rate My Call feature is enabled by default in the Client policy with the following settings:</span></span>
  
- <span data-ttu-id="8a38f-119">Velocidad de mi llamada Mostrar porcentaje - 10%</span><span class="sxs-lookup"><span data-stu-id="8a38f-119">Rate My Call Display Percentage - 10%</span></span>
    
- <span data-ttu-id="8a38f-120">Velocidad de mi llamada permitir personalizar comentarios del usuario - deshabilitado</span><span class="sxs-lookup"><span data-stu-id="8a38f-120">Rate My Call Allow Custom User Feedback - disabled</span></span>
    
<span data-ttu-id="8a38f-121">No hay ninguna acción necesaria para habilitar la característica base, sin embargo, pero si desea una respuesta personalizada debe habilitar por separado.</span><span class="sxs-lookup"><span data-stu-id="8a38f-121">There is no action required to enable the base feature, however but if you want custom feedback you will need to enable it separately.</span></span> <span data-ttu-id="8a38f-122">El siguiente cmdlet de Windows PowerShell es un ejemplo de habilitar comentarios de usuario final personalizadas y cambiar el intervalo de 10% a 80%.</span><span class="sxs-lookup"><span data-stu-id="8a38f-122">The following Windows PowerShell cmdlet is an example of enabling custom end user feedback and changing the interval from 10% to 80%.</span></span>
  
```
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 - RateMyCallAllowCustomUserFeedback $true 

```

## <a name="accessing-rate-my-call-data"></a><span data-ttu-id="8a38f-123">Velocidad de acceso a Mis datos de llamada</span><span class="sxs-lookup"><span data-stu-id="8a38f-123">Accessing Rate My Call Data</span></span>

<span data-ttu-id="8a38f-124">Se recopilan datos de los usuarios en dos tablas de la base de datos de supervisión.</span><span class="sxs-lookup"><span data-stu-id="8a38f-124">Data from users is collected in two tables in the monitoring database.</span></span>
  
 <span data-ttu-id="8a38f-125">**[QoeMetrics]. [dbo]. [CallQualityFeedbackToken]** -Esta tabla contiene los resultados de sondeo token por los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="8a38f-125">**[QoeMetrics].[dbo].[CallQualityFeedbackToken]** - this table contains results of token polling by end users.</span></span>
  
 <span data-ttu-id="8a38f-126">**[QoeMetrics]. [dbo]. [CallQualityFeedbackTokenDef]** -Esta tabla contiene las definiciones de símbolo (token).</span><span class="sxs-lookup"><span data-stu-id="8a38f-126">**[QoeMetrics].[dbo].[CallQualityFeedbackTokenDef]** - this table contains token definitions.</span></span>
  
<span data-ttu-id="8a38f-127">Las definiciones de símbolo (token) se codifican como sigue:</span><span class="sxs-lookup"><span data-stu-id="8a38f-127">Token definitions are coded as follows:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8a38f-128">1</span><span class="sxs-lookup"><span data-stu-id="8a38f-128">1</span></span>  <br/> |<span data-ttu-id="8a38f-129">DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="8a38f-129">DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="8a38f-130">2</span><span class="sxs-lookup"><span data-stu-id="8a38f-130">2</span></span>  <br/> | <span data-ttu-id="8a38f-131">ElectronicFeedback</span><span class="sxs-lookup"><span data-stu-id="8a38f-131">ElectronicFeedback</span></span> <br/> |
|<span data-ttu-id="8a38f-132">3</span><span class="sxs-lookup"><span data-stu-id="8a38f-132">3</span></span>  <br/> | <span data-ttu-id="8a38f-133">BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="8a38f-133">BackgroundNoise</span></span> <br/> |
|<span data-ttu-id="8a38f-134">4</span><span class="sxs-lookup"><span data-stu-id="8a38f-134">4</span></span>  <br/> |<span data-ttu-id="8a38f-135">MuffledSpeech</span><span class="sxs-lookup"><span data-stu-id="8a38f-135">MuffledSpeech</span></span>  <br/> |
|<span data-ttu-id="8a38f-136">5</span><span class="sxs-lookup"><span data-stu-id="8a38f-136">5</span></span>  <br/> |<span data-ttu-id="8a38f-137">Eco</span><span class="sxs-lookup"><span data-stu-id="8a38f-137">Echo</span></span>  <br/> |
|<span data-ttu-id="8a38f-138">21</span><span class="sxs-lookup"><span data-stu-id="8a38f-138">21</span></span>  <br/> | <span data-ttu-id="8a38f-139">FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="8a38f-139">FrozenVideo</span></span> <br/> |
|<span data-ttu-id="8a38f-140">22</span><span class="sxs-lookup"><span data-stu-id="8a38f-140">22</span></span>  <br/> | <span data-ttu-id="8a38f-141">PixelatedVideo</span><span class="sxs-lookup"><span data-stu-id="8a38f-141">PixelatedVideo</span></span> <br/> |
|<span data-ttu-id="8a38f-142">23</span><span class="sxs-lookup"><span data-stu-id="8a38f-142">23</span></span>  <br/> | <span data-ttu-id="8a38f-143">BlurryImage</span><span class="sxs-lookup"><span data-stu-id="8a38f-143">BlurryImage</span></span> <br/> |
|<span data-ttu-id="8a38f-144">24</span><span class="sxs-lookup"><span data-stu-id="8a38f-144">24</span></span>  <br/> | <span data-ttu-id="8a38f-145">PoorColor</span><span class="sxs-lookup"><span data-stu-id="8a38f-145">PoorColor</span></span> <br/> |
|<span data-ttu-id="8a38f-146">25</span><span class="sxs-lookup"><span data-stu-id="8a38f-146">25</span></span>  <br/> | <span data-ttu-id="8a38f-147">DarkVideo</span><span class="sxs-lookup"><span data-stu-id="8a38f-147">DarkVideo</span></span> <br/> |
|<span data-ttu-id="8a38f-148">101</span><span class="sxs-lookup"><span data-stu-id="8a38f-148">101</span></span>  <br/> |<span data-ttu-id="8a38f-149">Audio_SilentLocal</span><span class="sxs-lookup"><span data-stu-id="8a38f-149">Audio_SilentLocal</span></span>  <br/> |
|<span data-ttu-id="8a38f-150">102</span><span class="sxs-lookup"><span data-stu-id="8a38f-150">102</span></span>  <br/> |<span data-ttu-id="8a38f-151">Audio_SilentRemote</span><span class="sxs-lookup"><span data-stu-id="8a38f-151">Audio_SilentRemote</span></span>  <br/> |
|<span data-ttu-id="8a38f-152">103</span><span class="sxs-lookup"><span data-stu-id="8a38f-152">103</span></span>  <br/> |<span data-ttu-id="8a38f-153">Audio_Echo</span><span class="sxs-lookup"><span data-stu-id="8a38f-153">Audio_Echo</span></span>  <br/> |
|<span data-ttu-id="8a38f-154">104</span><span class="sxs-lookup"><span data-stu-id="8a38f-154">104</span></span>  <br/> |<span data-ttu-id="8a38f-155">Audio_BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="8a38f-155">Audio_BackgroundNoise</span></span>  <br/> |
|<span data-ttu-id="8a38f-156">105</span><span class="sxs-lookup"><span data-stu-id="8a38f-156">105</span></span>  <br/> |<span data-ttu-id="8a38f-157">Audio_LowSound</span><span class="sxs-lookup"><span data-stu-id="8a38f-157">Audio_LowSound</span></span>  <br/> |
|<span data-ttu-id="8a38f-158">106</span><span class="sxs-lookup"><span data-stu-id="8a38f-158">106</span></span>  <br/> |<span data-ttu-id="8a38f-159">Audio_Dropped</span><span class="sxs-lookup"><span data-stu-id="8a38f-159">Audio_Dropped</span></span>  <br/> |
|<span data-ttu-id="8a38f-160">107</span><span class="sxs-lookup"><span data-stu-id="8a38f-160">107</span></span>  <br/> |<span data-ttu-id="8a38f-161">Audio_DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="8a38f-161">Audio_DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="8a38f-162">108</span><span class="sxs-lookup"><span data-stu-id="8a38f-162">108</span></span>  <br/> |<span data-ttu-id="8a38f-163">Audio_Interrupted</span><span class="sxs-lookup"><span data-stu-id="8a38f-163">Audio_Interrupted</span></span>  <br/> |
|<span data-ttu-id="8a38f-164">109</span><span class="sxs-lookup"><span data-stu-id="8a38f-164">109</span></span>  <br/> |<span data-ttu-id="8a38f-165">Audio_Other</span><span class="sxs-lookup"><span data-stu-id="8a38f-165">Audio_Other</span></span>  <br/> |
|<span data-ttu-id="8a38f-166">201</span><span class="sxs-lookup"><span data-stu-id="8a38f-166">201</span></span>  <br/> |<span data-ttu-id="8a38f-167">Video_NoLocalVideo</span><span class="sxs-lookup"><span data-stu-id="8a38f-167">Video_NoLocalVideo</span></span>  <br/> |
|<span data-ttu-id="8a38f-168">202</span><span class="sxs-lookup"><span data-stu-id="8a38f-168">202</span></span>  <br/> |<span data-ttu-id="8a38f-169">Video_NoRemoteVideo</span><span class="sxs-lookup"><span data-stu-id="8a38f-169">Video_NoRemoteVideo</span></span>  <br/> |
|<span data-ttu-id="8a38f-170">203</span><span class="sxs-lookup"><span data-stu-id="8a38f-170">203</span></span>  <br/> |<span data-ttu-id="8a38f-171">Video_LowQuality</span><span class="sxs-lookup"><span data-stu-id="8a38f-171">Video_LowQuality</span></span>  <br/> |
|<span data-ttu-id="8a38f-172">204</span><span class="sxs-lookup"><span data-stu-id="8a38f-172">204</span></span>  <br/> |<span data-ttu-id="8a38f-173">Video_FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="8a38f-173">Video_FrozenVideo</span></span>  <br/> |
|<span data-ttu-id="8a38f-174">205</span><span class="sxs-lookup"><span data-stu-id="8a38f-174">205</span></span>  <br/> |<span data-ttu-id="8a38f-175">Video_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="8a38f-175">Video_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="8a38f-176">206</span><span class="sxs-lookup"><span data-stu-id="8a38f-176">206</span></span>  <br/> |<span data-ttu-id="8a38f-177">Video_DarkVideo</span><span class="sxs-lookup"><span data-stu-id="8a38f-177">Video_DarkVideo</span></span>  <br/> |
|<span data-ttu-id="8a38f-178">207</span><span class="sxs-lookup"><span data-stu-id="8a38f-178">207</span></span>  <br/> |<span data-ttu-id="8a38f-179">Video_NoAudioSync</span><span class="sxs-lookup"><span data-stu-id="8a38f-179">Video_NoAudioSync</span></span>  <br/> |
|<span data-ttu-id="8a38f-180">208</span><span class="sxs-lookup"><span data-stu-id="8a38f-180">208</span></span>  <br/> |<span data-ttu-id="8a38f-181">Video_Other</span><span class="sxs-lookup"><span data-stu-id="8a38f-181">Video_Other</span></span>  <br/> |
|<span data-ttu-id="8a38f-182">301</span><span class="sxs-lookup"><span data-stu-id="8a38f-182">301</span></span>  <br/> |<span data-ttu-id="8a38f-183">Pstn_DialPad</span><span class="sxs-lookup"><span data-stu-id="8a38f-183">Pstn_DialPad</span></span>  <br/> |
|<span data-ttu-id="8a38f-184">401</span><span class="sxs-lookup"><span data-stu-id="8a38f-184">401</span></span>  <br/> |<span data-ttu-id="8a38f-185">SS_NoContentLocal</span><span class="sxs-lookup"><span data-stu-id="8a38f-185">SS_NoContentLocal</span></span>  <br/> |
|<span data-ttu-id="8a38f-186">402</span><span class="sxs-lookup"><span data-stu-id="8a38f-186">402</span></span>  <br/> |<span data-ttu-id="8a38f-187">SS_NoContentRemote</span><span class="sxs-lookup"><span data-stu-id="8a38f-187">SS_NoContentRemote</span></span>  <br/> |
|<span data-ttu-id="8a38f-188">403</span><span class="sxs-lookup"><span data-stu-id="8a38f-188">403</span></span>  <br/> |<span data-ttu-id="8a38f-189">SS_CantPresent</span><span class="sxs-lookup"><span data-stu-id="8a38f-189">SS_CantPresent</span></span>  <br/> |
|<span data-ttu-id="8a38f-190">404</span><span class="sxs-lookup"><span data-stu-id="8a38f-190">404</span></span>  <br/> |<span data-ttu-id="8a38f-191">SS_LowQuality</span><span class="sxs-lookup"><span data-stu-id="8a38f-191">SS_LowQuality</span></span>  <br/> |
|<span data-ttu-id="8a38f-192">405</span><span class="sxs-lookup"><span data-stu-id="8a38f-192">405</span></span>  <br/> |<span data-ttu-id="8a38f-193">SS_Freezing</span><span class="sxs-lookup"><span data-stu-id="8a38f-193">SS_Freezing</span></span>  <br/> |
|<span data-ttu-id="8a38f-194">406</span><span class="sxs-lookup"><span data-stu-id="8a38f-194">406</span></span>  <br/> |<span data-ttu-id="8a38f-195">SS_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="8a38f-195">SS_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="8a38f-196">407</span><span class="sxs-lookup"><span data-stu-id="8a38f-196">407</span></span>  <br/> |<span data-ttu-id="8a38f-197">SS_LargeDelay</span><span class="sxs-lookup"><span data-stu-id="8a38f-197">SS_LargeDelay</span></span>  <br/> |
|<span data-ttu-id="8a38f-198">408</span><span class="sxs-lookup"><span data-stu-id="8a38f-198">408</span></span>  <br/> |<span data-ttu-id="8a38f-199">SS_Other</span><span class="sxs-lookup"><span data-stu-id="8a38f-199">SS_Other</span></span>  <br/> |
|<span data-ttu-id="8a38f-200">501</span><span class="sxs-lookup"><span data-stu-id="8a38f-200">501</span></span>  <br/> |<span data-ttu-id="8a38f-201">Reliabilty_Join</span><span class="sxs-lookup"><span data-stu-id="8a38f-201">Reliabilty_Join</span></span>  <br/> |
|<span data-ttu-id="8a38f-202">502</span><span class="sxs-lookup"><span data-stu-id="8a38f-202">502</span></span>  <br/> |<span data-ttu-id="8a38f-203">Reliabilty_Invite</span><span class="sxs-lookup"><span data-stu-id="8a38f-203">Reliabilty_Invite</span></span>  <br/> |
   
 <span data-ttu-id="8a38f-204">**[QoeMetrics]. [dbo]. [CallQualityFeedback]** Esta tabla contiene los resultados de sondeo de comentarios de voto y cliente "Estrella" si habilitado.</span><span class="sxs-lookup"><span data-stu-id="8a38f-204">**[QoeMetrics].[dbo].[CallQualityFeedback]** This table contains polling results from "Star" voting and customer feedback if enabled.</span></span>
  
<span data-ttu-id="8a38f-205">Datos de las tablas se pueden llamar utilizando un **seleccione \* de [Table.Name]** consulta o mediante Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="8a38f-205">Data from tables can be called by using a **select \* from [Table.Name]** query or by using Microsoft SQL Server Management Studio.</span></span>
  
<span data-ttu-id="8a38f-206">Pueden utilizarse las siguientes consultas SQL:</span><span class="sxs-lookup"><span data-stu-id="8a38f-206">The following SQL queries can be used:</span></span>
  
 <span data-ttu-id="8a38f-207">**Audio**</span><span class="sxs-lookup"><span data-stu-id="8a38f-207">**Audio**</span></span>
  
```
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [AudioStream] AS a WITH (NOLOCK) ON -- only look at Audio related feedback
            a.MediaLineLabel = m.MediaLineLabel    
            and a.ConferenceDateTime = m.ConferenceDateTime 
            and a.SessionSeq = m.SessionSeq
            and a.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
            (CallerCqfToken.TokenId < 20 or (CallerCqfToken.TokenId > 100 and CallerCqfToken.TokenId < 200)) -- only look at Audio related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
 
```

 <span data-ttu-id="8a38f-208">**Vídeo**</span><span class="sxs-lookup"><span data-stu-id="8a38f-208">**Video**</span></span>
  
```
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [VideoStream] AS v WITH (NOLOCK) ON -- only look at Video related feedback
            v.MediaLineLabel = m.MediaLineLabel    
            and v.ConferenceDateTime = m.ConferenceDateTime 
            and v.SessionSeq = m.SessionSeq
            and v.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
           ((CallerCqfToken.TokenId > 20 and CallerCqfToken.TokenId < 100) or (CallerCqfToken.TokenId > 200 and CallerCqfToken.TokenId < 300)) -- only look at Video related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

## <a name="updating-token-definitions"></a><span data-ttu-id="8a38f-209">Actualización de definiciones de símbolo (token)</span><span class="sxs-lookup"><span data-stu-id="8a38f-209">Updating Token Definitions</span></span>

<span data-ttu-id="8a38f-210">La última Skype para clientes empresariales informe nuevo token problema IDs (\> 100) que no pueden estar presentes en la sección [QoeMetrics]. [dbo]. Tabla [CallQualityFeedbackTokenDef].</span><span class="sxs-lookup"><span data-stu-id="8a38f-210">The latest Skype for Business clients report new problem token IDs (\> 100) that may not be present in your [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span> <span data-ttu-id="8a38f-211">Para actualizar la tabla de base de datos con las últimas definiciones de símbolo (token), el comando debajo de SQL se puede ejecutar en la base de datos de supervisión mediante Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="8a38f-211">To update the database table with the latest token definitions, the below SQL command can be run on the monitoring database using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="8a38f-212">Este comando reemplazará todas las entradas de la sección [QoeMetrics]. [dbo]. Tabla [CallQualityFeedbackTokenDef].</span><span class="sxs-lookup"><span data-stu-id="8a38f-212">This command will replace all entries in the [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span>
  
```
DELETE FROM [CallQualityFeedbackTokenDef];
INSERT INTO [CallQualityFeedbackTokenDef] (TokenId, TokenDescription) VALUES
    (1,   N'DistortedSpeech'),
    (2,   N'ElectronicFeedback'),
    (3,   N'BackgroundNoise'),
    (4,   N'MuffledSpeech'),
    (5,   N'Echo'),
    (21,  N'FrozenVideo'),
    (22,  N'PixelatedVideo'),
    (23,  N'BlurryImage'),
    (24,  N'PoorColor'),
    (25,  N'DarkVideo'),
    (101, N'Audio_SilentLocal'),
    (102, N'Audio_SilentRemote'),
    (103, N'Audio_Echo'),
    (104, N'Audio_BackgroundNoise'),
    (105, N'Audio_LowSound'),
    (106, N'Audio_Dropped'),
    (107, N'Audio_DistortedSpeech'),
    (108, N'Audio_Interrupted'),
    (109, N'Audio_Other'),
    (201, N'Video_NoLocalVideo'),
    (202, N'Video_NoRemoteVideo'),
    (203, N'Video_LowQuality'),
    (204, N'Video_FrozenVideo'),
    (205, N'Video_StoppedUnexpectedly'),
    (206, N'Video_DarkVideo'),
    (207, N'Video_NoAudioSync'),
    (208, N'Video_Other'),
    (301, N'Pstn_DialPad'),
    (401, N'SS_NoContentLocal'),
    (402, N'SS_NoContentRemote'),
    (403, N'SS_CantPresent'),
    (404, N'SS_LowQuality'),
    (405, N'SS_Freezing'),
    (406, N'SS_StoppedUnexpectedly'),
    (407, N'SS_LargeDelay'),
    (408, N'SS_Other'),
    (501, N'Reliabilty_Join'),
    (502, N'Reliabilty_Invite');

```


