---
title: Novedades de Skype empresarial Server 2019 | Ofrece
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumen: estas características son nuevas en Skype empresarial Server 2019.'
ms.openlocfilehash: 86a8ce580a8aafcfb487a4b0cf839cd001dace8f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42129403"
---
# <a name="whats-in-skype-for-business-server-2019"></a><span data-ttu-id="6c660-103">Contenido de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="6c660-103">What's in Skype for Business Server 2019</span></span>

<span data-ttu-id="6c660-104">**Resumen:** Lea este tema para obtener información sobre las nuevas características de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6c660-104">**Summary:** Read this topic to learn about new features in Skype for Business Server 2019.</span></span>  

<span data-ttu-id="6c660-105">Entre las nuevas características de Skype empresarial Server 2019 se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="6c660-105">New features in Skype for Business Server 2019 include the following:</span></span>
  
- <span data-ttu-id="6c660-106">Correo de voz de nube</span><span class="sxs-lookup"><span data-stu-id="6c660-106">Cloud Voicemail</span></span>  
- <span data-ttu-id="6c660-107">Conector de datos de llamada</span><span class="sxs-lookup"><span data-stu-id="6c660-107">Call Data Connector</span></span>
- <span data-ttu-id="6c660-108">Migración en paralelo</span><span class="sxs-lookup"><span data-stu-id="6c660-108">Side-by-side migration</span></span>

## <a name="unified-messaging-services-cloud-voicemail"></a><span data-ttu-id="6c660-109">Servicios de mensajería unificada: correo de voz de la nube</span><span class="sxs-lookup"><span data-stu-id="6c660-109">Unified messaging services: Cloud Voicemail</span></span>

<span data-ttu-id="6c660-110">La mensajería unificada de Exchange sigue disponible en Skype empresarial Server 2019 al integrar Skype empresarial 2019 con Exchange 2013 o Exchange 2016.</span><span class="sxs-lookup"><span data-stu-id="6c660-110">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="6c660-111">Debido a los cambios en la compatibilidad de Exchange 2019, la integración de la mensajería unificada de Exchange se desenfatiza en favor del correo de voz de nube y las características del operador automático de la nube.</span><span class="sxs-lookup"><span data-stu-id="6c660-111">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  

<span data-ttu-id="6c660-112">El correo de voz de nube permite que todos los usuarios de Skype empresarial 2019&#x2014;si están hospedados en instalaciones locales o en línea&#x2014;tener acceso al mismo servicio de correo de voz en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6c660-112">Cloud Voicemail enables all your Skype for Business 2019 users&#x2014;whether they are homed on premises or online&#x2014;to have access to the same voicemail service in the Microsoft Cloud.</span></span> <span data-ttu-id="6c660-113">El correo de voz de nube proporciona las siguientes ventajas tanto para los usuarios locales como en los en línea:</span><span class="sxs-lookup"><span data-stu-id="6c660-113">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="6c660-114">Acceso al correo de voz en su buzón de Exchange mediante los clientes de Skype empresarial online, Teams o Outlook</span><span class="sxs-lookup"><span data-stu-id="6c660-114">Access to voicemail in their Exchange mailbox by using the Skype for Business Online, Teams, or Outlook clients</span></span>
- <span data-ttu-id="6c660-115">Capacidad de usar el portal basado en web para administrar las opciones de correo de voz</span><span class="sxs-lookup"><span data-stu-id="6c660-115">Ability to use the web-based portal to manage their voicemail options</span></span>

<span data-ttu-id="6c660-116">Para obtener más información, vea [planear el servicio de correo de voz en la nube](../sfbhybrid/hybrid/plan-cloud-voicemail.md) y el [Plan for Skype for Business Server and Exchange Server Migration](../sfbhybrid/hybrid/plan-um-migration.md) .</span><span class="sxs-lookup"><span data-stu-id="6c660-116">See [Plan Cloud Voicemail service](../sfbhybrid/hybrid/plan-cloud-voicemail.md) and [Plan for Skype for Business Server and Exchange Server migration](../sfbhybrid/hybrid/plan-um-migration.md) for more information.</span></span>
  
## <a name="call-monitoring-call-data-connector"></a><span data-ttu-id="6c660-117">Supervisión de llamadas: conector de datos de llamadas</span><span class="sxs-lookup"><span data-stu-id="6c660-117">Call monitoring: Call Data Connector</span></span>

<span data-ttu-id="6c660-118">Call Data Connector simplifica enormemente la supervisión de llamadas en un entorno híbrido porque ya no es necesario usar distintos conjuntos de herramientas locales y en línea para supervisar a todos los usuarios la calidad de las llamadas.</span><span class="sxs-lookup"><span data-stu-id="6c660-118">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span>  <span data-ttu-id="6c660-119">Independientemente de si los usuarios están hospedados en local o en línea, puede elegir ver la calidad de las llamadas de toda la organización en línea.</span><span class="sxs-lookup"><span data-stu-id="6c660-119">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="6c660-120">Con el conector de datos de llamada, puede realizar las siguientes tareas mediante un único conjunto de herramientas:</span><span class="sxs-lookup"><span data-stu-id="6c660-120">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="6c660-121">Supervise la experiencia del usuario en Microsoft Teams, en Skype empresarial online y en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="6c660-121">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>
- <span data-ttu-id="6c660-122">Ver y solucionar problemas en la red</span><span class="sxs-lookup"><span data-stu-id="6c660-122">View and troubleshoot problems across your network</span></span>
- <span data-ttu-id="6c660-123">Asignar roles de administrador y de asistencia técnica a los análisis de llamadas, de modo que pueda hacer que los trabajadores del Departamento de soporte vean y solucionen problemas de sus áreas de responsabilidad.</span><span class="sxs-lookup"><span data-stu-id="6c660-123">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="6c660-124">Consulte [plan Call Data Connector](../sfbhybrid/hybrid/plan-call-data-connector.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="6c660-124">See [Plan Call Data Connector](../sfbhybrid/hybrid/plan-call-data-connector.md) for more information.</span></span>

### <a name="see-also"></a><span data-ttu-id="6c660-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c660-125">See also</span></span>

[<span data-ttu-id="6c660-126">Qué está en desuso en Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="6c660-126">What's deprecated from Skype for Business Server 2019</span></span>](deprecated.md)
