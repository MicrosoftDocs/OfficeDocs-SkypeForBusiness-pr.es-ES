---
title: Comprobar el entorno de Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify Lync Server 2010 environment
ms:assetid: bfc7c620-556a-43cd-b1ed-2c268ec2b5cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205231(v=OCS.15)
ms:contentKeyID: 48185301
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 248d779bc43b7c3e220728222aca030036f17e00
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-lync-server-2010-environment"></a><span data-ttu-id="97d60-102">Comprobar el entorno de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="97d60-102">Verify Lync Server 2010 environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97d60-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="97d60-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="97d60-104">Antes de implementar Lync Server 2013 en un estado de coexistencia con Lync Server 2010, debe comprobar que los servicios de Lync Server 2010 se han configurado e iniciado.</span><span class="sxs-lookup"><span data-stu-id="97d60-104">Before deploying Lync Server 2013 in a coexistence state with Lync Server 2010, you need to verify that Lync Server 2010 services have been configured and started.</span></span> <span data-ttu-id="97d60-105">Es importante identificar los servicios clave y las características que existen en el entorno heredado antes de implementar un grupo de pruebas piloto de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="97d60-105">It is important to identify key services and features that exist in your legacy environment, prior to deploying a Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="97d60-106">Antes de implementar Microsoft Lync Server 2013 XMPP en un estado de coexistencia con una implementación de XMPP heredada, debe comprobar que los servicios de XMPP heredado se han configurado e iniciado, e identificar qué socio federado son compatibles con la configuración del XMPP heredado.</span><span class="sxs-lookup"><span data-stu-id="97d60-106">Before deploying Microsoft Lync Server 2013 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="97d60-107">Comprobar la implementación heredada de Lync Server 2010 conlleva lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="97d60-107">Verifying your legacy Lync Server 2010 deployment entails the following:</span></span>

  - <span data-ttu-id="97d60-108">Comprobar que los servicios de Lync Server 2010 se han iniciado</span><span class="sxs-lookup"><span data-stu-id="97d60-108">Verifying the Lync Server 2010 services are started</span></span>

  - <span data-ttu-id="97d60-109">Revisar la topología y los usuarios en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="97d60-109">Reviewing the topology and users in Lync Server 2010.</span></span>

  - <span data-ttu-id="97d60-110">Comprobar la configuración del servidor perimetral y la Federación.</span><span class="sxs-lookup"><span data-stu-id="97d60-110">Verifying the federation and Edge server settings.</span></span>

  - <span data-ttu-id="97d60-111">Verificación de los servicios XMPP y los socios federados.</span><span class="sxs-lookup"><span data-stu-id="97d60-111">Verifying XMPP services and federated partners.</span></span>

<span data-ttu-id="97d60-112">**Comprobar que los servicios de Lync Server 2010 se han iniciado**</span><span class="sxs-lookup"><span data-stu-id="97d60-112">**Verify Lync Server 2010 Services are started**</span></span>

1.  <span data-ttu-id="97d60-113">En el servidor front-end de Lync Server 2010, vaya al subprograma Servicios de herramientas\\administrativas.</span><span class="sxs-lookup"><span data-stu-id="97d60-113">From the Lync Server 2010 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="97d60-114">Compruebe que se están ejecutando los siguientes servicios en el servidor front-end:</span><span class="sxs-lookup"><span data-stu-id="97d60-114">Verify that the following services are running on the Front End Server:</span></span>
    
    <span data-ttu-id="97d60-115">![Lista de servicios que se ejecutan en el servidor front-end] (images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "Lista de servicios que se ejecutan en el servidor front-end")</span><span class="sxs-lookup"><span data-stu-id="97d60-115">![List of services running on Front End Server](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "List of services running on Front End Server")</span></span>

<span data-ttu-id="97d60-116">**Revisar la topología de Lync Server 2010 en el panel de control de Lync Server**</span><span class="sxs-lookup"><span data-stu-id="97d60-116">**Review the Lync Server 2010 topology in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="97d60-117">Inicie sesión en el servidor front-end con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o miembro del rol administrativo CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="97d60-117">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="97d60-118">Abra el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="97d60-118">Open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="97d60-119">Seleccione **topología**.</span><span class="sxs-lookup"><span data-stu-id="97d60-119">Select **Topology**.</span></span> <span data-ttu-id="97d60-120">Compruebe que se muestran los diversos servidores de su implementación de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="97d60-120">Verify that the various servers in your Lync Server 2010 deployment are listed.</span></span>
    
    <span data-ttu-id="97d60-121">![Página de topología del panel de Control 2010 de Lync Server] (images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Página de topología del panel de Control 2010 de Lync Server")</span><span class="sxs-lookup"><span data-stu-id="97d60-121">![Lync Server 2010 Control Panel topology page](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 Control Panel topology page")</span></span>

<span data-ttu-id="97d60-122">**Para revisar los usuarios de Lync Server 2010 en el panel de control de Lync Server**</span><span class="sxs-lookup"><span data-stu-id="97d60-122">**To review Lync Server 2010 users in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="97d60-123">Abra el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="97d60-123">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="97d60-124">Seleccione **usuarios** y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="97d60-124">Select **Users** and then click **Find**.</span></span>

3.  <span data-ttu-id="97d60-125">Compruebe que la columna **registrar grupo** apunta al grupo de servidores de Lync 2010 para cada usuario de la lista.</span><span class="sxs-lookup"><span data-stu-id="97d60-125">Verify that the **Registrar Pool** column points to the Lync Server 2010 pool for each user listed.</span></span>
    
    <span data-ttu-id="97d60-126">![Panel de control de 2010 de Lync Server] (images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Panel de control de 2010 de Lync Server")</span><span class="sxs-lookup"><span data-stu-id="97d60-126">![Lync Server 2010 Control Panel listing users](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 Control Panel listing users")</span></span>

<span data-ttu-id="97d60-127">**Para comprobar la configuración de Edge y de Federación de Lync Server 2010**</span><span class="sxs-lookup"><span data-stu-id="97d60-127">**To verify Lync Server 2010 Edge and Federation Settings**</span></span>

1.  <span data-ttu-id="97d60-128">Iniciar el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="97d60-128">Start Topology Builder.</span></span>

2.  <span data-ttu-id="97d60-129">Seleccione **Descargar topología de la implementación existente**.</span><span class="sxs-lookup"><span data-stu-id="97d60-129">Select **Download Topology from existing deployment**.</span></span>

3.  <span data-ttu-id="97d60-130">Elija un nombre de archivo y guarde la topología con el tipo de archivo default. tbxml.</span><span class="sxs-lookup"><span data-stu-id="97d60-130">Choose a file name and save the topology with the default .tbxml file type.</span></span>

4.  <span data-ttu-id="97d60-131">Expanda el nodo de 2010 de Lync Server para mostrar los distintos roles de servidor en la implementación.</span><span class="sxs-lookup"><span data-stu-id="97d60-131">Expand the Lync Server 2010 node to reveal the various server roles in the deployment.</span></span>

5.  <span data-ttu-id="97d60-132">Seleccione el nodo de sitio y compruebe si se ha establecido un valor de **asignación de enrutamiento de Federación de sitios** .</span><span class="sxs-lookup"><span data-stu-id="97d60-132">Select the site node and verify if a **Site federation route assignment** value is set.</span></span>
    
    <span data-ttu-id="97d60-133">![Generador de topologías, ruta de Federación de sitios] (images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Generador de topologías, ruta de Federación de sitios")</span><span class="sxs-lookup"><span data-stu-id="97d60-133">![Topology Builder, Site Federation Route](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Topology Builder, Site Federation Route")</span></span>

6.  <span data-ttu-id="97d60-134">A continuación, seleccione el servidor Standard Edition o el grupo de servidores front-end Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="97d60-134">Next, select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="97d60-135">Determine si un grupo de medios se ha configurado para los medios por debajo de las **asociaciones**.</span><span class="sxs-lookup"><span data-stu-id="97d60-135">Determine if an Edge pool has been configured for Media below **Associations**.</span></span>
    
    <span data-ttu-id="97d60-136">![Generador de topología que muestra servidores y pools] (images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Generador de topología que muestra servidores y pools")</span><span class="sxs-lookup"><span data-stu-id="97d60-136">![Topology Builder showing servers and pools](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Topology Builder showing servers and pools")</span></span>

7.  <span data-ttu-id="97d60-137">Por último, seleccione el grupo de bordes y identifique si un grupo de saltos siguiente está configurado por debajo de la **selección de próximos saltos**.</span><span class="sxs-lookup"><span data-stu-id="97d60-137">Finally, select the Edge pool and identify if a Next hop pool is configured below **Next hop selection**.</span></span>
    
    <span data-ttu-id="97d60-138">![Generador de topologías, selección del próximo salto] (images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Generador de topologías, selección del próximo salto")</span><span class="sxs-lookup"><span data-stu-id="97d60-138">![Topology Builder, Next hop selection](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Topology Builder, Next hop selection")</span></span>

<span data-ttu-id="97d60-139">**Comprobar la configuración heredada del socio XMPP federado**</span><span class="sxs-lookup"><span data-stu-id="97d60-139">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="97d60-140">Desde el servidor XMPP heredado, vaya al subprograma\\servicios de herramientas administrativas.</span><span class="sxs-lookup"><span data-stu-id="97d60-140">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="97d60-141">Compruebe que se ha iniciado el servicio de puerta de enlace XMPP de Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="97d60-141">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="97d60-142">![Servicio de puerta de enlace XMPP de Office Communications Server] (images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Servicio de puerta de enlace XMPP de Office Communications Server")</span><span class="sxs-lookup"><span data-stu-id="97d60-142">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

