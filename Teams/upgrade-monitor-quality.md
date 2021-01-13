---
title: Calidad de la experiencia del usuario | Microsoft Teams | QoS | Calidad de la llamada
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: El administrador puede obtener información sobre las tareas y actividades necesarias para supervisar la calidad y el uso de Microsoft Teams.
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
ms.openlocfilehash: d57f01887961ad0c458b13db20ba79023272bcdf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809000"
---
# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="fa567-103">Guía de revisión de la experiencia de calidad</span><span class="sxs-lookup"><span data-stu-id="fa567-103">Quality of Experience Review Guide</span></span>

<span data-ttu-id="fa567-104">![Diagrama que resalta la fase de excelencia operativa del viaje de actualización](media/upgrade-banner-op-excellence.png "Fases del viaje de actualización, con énfasis en la fase de excelencia operativa")</span><span class="sxs-lookup"><span data-stu-id="fa567-104">![Diagram highlighting Operational Excellence stage of upgrade journey](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="fa567-105">Este artículo forma parte de la fase de excelencia operativa del viaje de actualización, que comienza tan pronto como haya completado la actualización de Skype Empresarial a Teams.</span><span class="sxs-lookup"><span data-stu-id="fa567-105">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

## <a name="improve-and-monitor-call-quality"></a><span data-ttu-id="fa567-106">Mejorar y supervisar la calidad de las llamadas</span><span class="sxs-lookup"><span data-stu-id="fa567-106">Improve and monitor call quality</span></span>

<span data-ttu-id="fa567-107">[Mejorar y supervisar](monitor-call-quality-qos.md) la calidad de las llamadas en Teams incluye un conjunto de actividades que evalúan y proporcionan instrucciones de corrección en áreas clave que tienen el mayor impacto en la mejora de la experiencia del usuario, como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="fa567-107">[Improve and monitor call quality for Teams](monitor-call-quality-qos.md) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="fa567-108">![Ilustración de las áreas clave para examinar durante una revisión.](media/plan-my-service-management-image2.png "Las áreas clave que se examinarán durante una Revisión de la calidad de la experiencia: resultados de encuestas de usuario, confiabilidad y audio.")</span><span class="sxs-lookup"><span data-stu-id="fa567-108">![Illustration of the key areas to examine during a Review.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="fa567-109">Al evaluar y corregir continuamente las áreas descritas en la guía, puede reducir su potencial para afectar negativamente a la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="fa567-109">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="fa567-110">La mayoría de problemas que se encuentran en la experiencia de usuario de una implementación se pueden agrupar en las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="fa567-110">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

- <span data-ttu-id="fa567-111">Una configuración de proxy o firewall incompleta</span><span class="sxs-lookup"><span data-stu-id="fa567-111">Incomplete firewall or proxy configuration</span></span>

- <span data-ttu-id="fa567-112">Una cobertura Wi-Fi insuficiente</span><span class="sxs-lookup"><span data-stu-id="fa567-112">Poor Wi-Fi coverage</span></span>

- <span data-ttu-id="fa567-113">Un ancho de banda insuficiente</span><span class="sxs-lookup"><span data-stu-id="fa567-113">Insufficient bandwidth</span></span>

- <span data-ttu-id="fa567-114">VPN</span><span class="sxs-lookup"><span data-stu-id="fa567-114">VPN</span></span>

- <span data-ttu-id="fa567-115">El uso de dispositivos de audio integrados o no optimizados</span><span class="sxs-lookup"><span data-stu-id="fa567-115">Use of unoptimized or built-in audio devices</span></span>

- <span data-ttu-id="fa567-116">Dispositivos de red o subred problemáticos</span><span class="sxs-lookup"><span data-stu-id="fa567-116">Problematic subnets or network devices</span></span>

<span data-ttu-id="fa567-117">Las instrucciones proporcionadas en Mejorar y supervisar la calidad de las llamadas de [Teams](monitor-call-quality-qos.md) se centran en usar el panel de calidad de llamadas (CQD) en línea como herramienta principal para informar e investigar cada área descrita, con un foco en el audio para maximizar la adopción y el impacto.</span><span class="sxs-lookup"><span data-stu-id="fa567-117">The guidance provided in [Improve and monitor call quality for Teams](monitor-call-quality-qos.md) focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="fa567-118">Las optimizaciones que se realicen en la red para mejorar la experiencia de audio se traducirán directamente en mejoras de las de vídeo y escritorio compartido.</span><span class="sxs-lookup"><span data-stu-id="fa567-118">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="fa567-119">Recomendamos encarecidamente que designe al expertos en calidad al principio.</span><span class="sxs-lookup"><span data-stu-id="fa567-119">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="fa567-120">Después de ser nominados, deberían empezar a familiarizarse con el contenido en Mejorar y supervisar la [calidad de las llamadas de Teams.](monitor-call-quality-qos.md)</span><span class="sxs-lookup"><span data-stu-id="fa567-120">After being nominated, they should start to familiarize themselves with the content in [Improve and monitor call quality for Teams](monitor-call-quality-qos.md).</span></span>

<!--ENDOFSECTION-->
