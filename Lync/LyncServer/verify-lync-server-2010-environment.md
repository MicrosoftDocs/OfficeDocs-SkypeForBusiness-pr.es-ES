---
title: Comprobar el entorno de Lync Server 2010
description: Compruebe el entorno de Lync Server 2010.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify Lync Server 2010 environment
ms:assetid: bfc7c620-556a-43cd-b1ed-2c268ec2b5cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205231(v=OCS.15)
ms:contentKeyID: 48185301
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 570fd2a9efdc90899ff4f91146b7aeb1991f6764
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555586"
---
# <a name="verify-lync-server-2010-environment"></a><span data-ttu-id="fa9d6-103">Comprobar el entorno de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="fa9d6-103">Verify Lync Server 2010 environment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa9d6-104">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="fa9d6-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="fa9d6-105">Antes de implementar Lync Server 2013 en un estado de coexistencia con Lync Server 2010, debe comprobar que los servicios de Lync Server 2010 se han configurado e iniciado.</span><span class="sxs-lookup"><span data-stu-id="fa9d6-105">Before deploying Lync Server 2013 in a coexistence state with Lync Server 2010, you need to verify that Lync Server 2010 services have been configured and started.</span></span> <span data-ttu-id="fa9d6-106">Es importante identificar los servicios y características clave que existen en el entorno heredado antes de implementar un grupo piloto de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fa9d6-106">It is important to identify key services and features that exist in your legacy environment, prior to deploying a Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="fa9d6-107">Antes de implementar Microsoft Lync Server 2013 XMPP en un estado de coexistencia con una implementación de XMPP heredada, debe comprobar que los servicios de XMPP heredado se han configurado e iniciado, e identificar qué socio federado admite la configuración de XMPP heredado.</span><span class="sxs-lookup"><span data-stu-id="fa9d6-107">Before deploying Microsoft Lync Server 2013 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="fa9d6-108">La comprobación de la implementación heredada de Lync Server 2010 implica lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fa9d6-108">Verifying your legacy Lync Server 2010 deployment entails the following:</span></span>

  - <span data-ttu-id="fa9d6-109">Comprobación de que se han iniciado los servicios de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="fa9d6-109">Verifying the Lync Server 2010 services are started</span></span>

  - <span data-ttu-id="fa9d6-110">Revisión de la topología y los usuarios en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="fa9d6-110">Reviewing the topology and users in Lync Server 2010.</span></span>

  - <span data-ttu-id="fa9d6-111">Comprobar la configuración de la federación y del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="fa9d6-111">Verifying the federation and Edge server settings.</span></span>

  - <span data-ttu-id="fa9d6-112">Comprobar los servicios de XMPP y los socios federados.</span><span class="sxs-lookup"><span data-stu-id="fa9d6-112">Verifying XMPP services and federated partners.</span></span>

<span data-ttu-id="fa9d6-113">**Comprobar que se han iniciado los servicios de Lync Server 2010**</span><span class="sxs-lookup"><span data-stu-id="fa9d6-113">**Verify Lync Server 2010 Services are started**</span></span>

1.  <span data-ttu-id="fa9d6-114">Desde el servidor front-end de Lync Server 2010, vaya al \\ subprograma Servicios de herramientas administrativas.</span><span class="sxs-lookup"><span data-stu-id="fa9d6-114">From the Lync Server 2010 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="fa9d6-115">Compruebe que los servicios siguientes se están ejecutando en el servidor front-end:</span><span class="sxs-lookup"><span data-stu-id="fa9d6-115">Verify that the following services are running on the Front End Server:</span></span>
    
    <span data-ttu-id="fa9d6-116">![Lista de servicios que se ejecutan en el servidor front-end](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "Lista de servicios que se ejecutan en el servidor front-end")</span><span class="sxs-lookup"><span data-stu-id="fa9d6-116">![List of services running on Front End Server](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "List of services running on Front End Server")</span></span>

<span data-ttu-id="fa9d6-117">**Revisar la topología de Lync Server 2010 en el panel de control de Lync Server**</span><span class="sxs-lookup"><span data-stu-id="fa9d6-117">**Review the Lync Server 2010 topology in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="fa9d6-118">Inicie sesión en el servidor front-end con una cuenta que sea miembro del grupo RTCUniversalServerAdmins, o del rol administrativo CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="fa9d6-118">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="fa9d6-119">Abra el Panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa9d6-119">Open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="fa9d6-120">Seleccione **Topología**.</span><span class="sxs-lookup"><span data-stu-id="fa9d6-120">Select **Topology**.</span></span> <span data-ttu-id="fa9d6-121">Compruebe que se muestran los diversos servidores de la implementación de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="fa9d6-121">Verify that the various servers in your Lync Server 2010 deployment are listed.</span></span>
    
    <span data-ttu-id="fa9d6-122">![Página de topología del panel de control 2010 de Lync Server](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Página de topología del panel de control 2010 de Lync Server")</span><span class="sxs-lookup"><span data-stu-id="fa9d6-122">![Lync Server 2010 Control Panel topology page](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 Control Panel topology page")</span></span>

<span data-ttu-id="fa9d6-123">**Para revisar los usuarios de Lync Server 2010 en el panel de control de Lync Server**</span><span class="sxs-lookup"><span data-stu-id="fa9d6-123">**To review Lync Server 2010 users in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="fa9d6-124">Abra el Panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa9d6-124">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="fa9d6-125">Seleccione **Usuarios** y haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="fa9d6-125">Select **Users** and then click **Find**.</span></span>

3.  <span data-ttu-id="fa9d6-126">Compruebe que la columna **grupo de registrador** apunta al grupo de servidores de Lync Server 2010 para cada usuario enumerado.</span><span class="sxs-lookup"><span data-stu-id="fa9d6-126">Verify that the **Registrar Pool** column points to the Lync Server 2010 pool for each user listed.</span></span>
    
    <span data-ttu-id="fa9d6-127">![Panel de control de Lync Server 2010 enumerar usuarios](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Panel de control de Lync Server 2010 enumerar usuarios")</span><span class="sxs-lookup"><span data-stu-id="fa9d6-127">![Lync Server 2010 Control Panel listing users](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 Control Panel listing users")</span></span>

<span data-ttu-id="fa9d6-128">**Para comprobar la configuración de la Federación y el servidor perimetral de Lync Server 2010**</span><span class="sxs-lookup"><span data-stu-id="fa9d6-128">**To verify Lync Server 2010 Edge and Federation Settings**</span></span>

1.  <span data-ttu-id="fa9d6-129">Inicie el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="fa9d6-129">Start Topology Builder.</span></span>

2.  <span data-ttu-id="fa9d6-130">Seleccione **Descargar una topología desde una implementación existente**.</span><span class="sxs-lookup"><span data-stu-id="fa9d6-130">Select **Download Topology from existing deployment**.</span></span>

3.  <span data-ttu-id="fa9d6-131">Elija un nombre de archivo y guarde la topología con el tipo de archivo .tbxml predeterminado.</span><span class="sxs-lookup"><span data-stu-id="fa9d6-131">Choose a file name and save the topology with the default .tbxml file type.</span></span>

4.  <span data-ttu-id="fa9d6-132">Expanda el nodo 2010 de Lync Server para mostrar los distintos roles de servidor en la implementación.</span><span class="sxs-lookup"><span data-stu-id="fa9d6-132">Expand the Lync Server 2010 node to reveal the various server roles in the deployment.</span></span>

5.  <span data-ttu-id="fa9d6-133">Seleccione el nodo del sitio y compruebe si se ha establecido un valor de **Asignación de ruta de federación del sitio**.</span><span class="sxs-lookup"><span data-stu-id="fa9d6-133">Select the site node and verify if a **Site federation route assignment** value is set.</span></span>
    
    <span data-ttu-id="fa9d6-134">![Generador de topologías, ruta de Federación del sitio](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Generador de topologías, ruta de Federación del sitio")</span><span class="sxs-lookup"><span data-stu-id="fa9d6-134">![Topology Builder, Site Federation Route](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Topology Builder, Site Federation Route")</span></span>

6.  <span data-ttu-id="fa9d6-p103">A continuación, seleccione el grupo de servidores front-end de Standard Edition o Enterprise Edition. Determine si se ha configurado un grupo de servidores perimetrales para los medios bajo **Asociaciones**.</span><span class="sxs-lookup"><span data-stu-id="fa9d6-p103">Next, select the Standard Edition Server or Enterprise Edition front end pool. Determine if an Edge pool has been configured for Media below **Associations**.</span></span>
    
    <span data-ttu-id="fa9d6-137">![Generador de topologías que muestra servidores y grupos de servidores](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Generador de topologías que muestra servidores y grupos de servidores")</span><span class="sxs-lookup"><span data-stu-id="fa9d6-137">![Topology Builder showing servers and pools](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Topology Builder showing servers and pools")</span></span>

7.  <span data-ttu-id="fa9d6-138">Por último, seleccione el grupo de servidores perimetrales e identifique si un grupo de próximo salto se ha configurado bajo **Selección de próximo salto**.</span><span class="sxs-lookup"><span data-stu-id="fa9d6-138">Finally, select the Edge pool and identify if a Next hop pool is configured below **Next hop selection**.</span></span>
    
    <span data-ttu-id="fa9d6-139">![Generador de topologías, selección de próximo salto](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Generador de topologías, selección de próximo salto")</span><span class="sxs-lookup"><span data-stu-id="fa9d6-139">![Topology Builder, Next hop selection](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Topology Builder, Next hop selection")</span></span>

<span data-ttu-id="fa9d6-140">**Compruebe la configuración del socio federado XMPP heredado**</span><span class="sxs-lookup"><span data-stu-id="fa9d6-140">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="fa9d6-141">Desde el servidor de XMPP heredado, vaya al \\ subprograma Servicios de herramientas administrativas.</span><span class="sxs-lookup"><span data-stu-id="fa9d6-141">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="fa9d6-142">Compruebe que se haya iniciado el servicio de puerta de enlace XMPP de Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="fa9d6-142">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="fa9d6-143">![Servicio de puerta de enlace XMPP de Office Communications Server](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Servicio de puerta de enlace XMPP de Office Communications Server")</span><span class="sxs-lookup"><span data-stu-id="fa9d6-143">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

