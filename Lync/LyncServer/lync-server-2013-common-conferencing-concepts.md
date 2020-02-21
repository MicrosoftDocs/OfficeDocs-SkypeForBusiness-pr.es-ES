---
title: 'Lync Server 2013: conceptos comunes de conferencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common conferencing concepts
ms:assetid: a21d4987-1c0a-44c8-8a39-9c17ffb57f3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688158(v=OCS.15)
ms:contentKeyID: 49733762
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2afd309f59a66a7117d43b930500a7807d493d1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="common-conferencing-concepts-in-lync-server-2013"></a><span data-ttu-id="593b3-102">Conceptos comunes de conferencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="593b3-102">Common conferencing concepts in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="593b3-103">_**Última modificación del tema:** 2012-09-19_</span><span class="sxs-lookup"><span data-stu-id="593b3-103">_**Topic Last Modified:** 2012-09-19_</span></span>

<span data-ttu-id="593b3-p101">Todos los tipos de conferencias tienen varios conceptos en común. Se describen en las siguientes secciones.</span><span class="sxs-lookup"><span data-stu-id="593b3-p101">Several concepts are common to all types of conferencing. These are described in the following sections.</span></span>

<div>

## <a name="policies-and-bandwidth-management"></a><span data-ttu-id="593b3-106">Directivas y administración de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="593b3-106">Policies and Bandwidth Management</span></span>

<span data-ttu-id="593b3-107">Lync Server 2013 permite a los administradores establecer directivas para los tipos de reuniones que los usuarios pueden organizar.</span><span class="sxs-lookup"><span data-stu-id="593b3-107">Lync Server 2013 enables administrators to set policies for the types of meetings that users can organize.</span></span> <span data-ttu-id="593b3-108">Esto ayuda a aplicar las directivas de la organización y a controlar el uso de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="593b3-108">This helps you enforce your organization’s policies and control bandwidth usage.</span></span> <span data-ttu-id="593b3-109">Puede definirse una gran variedad de directivas de reunión y asignarlas a usuarios individuales y grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="593b3-109">You can define a wide variety of meeting policies, and assign them to individual users and groups of users.</span></span> <span data-ttu-id="593b3-110">También se pueden establecer las directivas que rigen las conversaciones de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="593b3-110">You can also set policies that govern peer-to-peer conversations.</span></span> <span data-ttu-id="593b3-111">Para obtener más información sobre cómo establecer directivas de conferencia, consulte [directivas de conferencia en Lync Server 2013](lync-server-2013-conferencing-policies.md) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="593b3-111">For details about setting conferencing policies, see [Conferencing policies in Lync Server 2013](lync-server-2013-conferencing-policies.md) in the Operations documentation.</span></span> <span data-ttu-id="593b3-112">Para obtener más información acerca de la administración del ancho de banda, consulte [información general sobre el control de admisión de llamadas en Lync server 2013](lync-server-2013-overview-of-call-admission-control.md) y [configurar el ancho de banda de vídeo en Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span><span class="sxs-lookup"><span data-stu-id="593b3-112">For details about bandwidth management, see [Overview of call admission control in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md) and [Configuring video bandwidth in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span></span>

</div>

<div>

## <a name="archiving-and-compliance-features"></a><span data-ttu-id="593b3-113">Características de Archivado y Cumplimiento</span><span class="sxs-lookup"><span data-stu-id="593b3-113">Archiving and Compliance Features</span></span>

<span data-ttu-id="593b3-114">Lync Server 2013 proporciona características que puede usar si su organización debe seguir las normas de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="593b3-114">Lync Server 2013 provides features you can use if your organization must follow compliance regulations.</span></span> <span data-ttu-id="593b3-115">Pueden usarse las capacidades de archivado para archivar contenido presentado en las reuniones, así como el contenido de conversaciones y conferencias de mensajería instantánea (MI).</span><span class="sxs-lookup"><span data-stu-id="593b3-115">You can use the archiving abilities to archive content presented in meetings, and also the content of instant messaging (IM) conversations and IM conferences.</span></span> <span data-ttu-id="593b3-116">Para obtener más información, consulte [planeación del archivado en Lync Server 2013](lync-server-2013-planning-for-archiving.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="593b3-116">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span> <span data-ttu-id="593b3-117">Puede usar las características de cumplimiento de Servidor de Chat persistente para archivar conversaciones con varios participantes y basadas en temas que persistan durante mucho tiempo.</span><span class="sxs-lookup"><span data-stu-id="593b3-117">You can use compliance features of Persistent Chat Server to archive multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="593b3-118">Para obtener más información, consulte [Planning for persistent chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="593b3-118">For details, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="monitoring-feature"></a><span data-ttu-id="593b3-119">Función de supervisión</span><span class="sxs-lookup"><span data-stu-id="593b3-119">Monitoring Feature</span></span>

<span data-ttu-id="593b3-120">La característica de servidor de supervisión puede capturar registros de detalles de llamadas (CDR), que puede usar para realizar un seguimiento de los usuarios que hablan a otros usuarios que usan Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="593b3-120">The Monitoring Server feature can capture call detail records (CDRs), which you can use to track which users talk to which other users using Lync Server 2013.</span></span> <span data-ttu-id="593b3-121">Para obtener más información sobre la implementación y la configuración de la supervisión, consulte [Deploying Monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span><span class="sxs-lookup"><span data-stu-id="593b3-121">For details about deploying and configuring monitoring, see [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span></span>

</div>

<div>

## <a name="enabling-external-participation-in-conferences"></a><span data-ttu-id="593b3-122">Habilitar la participación externa en conferencias</span><span class="sxs-lookup"><span data-stu-id="593b3-122">Enabling External Participation in Conferences</span></span>

<span data-ttu-id="593b3-123">Puede aumentar en gran medida los beneficios de su inversión en conferencias de Lync Server 2013 al habilitar a los usuarios externos para que también participen en conferencias cuando se les invite.</span><span class="sxs-lookup"><span data-stu-id="593b3-123">You can greatly increase the benefits of your investment in Lync Server 2013 conferencing by enabling external users to also participate in conferences when invited.</span></span> <span data-ttu-id="593b3-124">Entre los usuarios externos se pueden incluir:</span><span class="sxs-lookup"><span data-stu-id="593b3-124">External users can include:</span></span>

  - <span data-ttu-id="593b3-125">**Usuarios remotos**   los propios usuarios de su organización, cuando trabajan fuera de los firewalls y están usando sus equipos portátiles u otros dispositivos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="593b3-125">**Remote Users**   Your organization’s own users, when they are working outside your firewalls and are using their laptops or other Lync Server 2013 devices.</span></span>

  - <span data-ttu-id="593b3-126">**Usuarios federados**   usuarios de empresas con las que trabaja y que también ejecutan Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="593b3-126">**Federated Users**   Users from companies you work with who also run Lync Server 2013.</span></span> <span data-ttu-id="593b3-127">Para habilitar a sus usuarios para que se pongan en contacto fácilmente con estos usuarios, cree relaciones federadas con estas compañías.</span><span class="sxs-lookup"><span data-stu-id="593b3-127">To enable your users to easily contact these users, you create federated relationships with these companies.</span></span>

  - <span data-ttu-id="593b3-128">**Usuarios anónimos**   todos los usuarios externos que han invitado específicamente a los usuarios a unirse a conferencias específicas.</span><span class="sxs-lookup"><span data-stu-id="593b3-128">**Anonymous Users**   Any other external users who are invited specifically by your users to join specific conferences.</span></span> <span data-ttu-id="593b3-129">Un organizador de reuniones de su compañía puede enviar una invitación por correo electrónico a un usuario externo para una conferencia.</span><span class="sxs-lookup"><span data-stu-id="593b3-129">A meeting organizer in your company can send an email invitation for a conference to an external user.</span></span> <span data-ttu-id="593b3-130">El correo electrónico incluye un vínculo en el que el usuario externo puede hacer clic para unirse a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="593b3-130">The email includes a link that the outside user can click to join the conference.</span></span>

<span data-ttu-id="593b3-131">Para habilitar uno o todos estos escenarios, debe implementar un servidor perimetral que ayude a habilitar las comunicaciones seguras entre la implementación de Lync Server 2013 y los usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="593b3-131">To enable any or all of these scenarios, you need to deploy an Edge Server to help enable secure communications between your Lync Server 2013 deployment and external users.</span></span> <span data-ttu-id="593b3-132">La solución Lync Server 2013 con servidores perimetrales proporciona una mayor calidad de medios que otras soluciones, como una red privada virtual (VPN).</span><span class="sxs-lookup"><span data-stu-id="593b3-132">The Lync Server 2013 solution using Edge Servers provides higher quality media than other solutions such as a virtual private network (VPN).</span></span> <span data-ttu-id="593b3-133">Para obtener más información, consulte [planeación del acceso de usuarios externos en Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="593b3-133">For details, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span></span>

<span data-ttu-id="593b3-134">Además, tanto si su organización implementa o no servidores perimetrales, puede habilitar usuarios (ya sean de dentro o de fuera de la organización) para que realicen marcados desde teléfonos RTC para unirse a conferencias de audio locales.</span><span class="sxs-lookup"><span data-stu-id="593b3-134">Additionally, whether or not you deploy Edge Servers, you can enable users (that is, either inside or outside your organization) to dial in from standard PSTN phones to join on-premises audio conferences.</span></span> <span data-ttu-id="593b3-135">Esto se logra mediante la implementación de la Conferencia de acceso telefónico local 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="593b3-135">This is accomplished by deploying Lync Server 2013 dial-in conferencing.</span></span>

</div>

<div>

## <a name="compatibility-among-meeting-types-and-client-versions"></a><span data-ttu-id="593b3-136">Compatibilidad entre tipos de reunión y versiones de cliente</span><span class="sxs-lookup"><span data-stu-id="593b3-136">Compatibility Among Meeting Types and Client Versions</span></span>

<span data-ttu-id="593b3-137">Si va a hacer que Lync Server 2013 interopere con versiones anteriores de Office Communications Server y sus clientes, debe tener en cuenta los siguientes problemas:</span><span class="sxs-lookup"><span data-stu-id="593b3-137">If you are going to have Lync Server 2013 interoperate with previous versions of Office Communications Server and its clients, you must be aware of the following issues:</span></span>

  - <span data-ttu-id="593b3-138">Los usuarios que usan Lync Server 2013 no pueden programar conferencias de Live Meeting ni modificar ninguna reunión migrada de este tipo.</span><span class="sxs-lookup"><span data-stu-id="593b3-138">Users using Lync Server 2013 cannot schedule Live Meeting conferences, or modify any migrated meetings of this type.</span></span>

  - <span data-ttu-id="593b3-139">Los usuarios que usan Lync Server 2013 y deben asistir a conferencias de Live Meeting hospedadas en servidores que ejecutan Office Communications Server 2007 R2 deben tener el cliente de Live Meeting instalado en su equipo (además de Lync Server 2013) para asistir a estas reuniones.</span><span class="sxs-lookup"><span data-stu-id="593b3-139">Users using Lync Server 2013 who need to attend Live Meeting conferences hosted on servers running Office Communications Server 2007 R2 must have the Live Meeting client installed on their computer (in addition to Lync Server 2013) to attend these meetings.</span></span>

  - <span data-ttu-id="593b3-140">Cuando se migran conferencias de Live Meeting a Lync Server 2013, el contenido de la reunión no se migra.</span><span class="sxs-lookup"><span data-stu-id="593b3-140">When Live Meeting conferences are migrated to Lync Server 2013, meeting content does not migrate.</span></span> <span data-ttu-id="593b3-141">Si necesita dicho contenido, deberá volver a cargarlo.</span><span class="sxs-lookup"><span data-stu-id="593b3-141">If this content is needed, it must be uploaded again.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

