---
title: Novedades de Skype Empresarial Server 2019 | Características
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumen: estas características son nuevas en Skype Empresarial Server 2019.'
ms.openlocfilehash: f20abfa7d48717052c8ee0144e143a21b168286d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812590"
---
# <a name="whats-in-skype-for-business-server-2019"></a><span data-ttu-id="80ecf-103">Qué hay en Skype Empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="80ecf-103">What's in Skype for Business Server 2019</span></span>

<span data-ttu-id="80ecf-104">**Resumen:** Lea este tema para obtener información sobre las nuevas características de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="80ecf-104">**Summary:** Read this topic to learn about new features in Skype for Business Server 2019.</span></span>  

<span data-ttu-id="80ecf-105">Entre las nuevas características de Skype Empresarial Server 2019 se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="80ecf-105">New features in Skype for Business Server 2019 include the following:</span></span>
  
- <span data-ttu-id="80ecf-106">Correo de voz en la nube</span><span class="sxs-lookup"><span data-stu-id="80ecf-106">Cloud Voicemail</span></span>  
- <span data-ttu-id="80ecf-107">Conector de datos de llamada</span><span class="sxs-lookup"><span data-stu-id="80ecf-107">Call Data Connector</span></span>
- <span data-ttu-id="80ecf-108">Migración en paralelo</span><span class="sxs-lookup"><span data-stu-id="80ecf-108">Side-by-side migration</span></span>

## <a name="unified-messaging-services-cloud-voicemail"></a><span data-ttu-id="80ecf-109">Servicios de mensajería unificada: Correo de voz en la nube</span><span class="sxs-lookup"><span data-stu-id="80ecf-109">Unified messaging services: Cloud Voicemail</span></span>

<span data-ttu-id="80ecf-110">La mensajería unificada de Exchange permanece disponible en Skype Empresarial Server 2019 al integrar Skype Empresarial 2019 con Exchange 2013 o Exchange 2016.</span><span class="sxs-lookup"><span data-stu-id="80ecf-110">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="80ecf-111">Debido a los cambios en el soporte técnico en Exchange 2019, la integración de mensajería unificada de Exchange se está haciendo menos importante a favor del correo de voz en la nube y las características de Operador automático nube.</span><span class="sxs-lookup"><span data-stu-id="80ecf-111">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  

<span data-ttu-id="80ecf-112">El correo de voz en la nube permite a todos los usuarios de Skype Empresarial 2019&#x2014;independientemente de si están ubicados en un entorno local o en línea&#x2014;para tener acceso al mismo servicio de correo de voz en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="80ecf-112">Cloud Voicemail enables all your Skype for Business 2019 users&#x2014;whether they are homed on premises or online&#x2014;to have access to the same voicemail service in the Microsoft Cloud.</span></span> <span data-ttu-id="80ecf-113">El correo de voz en la nube proporciona las siguientes ventajas para los usuarios locales y en línea:</span><span class="sxs-lookup"><span data-stu-id="80ecf-113">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="80ecf-114">Acceso al correo de voz en su buzón de Exchange mediante los clientes de Skype Empresarial Online, Teams o Outlook</span><span class="sxs-lookup"><span data-stu-id="80ecf-114">Access to voicemail in their Exchange mailbox by using the Skype for Business Online, Teams, or Outlook clients</span></span>
- <span data-ttu-id="80ecf-115">Capacidad de usar el portal basado en web para administrar sus opciones de correo de voz</span><span class="sxs-lookup"><span data-stu-id="80ecf-115">Ability to use the web-based portal to manage their voicemail options</span></span>

<span data-ttu-id="80ecf-116">Consulte [Plan Cloud Voicemail service](../sfbhybrid/hybrid/plan-cloud-voicemail.md) and Plan for Skype for Business Server and Exchange Server [migration](../sfbhybrid/hybrid/plan-um-migration.md) for more information.</span><span class="sxs-lookup"><span data-stu-id="80ecf-116">See [Plan Cloud Voicemail service](../sfbhybrid/hybrid/plan-cloud-voicemail.md) and [Plan for Skype for Business Server and Exchange Server migration](../sfbhybrid/hybrid/plan-um-migration.md) for more information.</span></span>
  
## <a name="call-monitoring-call-data-connector"></a><span data-ttu-id="80ecf-117">Supervisión de llamadas: Conector de datos de llamadas</span><span class="sxs-lookup"><span data-stu-id="80ecf-117">Call monitoring: Call Data Connector</span></span>

<span data-ttu-id="80ecf-118">Call Data Connector simplifica en gran medida la supervisión de llamadas en un entorno híbrido porque ya no necesita usar diferentes conjuntos de herramientas locales y en línea para supervisar la calidad de las llamadas de todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="80ecf-118">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span>  <span data-ttu-id="80ecf-119">Independientemente de si los usuarios están ubicados localmente o en línea, puede elegir ver la calidad de las llamadas para toda la organización en línea.</span><span class="sxs-lookup"><span data-stu-id="80ecf-119">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="80ecf-120">Con Call Data Connector, puede realizar las siguientes tareas mediante un único conjunto de herramientas:</span><span class="sxs-lookup"><span data-stu-id="80ecf-120">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="80ecf-121">Supervise su experiencia de usuario en Microsoft Teams, Skype Empresarial Online y Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="80ecf-121">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>
- <span data-ttu-id="80ecf-122">Ver y solucionar problemas en la red</span><span class="sxs-lookup"><span data-stu-id="80ecf-122">View and troubleshoot problems across your network</span></span>
- <span data-ttu-id="80ecf-123">Asigne roles de administrador y departamento de soporte técnico para El análisis de llamadas, de modo que pueda ayudar a los trabajadores del departamento de soporte técnico a ver y solucionar los problemas de sus áreas de responsabilidad.</span><span class="sxs-lookup"><span data-stu-id="80ecf-123">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="80ecf-124">Vea [Planear el conector de datos de llamadas](../sfbhybrid/hybrid/plan-call-data-connector.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="80ecf-124">See [Plan Call Data Connector](../sfbhybrid/hybrid/plan-call-data-connector.md) for more information.</span></span>

### <a name="see-also"></a><span data-ttu-id="80ecf-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="80ecf-125">See also</span></span>

[<span data-ttu-id="80ecf-126">Qué está en desuso de Skype Empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="80ecf-126">What's deprecated from Skype for Business Server 2019</span></span>](deprecated.md)
