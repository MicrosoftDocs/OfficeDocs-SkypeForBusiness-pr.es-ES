---
title: Calificar mi llamada en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: 'Resumen: Obtenga información sobre cómo calificar mi característica de llamada en Skype empresarial Server.'
ms.openlocfilehash: e146bba647c9586d96682bf8056417630676726e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279861"
---
# <a name="rate-my-call-in-skype-for-business-server"></a><span data-ttu-id="d2652-103">Calificar mi llamada en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d2652-103">Rate my Call in Skype for Business Server</span></span>

<span data-ttu-id="d2652-104">**Resumen:** Más información sobre la opción calificar mi llamada en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d2652-104">**Summary:** Learn about the Rate My Call feature in Skype for Business Server.</span></span>

<span data-ttu-id="d2652-105">Calificar mi llamada fue una nueva característica de los clientes de Skype empresarial 2015 y 2016 en Windows que ofrece a las empresas una forma de obtener los comentarios de sus usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="d2652-105">Rate My Call was a new feature in Skype for Business 2015 and 2016 clients on Windows that provides enterprises a way to get feedback from their end-users.</span></span>

<span data-ttu-id="d2652-106">La ventana calificar mi llamada ofrece un sistema de clasificación de "estrella" y símbolos predefinidos para las llamadas de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="d2652-106">The Rate My Call window offers a "star" rating system and predefined tokens for audio and video calls.</span></span> <span data-ttu-id="d2652-107">Además, los administradores pueden habilitar un campo personalizado para proporcionar comentarios.</span><span class="sxs-lookup"><span data-stu-id="d2652-107">In addition, administrators can enable a custom field to provide feedback.</span></span>

<span data-ttu-id="d2652-108">Actualmente, los datos recopilados de Valorar mi llamada no se incluyen en ningún informe de supervisión existente, aunque dispone de un informe de supervisión independiente.</span><span class="sxs-lookup"><span data-stu-id="d2652-108">Collected Rate My Call data is not currently included in any existing monitoring report, but it has a separate monitoring report.</span></span> <span data-ttu-id="d2652-109">Los datos se recopilan en tablas de SQL a las que se puede tener acceso ejecutando consultas SQL.</span><span class="sxs-lookup"><span data-stu-id="d2652-109">Data is collected in SQL tables that can be accessed by running SQL queries.</span></span>

## <a name="rate-my-call-prerequisites"></a><span data-ttu-id="d2652-110">Requisitos previos de Valorar mi llamada</span><span class="sxs-lookup"><span data-stu-id="d2652-110">Rate my Call Prerequisites</span></span>

<span data-ttu-id="d2652-111">Antes de que los usuarios de su implementación de Skype empresarial Server puedan acceder a la función mi llamada, se debe implementar y configurar el siguiente conjunto de componentes:</span><span class="sxs-lookup"><span data-stu-id="d2652-111">Before the users in your Skype for Business Server deployment can access Rate My Call functionality, the following set of components must be deployed and configured:</span></span>

-  <span data-ttu-id="d2652-112">Debe tener instalado Skype empresarial Server (versión 9160 o superior).</span><span class="sxs-lookup"><span data-stu-id="d2652-112">You must have Skype for Business Server installed (version 9160 or higher).</span></span>

- <span data-ttu-id="d2652-113">Pida a los usuarios que instalen y actualicen a la versión más reciente de Skype empresarial y que utilicen la interfaz de usuario de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="d2652-113">Have your users install and update to the latest version of Skype for Business and also ask them to use the Skype for Business UI.</span></span>

- <span data-ttu-id="d2652-114">Los usuarios deben estar alojados en el grupo de servidores front-end de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d2652-114">Users must be homed on the Skype for Business Server Front End pool.</span></span>

- <span data-ttu-id="d2652-115">Debe tener una base de datos de supervisión del servidor de Skype empresarial implementada y asociada a sus grupos de servidores de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="d2652-115">You must have a Skype for Business Server monitoring database deployed and associated to your Skype for Business Server pools.</span></span>

- <span data-ttu-id="d2652-116">Le recomendamos que implemente el Panel de calidad de llamadas (CQD).</span><span class="sxs-lookup"><span data-stu-id="d2652-116">We recommend deploying Call Quality Dashboard (CQD).</span></span>

## <a name="configure-rate-my-call"></a><span data-ttu-id="d2652-117">Configurar Valorar mi llamada</span><span class="sxs-lookup"><span data-stu-id="d2652-117">Configure Rate my Call</span></span>

<span data-ttu-id="d2652-118">La opción calificar mi llamada está habilitada de forma predeterminada en la Directiva de cliente con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="d2652-118">The Rate My Call feature is enabled by default in the Client policy with the following settings:</span></span>

- <span data-ttu-id="d2652-119">Calificar el porcentaje de visualización de llamadas% 10%</span><span class="sxs-lookup"><span data-stu-id="d2652-119">Rate My Call Display Percentage - 10%</span></span>

- <span data-ttu-id="d2652-120">Calificar mi llamada permitir comentarios personalizados de usuario: deshabilitado</span><span class="sxs-lookup"><span data-stu-id="d2652-120">Rate My Call Allow Custom User Feedback - disabled</span></span>

<span data-ttu-id="d2652-121">Sin embargo, no es necesario realizar ninguna acción para habilitar la característica básica, pero si desea comentarios personalizados, tendrá que habilitarlo por separado.</span><span class="sxs-lookup"><span data-stu-id="d2652-121">There is no action required to enable the base feature, however but if you want custom feedback you will need to enable it separately.</span></span> <span data-ttu-id="d2652-122">El siguiente cmdlet de Windows PowerShell es un ejemplo de cómo habilitar comentarios personalizados para el usuario final y cambiar el intervalo de 10% a 80%.</span><span class="sxs-lookup"><span data-stu-id="d2652-122">The following Windows PowerShell cmdlet is an example of enabling custom end user feedback and changing the interval from 10% to 80%.</span></span>

```
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 - RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a><span data-ttu-id="d2652-123">Obtener acceso a los datos de Valorar mi llamada</span><span class="sxs-lookup"><span data-stu-id="d2652-123">Accessing Rate My Call Data</span></span>

<span data-ttu-id="d2652-124">Los datos de los usuarios se recopilan en dos tablas de la base de datos de supervisión.</span><span class="sxs-lookup"><span data-stu-id="d2652-124">Data from users is collected in two tables in the monitoring database.</span></span>

 <span data-ttu-id="d2652-125">**[QoeMetrics]. [dbo]. [CallQualityFeedbackToken]** -Esta tabla contiene los resultados del sondeo de tokens por parte de los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="d2652-125">**[QoeMetrics].[dbo].[CallQualityFeedbackToken]** - this table contains results of token polling by end users.</span></span>

 <span data-ttu-id="d2652-126">**[QoeMetrics]. [dbo]. [CallQualityFeedbackTokenDef]** -Esta tabla contiene definiciones de token.</span><span class="sxs-lookup"><span data-stu-id="d2652-126">**[QoeMetrics].[dbo].[CallQualityFeedbackTokenDef]** - this table contains token definitions.</span></span>

<span data-ttu-id="d2652-127">Las definiciones de tokens se codifican del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="d2652-127">Token definitions are coded as follows:</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d2652-128">1</span><span class="sxs-lookup"><span data-stu-id="d2652-128">1</span></span>  <br/> |<span data-ttu-id="d2652-129">DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="d2652-129">DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="d2652-130">2</span><span class="sxs-lookup"><span data-stu-id="d2652-130">2</span></span>  <br/> | <span data-ttu-id="d2652-131">ElectronicFeedback</span><span class="sxs-lookup"><span data-stu-id="d2652-131">ElectronicFeedback</span></span> <br/> |
|<span data-ttu-id="d2652-132">3</span><span class="sxs-lookup"><span data-stu-id="d2652-132">3</span></span>  <br/> | <span data-ttu-id="d2652-133">BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="d2652-133">BackgroundNoise</span></span> <br/> |
|<span data-ttu-id="d2652-134">4</span><span class="sxs-lookup"><span data-stu-id="d2652-134">4</span></span>  <br/> |<span data-ttu-id="d2652-135">MuffledSpeech</span><span class="sxs-lookup"><span data-stu-id="d2652-135">MuffledSpeech</span></span>  <br/> |
|<span data-ttu-id="d2652-136">5</span><span class="sxs-lookup"><span data-stu-id="d2652-136">5</span></span>  <br/> |<span data-ttu-id="d2652-137">Eco</span><span class="sxs-lookup"><span data-stu-id="d2652-137">Echo</span></span>  <br/> |
|<span data-ttu-id="d2652-138">21Vianet</span><span class="sxs-lookup"><span data-stu-id="d2652-138">21</span></span>  <br/> | <span data-ttu-id="d2652-139">FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="d2652-139">FrozenVideo</span></span> <br/> |
|<span data-ttu-id="d2652-140">23</span><span class="sxs-lookup"><span data-stu-id="d2652-140">22</span></span>  <br/> | <span data-ttu-id="d2652-141">PixelatedVideo</span><span class="sxs-lookup"><span data-stu-id="d2652-141">PixelatedVideo</span></span> <br/> |
|<span data-ttu-id="d2652-142">,23</span><span class="sxs-lookup"><span data-stu-id="d2652-142">23</span></span>  <br/> | <span data-ttu-id="d2652-143">BlurryImage</span><span class="sxs-lookup"><span data-stu-id="d2652-143">BlurryImage</span></span> <br/> |
|<span data-ttu-id="d2652-144">veinticuatro</span><span class="sxs-lookup"><span data-stu-id="d2652-144">24</span></span>  <br/> | <span data-ttu-id="d2652-145">PoorColor</span><span class="sxs-lookup"><span data-stu-id="d2652-145">PoorColor</span></span> <br/> |
|<span data-ttu-id="d2652-146">veinticinco</span><span class="sxs-lookup"><span data-stu-id="d2652-146">25</span></span>  <br/> | <span data-ttu-id="d2652-147">DarkVideo</span><span class="sxs-lookup"><span data-stu-id="d2652-147">DarkVideo</span></span> <br/> |
|<span data-ttu-id="d2652-148">101</span><span class="sxs-lookup"><span data-stu-id="d2652-148">101</span></span>  <br/> |<span data-ttu-id="d2652-149">Audio_SilentLocal</span><span class="sxs-lookup"><span data-stu-id="d2652-149">Audio_SilentLocal</span></span>  <br/> |
|<span data-ttu-id="d2652-150">102</span><span class="sxs-lookup"><span data-stu-id="d2652-150">102</span></span>  <br/> |<span data-ttu-id="d2652-151">Audio_SilentRemote</span><span class="sxs-lookup"><span data-stu-id="d2652-151">Audio_SilentRemote</span></span>  <br/> |
|<span data-ttu-id="d2652-152">103</span><span class="sxs-lookup"><span data-stu-id="d2652-152">103</span></span>  <br/> |<span data-ttu-id="d2652-153">Audio_Echo</span><span class="sxs-lookup"><span data-stu-id="d2652-153">Audio_Echo</span></span>  <br/> |
|<span data-ttu-id="d2652-154">104</span><span class="sxs-lookup"><span data-stu-id="d2652-154">104</span></span>  <br/> |<span data-ttu-id="d2652-155">Audio_BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="d2652-155">Audio_BackgroundNoise</span></span>  <br/> |
|<span data-ttu-id="d2652-156">105</span><span class="sxs-lookup"><span data-stu-id="d2652-156">105</span></span>  <br/> |<span data-ttu-id="d2652-157">Audio_LowSound</span><span class="sxs-lookup"><span data-stu-id="d2652-157">Audio_LowSound</span></span>  <br/> |
|<span data-ttu-id="d2652-158">106</span><span class="sxs-lookup"><span data-stu-id="d2652-158">106</span></span>  <br/> |<span data-ttu-id="d2652-159">Audio_Dropped</span><span class="sxs-lookup"><span data-stu-id="d2652-159">Audio_Dropped</span></span>  <br/> |
|<span data-ttu-id="d2652-160">107</span><span class="sxs-lookup"><span data-stu-id="d2652-160">107</span></span>  <br/> |<span data-ttu-id="d2652-161">Audio_DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="d2652-161">Audio_DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="d2652-162">108</span><span class="sxs-lookup"><span data-stu-id="d2652-162">108</span></span>  <br/> |<span data-ttu-id="d2652-163">Audio_Interrupted</span><span class="sxs-lookup"><span data-stu-id="d2652-163">Audio_Interrupted</span></span>  <br/> |
|<span data-ttu-id="d2652-164">109</span><span class="sxs-lookup"><span data-stu-id="d2652-164">109</span></span>  <br/> |<span data-ttu-id="d2652-165">Audio_Other</span><span class="sxs-lookup"><span data-stu-id="d2652-165">Audio_Other</span></span>  <br/> |
|<span data-ttu-id="d2652-166">201</span><span class="sxs-lookup"><span data-stu-id="d2652-166">201</span></span>  <br/> |<span data-ttu-id="d2652-167">Video_NoLocalVideo</span><span class="sxs-lookup"><span data-stu-id="d2652-167">Video_NoLocalVideo</span></span>  <br/> |
|<span data-ttu-id="d2652-168">202</span><span class="sxs-lookup"><span data-stu-id="d2652-168">202</span></span>  <br/> |<span data-ttu-id="d2652-169">Video_NoRemoteVideo</span><span class="sxs-lookup"><span data-stu-id="d2652-169">Video_NoRemoteVideo</span></span>  <br/> |
|<span data-ttu-id="d2652-170">203</span><span class="sxs-lookup"><span data-stu-id="d2652-170">203</span></span>  <br/> |<span data-ttu-id="d2652-171">Video_LowQuality</span><span class="sxs-lookup"><span data-stu-id="d2652-171">Video_LowQuality</span></span>  <br/> |
|<span data-ttu-id="d2652-172">204</span><span class="sxs-lookup"><span data-stu-id="d2652-172">204</span></span>  <br/> |<span data-ttu-id="d2652-173">Video_FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="d2652-173">Video_FrozenVideo</span></span>  <br/> |
|<span data-ttu-id="d2652-174">205</span><span class="sxs-lookup"><span data-stu-id="d2652-174">205</span></span>  <br/> |<span data-ttu-id="d2652-175">Video_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="d2652-175">Video_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="d2652-176">206</span><span class="sxs-lookup"><span data-stu-id="d2652-176">206</span></span>  <br/> |<span data-ttu-id="d2652-177">Video_DarkVideo</span><span class="sxs-lookup"><span data-stu-id="d2652-177">Video_DarkVideo</span></span>  <br/> |
|<span data-ttu-id="d2652-178">207</span><span class="sxs-lookup"><span data-stu-id="d2652-178">207</span></span>  <br/> |<span data-ttu-id="d2652-179">Video_NoAudioSync</span><span class="sxs-lookup"><span data-stu-id="d2652-179">Video_NoAudioSync</span></span>  <br/> |
|<span data-ttu-id="d2652-180">208</span><span class="sxs-lookup"><span data-stu-id="d2652-180">208</span></span>  <br/> |<span data-ttu-id="d2652-181">Video_Other</span><span class="sxs-lookup"><span data-stu-id="d2652-181">Video_Other</span></span>  <br/> |
|<span data-ttu-id="d2652-182">301</span><span class="sxs-lookup"><span data-stu-id="d2652-182">301</span></span>  <br/> |<span data-ttu-id="d2652-183">Pstn_DialPad</span><span class="sxs-lookup"><span data-stu-id="d2652-183">Pstn_DialPad</span></span>  <br/> |
|<span data-ttu-id="d2652-184">401</span><span class="sxs-lookup"><span data-stu-id="d2652-184">401</span></span>  <br/> |<span data-ttu-id="d2652-185">SS_NoContentLocal</span><span class="sxs-lookup"><span data-stu-id="d2652-185">SS_NoContentLocal</span></span>  <br/> |
|<span data-ttu-id="d2652-186">402</span><span class="sxs-lookup"><span data-stu-id="d2652-186">402</span></span>  <br/> |<span data-ttu-id="d2652-187">SS_NoContentRemote</span><span class="sxs-lookup"><span data-stu-id="d2652-187">SS_NoContentRemote</span></span>  <br/> |
|<span data-ttu-id="d2652-188">403</span><span class="sxs-lookup"><span data-stu-id="d2652-188">403</span></span>  <br/> |<span data-ttu-id="d2652-189">SS_CantPresent</span><span class="sxs-lookup"><span data-stu-id="d2652-189">SS_CantPresent</span></span>  <br/> |
|<span data-ttu-id="d2652-190">404</span><span class="sxs-lookup"><span data-stu-id="d2652-190">404</span></span>  <br/> |<span data-ttu-id="d2652-191">SS_LowQuality</span><span class="sxs-lookup"><span data-stu-id="d2652-191">SS_LowQuality</span></span>  <br/> |
|<span data-ttu-id="d2652-192">405</span><span class="sxs-lookup"><span data-stu-id="d2652-192">405</span></span>  <br/> |<span data-ttu-id="d2652-193">SS_Freezing</span><span class="sxs-lookup"><span data-stu-id="d2652-193">SS_Freezing</span></span>  <br/> |
|<span data-ttu-id="d2652-194">406</span><span class="sxs-lookup"><span data-stu-id="d2652-194">406</span></span>  <br/> |<span data-ttu-id="d2652-195">SS_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="d2652-195">SS_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="d2652-196">407</span><span class="sxs-lookup"><span data-stu-id="d2652-196">407</span></span>  <br/> |<span data-ttu-id="d2652-197">SS_LargeDelay</span><span class="sxs-lookup"><span data-stu-id="d2652-197">SS_LargeDelay</span></span>  <br/> |
|<span data-ttu-id="d2652-198">408</span><span class="sxs-lookup"><span data-stu-id="d2652-198">408</span></span>  <br/> |<span data-ttu-id="d2652-199">SS_Other</span><span class="sxs-lookup"><span data-stu-id="d2652-199">SS_Other</span></span>  <br/> |
|<span data-ttu-id="d2652-200">501</span><span class="sxs-lookup"><span data-stu-id="d2652-200">501</span></span>  <br/> |<span data-ttu-id="d2652-201">Reliabilty_Join</span><span class="sxs-lookup"><span data-stu-id="d2652-201">Reliabilty_Join</span></span>  <br/> |
|<span data-ttu-id="d2652-202">502</span><span class="sxs-lookup"><span data-stu-id="d2652-202">502</span></span>  <br/> |<span data-ttu-id="d2652-203">Reliabilty_Invite</span><span class="sxs-lookup"><span data-stu-id="d2652-203">Reliabilty_Invite</span></span>  <br/> |

 <span data-ttu-id="d2652-204">**[QoeMetrics]. [dbo]. [CallQualityFeedback]** Esta tabla contiene los resultados del sondeo de votación de "estrella" y comentarios de clientes si está habilitado.</span><span class="sxs-lookup"><span data-stu-id="d2652-204">**[QoeMetrics].[dbo].[CallQualityFeedback]** This table contains polling results from "Star" voting and customer feedback if enabled.</span></span>

<span data-ttu-id="d2652-205">Se puede llamar a los datos de las tablas mediante una consulta **SELECT \* from [Table.Name]** o mediante Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="d2652-205">Data from tables can be called by using a **select \* from [Table.Name]** query or by using Microsoft SQL Server Management Studio.</span></span>

<span data-ttu-id="d2652-206">Se pueden utilizar las siguientes consultas SQL:</span><span class="sxs-lookup"><span data-stu-id="d2652-206">The following SQL queries can be used:</span></span>

 <span data-ttu-id="d2652-207">**Audio**</span><span class="sxs-lookup"><span data-stu-id="d2652-207">**Audio**</span></span>

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

 <span data-ttu-id="d2652-208">**Vídeo**</span><span class="sxs-lookup"><span data-stu-id="d2652-208">**Video**</span></span>

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

## <a name="updating-token-definitions"></a><span data-ttu-id="d2652-209">Actualización de definiciones de token</span><span class="sxs-lookup"><span data-stu-id="d2652-209">Updating Token Definitions</span></span>

<span data-ttu-id="d2652-210">Los últimos clientes de Skype empresarial informan de nuevos identificadores de problema (\> 100) que podrían no estar presentes en tu [QoeMetrics]. [dbo]. Tabla [CallQualityFeedbackTokenDef].</span><span class="sxs-lookup"><span data-stu-id="d2652-210">The latest Skype for Business clients report new problem token IDs (\> 100) that may not be present in your [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span> <span data-ttu-id="d2652-211">Para actualizar la tabla de la base de datos con las definiciones de token más recientes, el comando SQL siguiente se puede ejecutar en la base de datos de supervisión con Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="d2652-211">To update the database table with the latest token definitions, the below SQL command can be run on the monitoring database using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="d2652-212">Este comando reemplazará todas las entradas de [QoeMetrics]. [dbo]. Tabla [CallQualityFeedbackTokenDef].</span><span class="sxs-lookup"><span data-stu-id="d2652-212">This command will replace all entries in the [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span>

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


