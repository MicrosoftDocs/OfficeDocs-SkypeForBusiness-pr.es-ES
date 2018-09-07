---
title: Calidad de experiencia consulte la Guía de-equipos de Microsoft
author: turgayo
ms.author: turgayo
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Las tareas y actividades necesarias para supervisar la calidad y uso de Microsoft Teams
localization_priority: Priority
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 42d48f9a6bd841ce2756e783e712ee01ed108c55
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23862622"
---
<span data-ttu-id="35d1b-103">![Fases de la actualización viaje, con especial hincapié en la fase de excelencia operativa] (media/upgrade-banner-op-excellence.png "Fases de la actualización viaje, con especial hincapié en la fase de excelencia operativa")</span><span class="sxs-lookup"><span data-stu-id="35d1b-103">![Stages of the upgrade journey, with emphasis on the Operational Excellence stage](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="35d1b-104">En este artículo forma parte de la fase de excelencia operativa de su viaje de actualización, que comienza en cuanto se haya completado la actualización de Skype para la empresa a los equipos.</span><span class="sxs-lookup"><span data-stu-id="35d1b-104">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="35d1b-105">Calidad de experiencia consulte la Guía</span><span class="sxs-lookup"><span data-stu-id="35d1b-105">Quality of Experience Review Guide</span></span>

<span data-ttu-id="35d1b-106">La [Calidad de experiencia consulte la guía](https://aka.ms/qerguide) incluye un conjunto de actividades que evaluar y se proporcionan instrucciones de corrección en áreas clave que tienen el mayor impacto sobre cómo mejorar la experiencia del usuario, tal y como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="35d1b-106">The [Quality of Experience Review Guide](https://aka.ms/qerguide) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="35d1b-107">![Las áreas clave que se desea examinar durante una revisión de calidad de experiencia: audio, la confiabilidad y resultados de la encuesta.] (media/plan-my-service-management-image2.png "Las áreas clave que se desea examinar durante una revisión de calidad de experiencia: audio, la confiabilidad y resultados de la encuesta.")</span><span class="sxs-lookup"><span data-stu-id="35d1b-107">![The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="35d1b-108">Al continuamente evaluar y solucionar relativos a las áreas que se describen en la guía, puede reducir su potencial de afectar negativamente a la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="35d1b-108">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="35d1b-109">Mayoría de experiencia de usuario los problemas encontrada en una implementación puede agruparse en las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="35d1b-109">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

-   <span data-ttu-id="35d1b-110">Configuración de firewall o proxy incompleto</span><span class="sxs-lookup"><span data-stu-id="35d1b-110">Incomplete firewall or proxy configuration</span></span>

-   <span data-ttu-id="35d1b-111">Cobertura Wi-Fi deficiente</span><span class="sxs-lookup"><span data-stu-id="35d1b-111">Poor Wi-Fi coverage</span></span>

-   <span data-ttu-id="35d1b-112">Ancho de banda insuficiente</span><span class="sxs-lookup"><span data-stu-id="35d1b-112">Insufficient bandwidth</span></span>

-   <span data-ttu-id="35d1b-113">VPN</span><span class="sxs-lookup"><span data-stu-id="35d1b-113">VPN</span></span>

-   <span data-ttu-id="35d1b-114">Uso de dispositivos de audio integrados o no optimizados</span><span class="sxs-lookup"><span data-stu-id="35d1b-114">Use of unoptimized or built-in audio devices</span></span>

-   <span data-ttu-id="35d1b-115">Subredes problemáticas o dispositivos de red</span><span class="sxs-lookup"><span data-stu-id="35d1b-115">Problematic subnets or network devices</span></span>

<span data-ttu-id="35d1b-116">Las instrucciones proporcionadas en la Guía de revisión de calidad de experiencia se centra en uso en pantalla de panel de calidad de llamadas (CQD) como la principal herramienta para notificar e investigar cada área que se ha descrito, con un enfoque en audio para maximizar la adopción y el impacto.</span><span class="sxs-lookup"><span data-stu-id="35d1b-116">The guidance provided in the Quality of Experience Review Guide focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="35d1b-117">Cualquier optimizaciones realizadas a la red para mejorar la experiencia de audio traducirá también directamente a las mejoras en uso compartido de escritorio y de vídeo.</span><span class="sxs-lookup"><span data-stu-id="35d1b-117">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="35d1b-118">Se recomienda encarecidamente que se nombra al Campeón de calidad desde el principio.</span><span class="sxs-lookup"><span data-stu-id="35d1b-118">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="35d1b-119">Después de que se ha designado, debe comenzar a familiarizarse con el contenido en la [Calidad de experiencia de guía para la revisión](https://aka.ms/qerguide).</span><span class="sxs-lookup"><span data-stu-id="35d1b-119">After being nominated, they should start to familiarize themselves with the content in the [Quality of Experience Review Guide](https://aka.ms/qerguide).</span></span>

<!--ENDOFSECTION-->