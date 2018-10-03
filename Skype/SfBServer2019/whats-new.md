---
title: Novedades de Skype Empresarial Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 7/10/2018
ms.audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumen: Estas características son nuevas en Skype para Business Server 2019.'
ms.openlocfilehash: 7b4e07ab6fbb7bfddcd056c9d6c4cd9d836d9a8e
ms.sourcegitcommit: 02ff91505a2f185bb3c1059a1b26ee31bb272438
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2018
ms.locfileid: "25027329"
---
# <a name="whats-in-skype-for-business-server-2019"></a><span data-ttu-id="54d69-103">¿Qué es en Skype para Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="54d69-103">What's in Skype for Business Server 2019</span></span> 

<span data-ttu-id="54d69-104">**Resumen:** Lea este tema para obtener más información acerca de las nuevas características de Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="54d69-104">**Summary:** Read this topic to learn about new features in Skype for Business Server 2019.</span></span>  

[!INCLUDE [disclaimer](disclaimer.md)]

<span data-ttu-id="54d69-105">Nuevas características de Skype para Business Server 2019 incluyen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="54d69-105">New features in Skype for Business Server 2019 include the following:</span></span>
  
- <span data-ttu-id="54d69-106">Correo de voz en la nube</span><span class="sxs-lookup"><span data-stu-id="54d69-106">Cloud Voicemail</span></span>  
- <span data-ttu-id="54d69-107">Conector de datos de llamada</span><span class="sxs-lookup"><span data-stu-id="54d69-107">Call Data Connector</span></span>
- <span data-ttu-id="54d69-108">Migración en paralelo</span><span class="sxs-lookup"><span data-stu-id="54d69-108">Side-by-side migration</span></span>
- <span data-ttu-id="54d69-109">Migración a los equipos</span><span class="sxs-lookup"><span data-stu-id="54d69-109">Migration to Teams</span></span>

## <a name="unified-messaging-services-cloud-voicemail"></a><span data-ttu-id="54d69-110">Servicios de mensajería unificado: correo de voz en la nube</span><span class="sxs-lookup"><span data-stu-id="54d69-110">Unified messaging services: Cloud Voicemail</span></span> 

<span data-ttu-id="54d69-111">Mensajería unificada de Exchange sigue estando disponible en Skype para Business Server 2019 al integrar Skype para la empresa 2019 con Exchange 2013 o 2016 de Exchange.</span><span class="sxs-lookup"><span data-stu-id="54d69-111">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="54d69-112">Debido a los cambios en la compatibilidad en Exchange 2019, integración de mensajería unificada de Exchange se está desaprovisionamiento emphasised en favor de las características de correo de voz en la nube y operador automático de la nube.</span><span class="sxs-lookup"><span data-stu-id="54d69-112">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasised in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  

<span data-ttu-id="54d69-113">Correo de voz en la nube permite todas su Skype para los usuarios empresariales 2019 & #x 2014; si están hospedados en local o en línea & #x 2014; tener acceso al mismo servicio de correo de voz en el Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="54d69-113">Cloud Voicemail enables all your Skype for Business 2019 users&#x2014;whether they are homed on premises or online&#x2014;to have access to the same voicemail service in the Microsoft Cloud.</span></span> <span data-ttu-id="54d69-114">Correo de voz en la nube proporciona las siguientes ventajas para los usuarios en línea y local:</span><span class="sxs-lookup"><span data-stu-id="54d69-114">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="54d69-115">Acceso al correo de voz en su buzón de Exchange mediante el uso de la Skype para clientes empresariales en línea, los equipos o Outlook</span><span class="sxs-lookup"><span data-stu-id="54d69-115">Access to voicemail in their Exchange mailbox by using the Skype for Business Online, Teams, or Outlook clients</span></span> 
- <span data-ttu-id="54d69-116">Posibilidad de usar el portal basado en web para administrar sus opciones de correo de voz</span><span class="sxs-lookup"><span data-stu-id="54d69-116">Ability to use the web-based portal to manage their voicemail options</span></span>

<span data-ttu-id="54d69-117">Para obtener más información, vea [servicio de planeación de correo de voz en la nube](hybrid/plan-cloud-voicemail.md) y [planeación de Skype para Business Server y la migración de Exchange Server](hybrid/plan-um-migration.md) .</span><span class="sxs-lookup"><span data-stu-id="54d69-117">See [Plan Cloud Voicemail service](hybrid/plan-cloud-voicemail.md) and [Plan for Skype for Business Server and Exchange Server migration](hybrid/plan-um-migration.md) for more information.</span></span>
  
## <a name="call-monitoring-call-data-connector"></a><span data-ttu-id="54d69-118">Supervisión de llamadas: conector de datos de llamada</span><span class="sxs-lookup"><span data-stu-id="54d69-118">Call monitoring: Call Data Connector</span></span>

<span data-ttu-id="54d69-119">Conector de datos de llamada simplifica en gran medida la llamada de supervisión en un entorno híbrido debido a que ya no necesita usar distintos conjuntos de herramientas en línea y local para supervisar todos los de la calidad de las llamadas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="54d69-119">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span>  <span data-ttu-id="54d69-120">Si los usuarios están hospedados en local o en línea, puede elegir ver la calidad de las llamadas para toda la organización en línea.</span><span class="sxs-lookup"><span data-stu-id="54d69-120">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="54d69-121">Con el conector de datos de llamadas, puede realizar las siguientes tareas mediante el uso de un único conjunto de herramientas:</span><span class="sxs-lookup"><span data-stu-id="54d69-121">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="54d69-122">Supervisar la experiencia del usuario a través de Microsoft Teams, Skype para profesionales en línea y Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="54d69-122">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>
- <span data-ttu-id="54d69-123">Ver y solucionar los problemas a través de la red</span><span class="sxs-lookup"><span data-stu-id="54d69-123">View and troubleshoot problems across your network</span></span>
- <span data-ttu-id="54d69-124">Asignación de roles de departamento de soporte técnico y administrador para análisis de llamadas, por lo que puede ofrecer a los trabajadores del departamento de soporte técnico ver y solucionar problemas de sus áreas de responsabilidad.</span><span class="sxs-lookup"><span data-stu-id="54d69-124">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span> 

<span data-ttu-id="54d69-125">Para obtener más información, consulte [Planeación de conector de datos de llamada](hybrid/plan-call-data-connector.md) .</span><span class="sxs-lookup"><span data-stu-id="54d69-125">See [Plan Call Data Connector](hybrid/plan-call-data-connector.md) for more information.</span></span>
  


## <a name="installation-and-upgrade-side-by-side-migration"></a><span data-ttu-id="54d69-126">Instalación y actualización: migración en paralelo</span><span class="sxs-lookup"><span data-stu-id="54d69-126">Installation and Upgrade: Side-by-side migration</span></span>

<span data-ttu-id="54d69-127">En una migración en paralelo, implementar un nuevo servidor que ejecuta Skype para Business Server 2019 junto con un servidor correspondiente que se está ejecutando una versión anterior (Skype para Business Server 2015 o Lync Server 2013) y, a continuación, transferir las operaciones al nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="54d69-127">In a side-by-side migration, you deploy a new server running Skype for Business Server 2019 alongside a corresponding server that is running a previous version (Skype for Business Server 2015 or Lync Server 2013), and then transfer operations to the new server.</span></span> <span data-ttu-id="54d69-128">Si es necesario revertir a la versión anterior, debe sólo transferir las operaciones a los servidores originales.</span><span class="sxs-lookup"><span data-stu-id="54d69-128">If it becomes necessary to roll back to the previous version, you have only to shift operations back to the original servers.</span></span> 

<span data-ttu-id="54d69-129">Para obtener información detallada, vea [migración de Skype para Business Server 2019](migration/migration-to-skype-for-business-server-2019.md).</span><span class="sxs-lookup"><span data-stu-id="54d69-129">For complete details, see [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md).</span></span>

### <a name="see-also"></a><span data-ttu-id="54d69-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="54d69-130">See also</span></span>

[<span data-ttu-id="54d69-131">¿Qué está en desuso de Skype para Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="54d69-131">What's deprecated from Skype for Business Server 2019</span></span>](deprecated.md)