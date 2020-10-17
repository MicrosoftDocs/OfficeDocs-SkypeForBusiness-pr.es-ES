---
title: 'Lync Server 2013: decidir cómo implementar Microsoft Lync'
description: 'Lync Server 2013: decidir cómo implementar Microsoft Lync.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deciding how to deploy Microsoft Lync
ms:assetid: 6ca677d3-745d-4935-8f05-19274a8bccf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204979(v=OCS.15)
ms:contentKeyID: 48184423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a800b51dfddc6f2c99e42c8f117056ed4091b6a5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558106"
---
# <a name="deciding-how-to-deploy-lync-server-2013"></a><span data-ttu-id="b40ac-103">Decidir cómo implementar Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b40ac-103">Deciding how to deploy Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b40ac-104">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="b40ac-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="b40ac-105">Al planear Lync, la primera decisión importante es cómo implementar Microsoft Lync: como Lync Server 2013 local o Lync Online con Microsoft 365 u Office 365 en la nube.</span><span class="sxs-lookup"><span data-stu-id="b40ac-105">When planning for Lync, the first major decision is how to deploy Microsoft Lync: as Lync Server 2013 on premises, or Lync Online with Microsoft 365 or Office 365 in the cloud.</span></span>

  - <span data-ttu-id="b40ac-106">**Lync Server 2013 local** : esta opción proporciona el conjunto completo de características de Lync y proporciona la máxima flexibilidad para la configuración, personalización y funcionamiento de la implementación.</span><span class="sxs-lookup"><span data-stu-id="b40ac-106">**Lync Server 2013 on-premises** : This choice provides the complete Lync feature set and provides ultimate flexibility in configuring, customizing, and operating your deployment.</span></span> <span data-ttu-id="b40ac-107">La organización se encarga de instalar todos los servidores en el sitio y de su mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="b40ac-107">All servers are installed onsite and maintained by your organization.</span></span> <span data-ttu-id="b40ac-108">Una implementación local proporciona el conjunto completo de características de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b40ac-108">An on-premises deployment provides the full range of Lync Server features.</span></span>

  - <span data-ttu-id="b40ac-109">**Lync Online en la nube** Lync Online está diseñado para organizaciones que quieren obtener el costo y la agilidad de las reuniones de mensajería instantánea, presencia y reuniones basadas en la nube sin sacrificar las capacidades de clase empresarial de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b40ac-109">**Lync Online in the cloud** Lync Online is designed for organizations that want the cost and agility benefits of cloud-based instant messaging, presence, and meetings without sacrificing the business-class capabilities of Lync Server.</span></span> <span data-ttu-id="b40ac-110">Con Lync Online, Microsoft implementa y mantiene la infraestructura de servidor necesaria y controla el mantenimiento continuo, las revisiones y las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="b40ac-110">With Lync Online, Microsoft deploys and maintains the required server infrastructure, and handles ongoing maintenance, patches, and upgrades.</span></span> <span data-ttu-id="b40ac-111">Algunas de las características disponibles en una implementación local no están disponibles en Lync Online.</span><span class="sxs-lookup"><span data-stu-id="b40ac-111">Some features available in an on-premises deployment are not available in Lync Online.</span></span>

<span data-ttu-id="b40ac-112">El tipo de implementación que más le convenga dependerá de las cargas de trabajo que desee implementar y de la situación financiera y geográfica de su organización.</span><span class="sxs-lookup"><span data-stu-id="b40ac-112">Which type of deployment would be best for you depends on the workloads you want to deploy, and your organization’s geographical and business status.</span></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="b40ac-113">Lync Server</span><span class="sxs-lookup"><span data-stu-id="b40ac-113">Lync Server</span></span>

<span data-ttu-id="b40ac-114">Se recomienda implementar Lync Server si se necesitan las características siguientes:</span><span class="sxs-lookup"><span data-stu-id="b40ac-114">An on-premises Lync Server deployment is best for the following scenarios:</span></span>

  - <span data-ttu-id="b40ac-115">Capacidades completas de la **telefonía IP empresarial**     Si planea implementar una solución de telefonía IP completa para reemplazar su PBX o usa características avanzadas de llamada, se necesita una implementación local de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b40ac-115">**Full Enterprise Voice Capabilities**   If you plan to deploy a full Enterprise Voice solution to replace your PBX or which uses advanced calling features, an on-premises Lync Server deployment is required.</span></span> <span data-ttu-id="b40ac-116">La implementación local admite la conectividad directa con troncos y sistemas PBX, además de características telefónicas avanzadas como los grupos de respuesta y el Estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="b40ac-116">On-premises supports direct connectivity with PBX systems and trunks, and advanced phone features such as response groups and call park.</span></span> <span data-ttu-id="b40ac-117">Lync Online no admite estas características en este momento.</span><span class="sxs-lookup"><span data-stu-id="b40ac-117">Lync Online does not currently support these features.</span></span>

  - <span data-ttu-id="b40ac-118">Controles de calidad de **medios**     Si desea disponer de todas las características de seguridad de calidad de medios, como el control de admisión de llamadas (CAC) y las características de calidad de servicio (QoS), querrá una implementación local.</span><span class="sxs-lookup"><span data-stu-id="b40ac-118">**Media Quality Controls**   If you want the full range of media quality assurance features, such as Call Admission Control (CAC) and Quality of Service (QoS) features, you will want an on-premises deployment .</span></span>

  - <span data-ttu-id="b40ac-119">**Chat persistente**     Si tiene que implementar chat persistente en su organización, debe elegir una implementación local.</span><span class="sxs-lookup"><span data-stu-id="b40ac-119">**Persistent Chat**   If you need to deploy Persistent chat for your organization, you must choose an on-premises deployment.</span></span>

  - <span data-ttu-id="b40ac-120">Aplicaciones de servidor **de**     terceros Solo las implementaciones locales pueden funcionar con aplicaciones de terceros de confianza que usen la API administrada de comunicaciones unificadas de Microsoft (UCMA).</span><span class="sxs-lookup"><span data-stu-id="b40ac-120">**3rd-Party Server Applications**   Only on-premises deployments can work with trusted 3rd-party applications that use the Microsoft Unified Communications Managed API (UCMA).</span></span>

  - <span data-ttu-id="b40ac-121">**Empresas multinacionales y multiregionales que necesitan soporte regional**     Si tiene centros de información en varios países o regiones y necesita que los servidores se implementen y administren de manera regional, es mejor que una implementación local, ya que proporciona este tipo de capacidades de administración regionales.</span><span class="sxs-lookup"><span data-stu-id="b40ac-121">**Multi-National/Multi-Regional Companies Needing Regional Support**   If you have datacenters in multiple countries or regions and need servers to be deployed and managed on a regional basis, an on-premises deployment is best, as it provides this type of regional management capabilities.</span></span>

  - <span data-ttu-id="b40ac-122">**Control completo de las directivas, informes y actualizaciones**     Con una implementación local de Lync Server, tiene acceso a todo el conjunto de directivas de servidor y cliente, la supervisión y otros informes, y el tiempo de las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="b40ac-122">**Complete control over policies, reports, and upgrades**   With an on premises Lync Server deployment, you have access to the full set of server and client policies, Monitoring and other reports, and timing of upgrades.</span></span> <span data-ttu-id="b40ac-123">Lync Online proporciona un subconjunto de los informes y la configuración de directivas, y proporciona una ventana limitada, aunque significativa, para aceptar actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="b40ac-123">Lync Online provides a subset of policy setting and reports, and provides a limited, though significant, window for accepting upgrades.</span></span>

</div>

<div>

## <a name="lync-online"></a><span data-ttu-id="b40ac-124">Lync Online</span><span class="sxs-lookup"><span data-stu-id="b40ac-124">Lync Online</span></span>

<span data-ttu-id="b40ac-125">Si ninguno de los aspectos enumerados en la lista anterior le resulta fundamental, puede que desee escoger Lync Online para una administración e implementación más sencillas.</span><span class="sxs-lookup"><span data-stu-id="b40ac-125">If none of the factors in the preceding list are critical for you, you may want to choose Lync Online, for simpler deployment and manageability.</span></span> <span data-ttu-id="b40ac-126">Lync Online proporciona un conjunto de características de mensajería instantánea, presencia y Conferencia sólidas, y también habilita las llamadas de voz y vídeo a través de IP entre los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="b40ac-126">Lync Online provides a robust IM, presence and conferencing feature set, and also enables voice and video calls over IP between users in your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>
