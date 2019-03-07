---
title: Calidad de la experiencia de usuario | Los equipos de Microsoft | QoS | Calidad de la llamada
author: turgayo
ms.author: turgayo
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Las tareas y actividades necesarias para supervisar la calidad y uso de Microsoft Teams
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4060c0f9171c8871ed22d15325d560616bf5fc23
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460079"
---
<span data-ttu-id="6c40c-103">![Fases de la actualización viaje, con especial hincapié en la fase de excelencia operativa] (media/upgrade-banner-op-excellence.png "Fases de la actualización viaje, con especial hincapié en la fase de excelencia operativa")</span><span class="sxs-lookup"><span data-stu-id="6c40c-103">![Stages of the upgrade journey, with emphasis on the Operational Excellence stage](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="6c40c-104">En este artículo forma parte de la fase de excelencia operativa de su viaje de actualización, que comienza en cuanto se haya completado la actualización de Skype para la empresa a los equipos.</span><span class="sxs-lookup"><span data-stu-id="6c40c-104">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="6c40c-105">Calidad de experiencia consulte la Guía</span><span class="sxs-lookup"><span data-stu-id="6c40c-105">Quality of Experience Review Guide</span></span>

<span data-ttu-id="6c40c-106">La [Calidad de experiencia consulte la guía](https://aka.ms/qerguide) incluye un conjunto de actividades que evaluar y se proporcionan instrucciones de corrección en áreas clave que tienen el mayor impacto sobre cómo mejorar la experiencia del usuario, tal y como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="6c40c-106">The [Quality of Experience Review Guide](https://aka.ms/qerguide) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="6c40c-107">![Las áreas clave que se desea examinar durante una revisión de calidad de experiencia: audio, la confiabilidad y resultados de la encuesta.] (media/plan-my-service-management-image2.png "Las áreas clave que se desea examinar durante una revisión de calidad de experiencia: audio, la confiabilidad y resultados de la encuesta.")</span><span class="sxs-lookup"><span data-stu-id="6c40c-107">![The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="6c40c-108">Al continuamente evaluar y solucionar relativos a las áreas que se describen en la guía, puede reducir su potencial de afectar negativamente a la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="6c40c-108">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="6c40c-109">La mayoría de problemas que se encuentran en la experiencia de usuario de una implementación se pueden agrupar en las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="6c40c-109">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

- <span data-ttu-id="6c40c-110">Una configuración de proxy o firewall incompleta</span><span class="sxs-lookup"><span data-stu-id="6c40c-110">Incomplete firewall or proxy configuration</span></span>

- <span data-ttu-id="6c40c-111">Una cobertura Wi-Fi insuficiente</span><span class="sxs-lookup"><span data-stu-id="6c40c-111">Poor Wi-Fi coverage</span></span>

- <span data-ttu-id="6c40c-112">Un ancho de banda insuficiente</span><span class="sxs-lookup"><span data-stu-id="6c40c-112">Insufficient bandwidth</span></span>

- <span data-ttu-id="6c40c-113">VPN</span><span class="sxs-lookup"><span data-stu-id="6c40c-113">VPN</span></span>

- <span data-ttu-id="6c40c-114">El uso de dispositivos de audio integrados o no optimizados</span><span class="sxs-lookup"><span data-stu-id="6c40c-114">Use of unoptimized or built-in audio devices</span></span>

- <span data-ttu-id="6c40c-115">Dispositivos de red o subred problemáticos</span><span class="sxs-lookup"><span data-stu-id="6c40c-115">Problematic subnets or network devices</span></span>

<span data-ttu-id="6c40c-116">Las instrucciones proporcionadas en la Guía de revisión de calidad de experiencia se centra en uso en pantalla de panel de calidad de llamadas (CQD) como la principal herramienta para notificar e investigar cada área que se ha descrito, con un enfoque en audio para maximizar la adopción y el impacto.</span><span class="sxs-lookup"><span data-stu-id="6c40c-116">The guidance provided in the Quality of Experience Review Guide focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="6c40c-117">Las optimizaciones que se realicen en la red para mejorar la experiencia de audio se traducirán directamente en mejoras de las de vídeo y escritorio compartido.</span><span class="sxs-lookup"><span data-stu-id="6c40c-117">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="6c40c-118">Se recomienda encarecidamente que se nombra al Campeón de calidad desde el principio.</span><span class="sxs-lookup"><span data-stu-id="6c40c-118">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="6c40c-119">Después de que se ha designado, debe comenzar a familiarizarse con el contenido en la [Calidad de experiencia de guía para la revisión](https://aka.ms/qerguide).</span><span class="sxs-lookup"><span data-stu-id="6c40c-119">After being nominated, they should start to familiarize themselves with the content in the [Quality of Experience Review Guide](https://aka.ms/qerguide).</span></span>

<!--ENDOFSECTION-->