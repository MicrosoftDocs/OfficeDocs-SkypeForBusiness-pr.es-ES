---
title: Novedades de Skype empresarial Server 2019 | Opciones
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumen: estas características son nuevas en Skype empresarial Server 2019.'
ms.openlocfilehash: 4ede00188c8928e0fa3d89857b6d5bfdb0a44ade
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283902"
---
# <a name="whats-in-skype-for-business-server-2019"></a><span data-ttu-id="d0c42-103">Qué hay en Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="d0c42-103">What's in Skype for Business Server 2019</span></span>

<span data-ttu-id="d0c42-104">**Resumen:** Lea este tema para obtener información sobre las nuevas características de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d0c42-104">**Summary:** Read this topic to learn about new features in Skype for Business Server 2019.</span></span>  

<span data-ttu-id="d0c42-105">Entre las nuevas características de Skype empresarial Server 2019 se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="d0c42-105">New features in Skype for Business Server 2019 include the following:</span></span>
  
- <span data-ttu-id="d0c42-106">Correo de voz en la nube</span><span class="sxs-lookup"><span data-stu-id="d0c42-106">Cloud Voicemail</span></span>  
- <span data-ttu-id="d0c42-107">Conector de datos de llamada</span><span class="sxs-lookup"><span data-stu-id="d0c42-107">Call Data Connector</span></span>
- <span data-ttu-id="d0c42-108">Migración en paralelo</span><span class="sxs-lookup"><span data-stu-id="d0c42-108">Side-by-side migration</span></span>

## <a name="unified-messaging-services-cloud-voicemail"></a><span data-ttu-id="d0c42-109">Servicios de mensajería unificada: buzón de voz de nube</span><span class="sxs-lookup"><span data-stu-id="d0c42-109">Unified messaging services: Cloud Voicemail</span></span>

<span data-ttu-id="d0c42-110">La mensajería unificada de Exchange sigue disponible en Skype empresarial Server 2019 al integrar la 2019 de Skype empresarial con Exchange 2013 o Exchange 2016.</span><span class="sxs-lookup"><span data-stu-id="d0c42-110">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="d0c42-111">Debido a cambios en el soporte técnico de Exchange 2019, la integración de mensajería unificada de Exchange se subraya en favor del buzón de voz de nube y las características del operador automático de la nube.</span><span class="sxs-lookup"><span data-stu-id="d0c42-111">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  

<span data-ttu-id="d0c42-112">El buzón de voz de nube permite que todos los usuarios de 2019 Skype users& # x2014, ya estén locales o online& # x2014; tengan acceso al mismo servicio de correo de voz en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d0c42-112">Cloud Voicemail enables all your Skype for Business 2019 users&#x2014;whether they are homed on premises or online&#x2014;to have access to the same voicemail service in the Microsoft Cloud.</span></span> <span data-ttu-id="d0c42-113">El buzón de voz de nube ofrece las siguientes ventajas para los usuarios locales y en línea:</span><span class="sxs-lookup"><span data-stu-id="d0c42-113">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="d0c42-114">Acceso al buzón de voz en su buzón de Exchange mediante los clientes de Skype empresarial online, Teams o Outlook</span><span class="sxs-lookup"><span data-stu-id="d0c42-114">Access to voicemail in their Exchange mailbox by using the Skype for Business Online, Teams, or Outlook clients</span></span>
- <span data-ttu-id="d0c42-115">Posibilidad de usar el portal basado en web para administrar sus opciones de buzón de voz</span><span class="sxs-lookup"><span data-stu-id="d0c42-115">Ability to use the web-based portal to manage their voicemail options</span></span>

<span data-ttu-id="d0c42-116">Para obtener más información, vea [planear el servicio de buzón de voz en la nube](../sfbhybrid/hybrid/plan-cloud-voicemail.md) y el [plan de Skype empresarial Server y de la migración de Exchange Server](../sfbhybrid/hybrid/plan-um-migration.md) .</span><span class="sxs-lookup"><span data-stu-id="d0c42-116">See [Plan Cloud Voicemail service](../sfbhybrid/hybrid/plan-cloud-voicemail.md) and [Plan for Skype for Business Server and Exchange Server migration](../sfbhybrid/hybrid/plan-um-migration.md) for more information.</span></span>
  
## <a name="call-monitoring-call-data-connector"></a><span data-ttu-id="d0c42-117">Supervisión de llamadas: conector de datos de llamadas</span><span class="sxs-lookup"><span data-stu-id="d0c42-117">Call monitoring: Call Data Connector</span></span>

<span data-ttu-id="d0c42-118">El conector de datos de llamadas simplifica enormemente la supervisión de llamadas en un entorno híbrido porque ya no es necesario usar distintos conjuntos de herramientas locales y en línea para supervisar la calidad de las llamadas de todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="d0c42-118">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span>  <span data-ttu-id="d0c42-119">Ya sea que los usuarios estén locales o conectados, puede elegir ver la calidad de las llamadas de toda la organización en línea.</span><span class="sxs-lookup"><span data-stu-id="d0c42-119">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="d0c42-120">Con Call Connector, puede realizar las siguientes tareas mediante un único conjunto de herramientas:</span><span class="sxs-lookup"><span data-stu-id="d0c42-120">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="d0c42-121">Supervise la experiencia del usuario en Microsoft Teams, Skype empresarial online y Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d0c42-121">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>
- <span data-ttu-id="d0c42-122">Ver y solucionar problemas en la red</span><span class="sxs-lookup"><span data-stu-id="d0c42-122">View and troubleshoot problems across your network</span></span>
- <span data-ttu-id="d0c42-123">Asignar roles de administrador y de asistencia al usuario para el análisis de llamadas, de modo que pueda habilitar a los trabajadores del Departamento de soporte técnico para que vean y solucionen sus áreas de responsabilidad.</span><span class="sxs-lookup"><span data-stu-id="d0c42-123">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="d0c42-124">Para obtener más información, consulte [plan Call Data Connector](../sfbhybrid/hybrid/plan-call-data-connector.md) .</span><span class="sxs-lookup"><span data-stu-id="d0c42-124">See [Plan Call Data Connector](../sfbhybrid/hybrid/plan-call-data-connector.md) for more information.</span></span>

### <a name="see-also"></a><span data-ttu-id="d0c42-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0c42-125">See also</span></span>

[<span data-ttu-id="d0c42-126">Qué es en desuso de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="d0c42-126">What's deprecated from Skype for Business Server 2019</span></span>](deprecated.md)
