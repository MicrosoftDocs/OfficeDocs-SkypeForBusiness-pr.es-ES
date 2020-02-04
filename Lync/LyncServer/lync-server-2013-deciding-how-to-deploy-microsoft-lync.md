---
title: 'Lync Server 2013: Decidir cómo implementar Microsoft Lync'
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
ms.openlocfilehash: aef6ac76b6c0e8a6fb3c0444ab219acf78119ecd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deciding-how-to-deploy-lync-server-2013"></a><span data-ttu-id="50d2d-102">Decidir cómo implementar Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50d2d-102">Deciding how to deploy Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50d2d-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="50d2d-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="50d2d-104">Al planear Lync, la primera decisión importante es cómo implementar Microsoft Lync: como local de Lync Server 2013 o Lync Online con Microsoft Office 365 en la nube.</span><span class="sxs-lookup"><span data-stu-id="50d2d-104">When planning for Lync, the first major decision is how to deploy Microsoft Lync: as Lync Server 2013 on premises, or Lync Online with Microsoft Office 365 in the cloud.</span></span>

  - <span data-ttu-id="50d2d-105">**Lync Server 2013 local** : esta opción proporciona el conjunto completo de características de Lync y proporciona la máxima flexibilidad a la hora de configurar, personalizar y trabajar con la implementación.</span><span class="sxs-lookup"><span data-stu-id="50d2d-105">**Lync Server 2013 on-premises** : This choice provides the complete Lync feature set and provides ultimate flexibility in configuring, customizing, and operating your deployment.</span></span> <span data-ttu-id="50d2d-106">Todos los servidores se instalan en el sitio y los mantiene la organización.</span><span class="sxs-lookup"><span data-stu-id="50d2d-106">All servers are installed onsite and maintained by your organization.</span></span> <span data-ttu-id="50d2d-107">Una implementación local proporciona la gama completa de características de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="50d2d-107">An on-premises deployment provides the full range of Lync Server features.</span></span>

  - <span data-ttu-id="50d2d-108">**Lync Online en la nube** Lync Online está diseñado para organizaciones que desean beneficiarse de los beneficios de la mensajería instantánea, la presencia y las reuniones de la nube sin sacrificar las capacidades de clase empresarial de Lync Server basadas en la nube.</span><span class="sxs-lookup"><span data-stu-id="50d2d-108">**Lync Online in the cloud** Lync Online is designed for organizations that want the cost and agility benefits of cloud-based instant messaging, presence, and meetings without sacrificing the business-class capabilities of Lync Server.</span></span> <span data-ttu-id="50d2d-109">Con Lync Online, Microsoft implementa y mantiene la infraestructura de servidor necesaria, y administra el mantenimiento, las revisiones y las actualizaciones en curso.</span><span class="sxs-lookup"><span data-stu-id="50d2d-109">With Lync Online, Microsoft deploys and maintains the required server infrastructure, and handles ongoing maintenance, patches, and upgrades.</span></span> <span data-ttu-id="50d2d-110">Algunas de las características disponibles en una implementación local no están disponibles en Lync Online.</span><span class="sxs-lookup"><span data-stu-id="50d2d-110">Some features available in an on-premises deployment are not available in Lync Online.</span></span>

<span data-ttu-id="50d2d-111">El tipo de implementación más conveniente depende de las cargas de trabajo que desee implementar y del estado geográfico y comercial de su organización.</span><span class="sxs-lookup"><span data-stu-id="50d2d-111">Which type of deployment would be best for you depends on the workloads you want to deploy, and your organization’s geographical and business status.</span></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="50d2d-112">Lync Server</span><span class="sxs-lookup"><span data-stu-id="50d2d-112">Lync Server</span></span>

<span data-ttu-id="50d2d-113">Una implementación local de Lync Server es la mejor para los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="50d2d-113">An on-premises Lync Server deployment is best for the following scenarios:</span></span>

  - <span data-ttu-id="50d2d-114">**Capacidades completas de voz**   si piensa implementar una solución de voz empresarial completa para reemplazar su PBX o usa características avanzadas de llamada, se requiere una implementación de Lync Server local.</span><span class="sxs-lookup"><span data-stu-id="50d2d-114">**Full Enterprise Voice Capabilities**   If you plan to deploy a full Enterprise Voice solution to replace your PBX or which uses advanced calling features, an on-premises Lync Server deployment is required.</span></span> <span data-ttu-id="50d2d-115">Local admite conectividad directa con sistemas PBX y troncos, y características de teléfono avanzadas, como grupos de respuesta y estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="50d2d-115">On-premises supports direct connectivity with PBX systems and trunks, and advanced phone features such as response groups and call park.</span></span> <span data-ttu-id="50d2d-116">En este momento, Lync Online no admite estas características.</span><span class="sxs-lookup"><span data-stu-id="50d2d-116">Lync Online does not currently support these features.</span></span>

  - <span data-ttu-id="50d2d-117">**Controles de calidad multimedia**   si desea la gama completa de características de garantía de calidad multimedia, como el control de admisión de llamadas (CAC) y las características de calidad de servicio (QoS), necesitará una implementación local.</span><span class="sxs-lookup"><span data-stu-id="50d2d-117">**Media Quality Controls**   If you want the full range of media quality assurance features, such as Call Admission Control (CAC) and Quality of Service (QoS) features, you will want an on-premises deployment .</span></span>

  - <span data-ttu-id="50d2d-118">**Chat persistente si**   necesita implementar una conversación persistente para su organización, debe elegir una implementación local.</span><span class="sxs-lookup"><span data-stu-id="50d2d-118">**Persistent Chat**   If you need to deploy Persistent chat for your organization, you must choose an on-premises deployment.</span></span>

  - <span data-ttu-id="50d2d-119">**las aplicaciones**   de servidor de terceros solo pueden funcionar con aplicaciones de terceros de confianza que usen la API administrada de comunicaciones unificadas de Microsoft (UCMA).</span><span class="sxs-lookup"><span data-stu-id="50d2d-119">**3rd-Party Server Applications**   Only on-premises deployments can work with trusted 3rd-party applications that use the Microsoft Unified Communications Managed API (UCMA).</span></span>

  - <span data-ttu-id="50d2d-120">**Empresas multinacionales o multiregional que necesitan asistencia**   regional si tiene centros de información en varios países o regiones y necesita que se implementen y administren servidores de forma regional, la implementación local es la mejor, ya que proporciona este tipo de capacidades de administración regional.</span><span class="sxs-lookup"><span data-stu-id="50d2d-120">**Multi-National/Multi-Regional Companies Needing Regional Support**   If you have datacenters in multiple countries or regions and need servers to be deployed and managed on a regional basis, an on-premises deployment is best, as it provides this type of regional management capabilities.</span></span>

  - <span data-ttu-id="50d2d-121">**Control completo de las directivas, informes y actualizaciones**   con una implementación local de Lync Server, tendrá acceso al conjunto completo de directivas de servidor y de cliente, la supervisión y otros informes, y los intervalos de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="50d2d-121">**Complete control over policies, reports, and upgrades**   With an on premises Lync Server deployment, you have access to the full set of server and client policies, Monitoring and other reports, and timing of upgrades.</span></span> <span data-ttu-id="50d2d-122">Lync Online proporciona un subconjunto de los informes y la configuración de directivas, y ofrece una ventana limitada, aunque importante, para aceptar actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="50d2d-122">Lync Online provides a subset of policy setting and reports, and provides a limited, though significant, window for accepting upgrades.</span></span>

</div>

<div>

## <a name="lync-online"></a><span data-ttu-id="50d2d-123">Lync Online</span><span class="sxs-lookup"><span data-stu-id="50d2d-123">Lync Online</span></span>

<span data-ttu-id="50d2d-124">Si ninguno de los factores de la lista anterior es crítico para usted, es posible que desee elegir Lync Online, para una implementación y administración más sencillas.</span><span class="sxs-lookup"><span data-stu-id="50d2d-124">If none of the factors in the preceding list are critical for you, you may want to choose Lync Online, for simpler deployment and manageability.</span></span> <span data-ttu-id="50d2d-125">Lync Online ofrece un sólido conjunto de características de mensajería instantánea, presencia y Conferencia, y también permite llamadas de voz y vídeo a través de IP entre los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="50d2d-125">Lync Online provides a robust IM, presence and conferencing feature set, and also enables voice and video calls over IP between users in your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

