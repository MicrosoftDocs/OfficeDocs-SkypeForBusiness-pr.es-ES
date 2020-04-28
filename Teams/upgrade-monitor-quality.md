---
title: Calidad de la experiencia del usuario | Microsoft Teams | QoS | Calidad de las llamadas
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Administrador puede obtener información sobre las tareas y las actividades necesarias para supervisar la calidad y el uso de Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9737834e38d87fbc5f925a5667d57ccd0a0aa626
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904345"
---
# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="84717-103">Guía de revisión de la experiencia de calidad</span><span class="sxs-lookup"><span data-stu-id="84717-103">Quality of Experience Review Guide</span></span>

<span data-ttu-id="84717-104">![Diagrama resaltado de excelencia operativa fase de actualización de viaje](media/upgrade-banner-op-excellence.png "Etapas del viaje de actualización, con énfasis en la fase de excelencia operativa")</span><span class="sxs-lookup"><span data-stu-id="84717-104">![Diagram highlighting Operational Excellence stage of upgrade journey](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="84717-105">Este artículo forma parte de la fase de excelencia operativa de su viaje de actualización, que comienza tan pronto como haya completado la actualización de Skype empresarial a teams.</span><span class="sxs-lookup"><span data-stu-id="84717-105">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

<span data-ttu-id="84717-106">La [Guía de revisión de la calidad de la experiencia](https://aka.ms/qerguide) incluye un conjunto de actividades que evalúan y proporcionan instrucciones de corrección en áreas clave que tienen el mayor impacto en la mejora de la experiencia del usuario, como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="84717-106">The [Quality of Experience Review Guide](https://aka.ms/qerguide) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="84717-107">![Ilustración de las áreas clave que se deben examinar durante una revisión.](media/plan-my-service-management-image2.png "Las áreas clave que debe examinar durante una revisión de la calidad de la experiencia: el audio, la fiabilidad y los resultados de la encuesta de usuarios.")</span><span class="sxs-lookup"><span data-stu-id="84717-107">![Illustration of the key areas to examine during a Review.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="84717-108">Al evaluar y corregir continuamente las áreas descritas en la guía, puede reducir su potencial de afectar negativamente a la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="84717-108">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="84717-109">La mayoría de problemas que se encuentran en la experiencia de usuario de una implementación se pueden agrupar en las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="84717-109">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

- <span data-ttu-id="84717-110">Una configuración de proxy o firewall incompleta</span><span class="sxs-lookup"><span data-stu-id="84717-110">Incomplete firewall or proxy configuration</span></span>

- <span data-ttu-id="84717-111">Una cobertura Wi-Fi insuficiente</span><span class="sxs-lookup"><span data-stu-id="84717-111">Poor Wi-Fi coverage</span></span>

- <span data-ttu-id="84717-112">Un ancho de banda insuficiente</span><span class="sxs-lookup"><span data-stu-id="84717-112">Insufficient bandwidth</span></span>

- <span data-ttu-id="84717-113">VPN</span><span class="sxs-lookup"><span data-stu-id="84717-113">VPN</span></span>

- <span data-ttu-id="84717-114">El uso de dispositivos de audio integrados o no optimizados</span><span class="sxs-lookup"><span data-stu-id="84717-114">Use of unoptimized or built-in audio devices</span></span>

- <span data-ttu-id="84717-115">Dispositivos de red o subred problemáticos</span><span class="sxs-lookup"><span data-stu-id="84717-115">Problematic subnets or network devices</span></span>

<span data-ttu-id="84717-116">Las instrucciones que se proporcionan en la guía de revisión de la calidad de la experiencia se centra en usar el panel de calidad de llamadas (CQD) en línea como la herramienta principal para informar e investigar cada área descrita, centrándose en el audio para maximizar la adopción y el impacto.</span><span class="sxs-lookup"><span data-stu-id="84717-116">The guidance provided in the Quality of Experience Review Guide focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="84717-117">Las optimizaciones que se realicen en la red para mejorar la experiencia de audio se traducirán directamente en mejoras de las de vídeo y escritorio compartido.</span><span class="sxs-lookup"><span data-stu-id="84717-117">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="84717-118">Le recomendamos encarecidamente que se haya nominado el preexperto de calidad.</span><span class="sxs-lookup"><span data-stu-id="84717-118">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="84717-119">Después de ser nombrados, deben empezar a familiarizarse con el contenido de la [Guía de revisión de la calidad de la experiencia](https://aka.ms/qerguide).</span><span class="sxs-lookup"><span data-stu-id="84717-119">After being nominated, they should start to familiarize themselves with the content in the [Quality of Experience Review Guide](https://aka.ms/qerguide).</span></span>

<!--ENDOFSECTION-->
