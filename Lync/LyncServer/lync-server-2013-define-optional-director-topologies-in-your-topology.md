---
title: 'Lync Server 2013: definir topologías de Director opcionales en la topología'
description: 'Lync Server 2013: defina topologías de Director opcionales en la topología.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define optional Director topologies in your topology
ms:assetid: 8e9a659d-23b0-401d-b296-59c7df414d49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398717(v=OCS.15)
ms:contentKeyID: 48184808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bc82108d4277969489739fc81db07ec6f96bb96
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542660"
---
# <a name="define-optional-director-topologies-in-your-topology-for-lync-server-2013"></a><span data-ttu-id="1e3fe-103">Definir topologías de Director opcionales en la topología para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e3fe-103">Define optional Director topologies in your topology for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e3fe-104">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="1e3fe-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="1e3fe-105">Los directores de Lync Server 2013 pueden ser servidores de instancia única o se pueden instalar como un grupo de carga equilibrada de varios directores para obtener una mayor disponibilidad y capacidad.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-105">Lync Server 2013 Directors can be single-instance servers or they can be installed as a load-balanced pool of multiple Directors for higher availability and capacity.</span></span> <span data-ttu-id="1e3fe-106">Se admiten el equilibrio de carga de hardware y el equilibrio de carga del sistema de nombres de dominio (DNS).</span><span class="sxs-lookup"><span data-stu-id="1e3fe-106">Both hardware load balancing and Domain Name System (DNS) load balancing are supported.</span></span> <span data-ttu-id="1e3fe-107">En este tema se explica cómo configurar el equilibrio de carga de DNS para grupos de directores.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-107">This topic explains how to configure DNS load balancing for Director pools.</span></span>

<span data-ttu-id="1e3fe-108">Para publicar, habilitar o deshabilitar una topología correctamente al agregar o quitar un rol de servidor, debe haber iniciado sesión con un usuario que sea miembro de los grupos **RTCUniversalServerAdmins** y **Administradores de dominio**.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-108">To successfully publish, enable, or disable a topology when you add or remove a server role, you should be logged on as a user who is a member of the **RTCUniversalServerAdmins** and **Domain Admins** groups.</span></span> <span data-ttu-id="1e3fe-109">También es posible delegar los permisos apropiados para agregar roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-109">You can also delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="1e3fe-110">Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) en la documentación de implementación de servidor Standard Edition o Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="1e3fe-111">Para realizar otros cambios en la configuración, solo se necesita ser miembro del grupo **RTCUniversalServerAdmins**.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-111">For other configuration changes, only membership in the **RTCUniversalServerAdmins** group is required.</span></span>

<span data-ttu-id="1e3fe-112">En este tema se describen los pasos para definir y publicar la topología para las dos topologías de Director:</span><span class="sxs-lookup"><span data-stu-id="1e3fe-112">This topic describes the steps to define and publish the topology for the two Director topologies:</span></span>

  - <span data-ttu-id="1e3fe-113">Para definir el director (una sola instancia)</span><span class="sxs-lookup"><span data-stu-id="1e3fe-113">To define the Director (single instance)</span></span>

  - <span data-ttu-id="1e3fe-114">Para definir el Director (grupo de varios directores)</span><span class="sxs-lookup"><span data-stu-id="1e3fe-114">To define the Director (multiple Director pool)</span></span>

<div>

## <a name="to-define-the-director-single-instance"></a><span data-ttu-id="1e3fe-115">Para definir el Director (instancia única)</span><span class="sxs-lookup"><span data-stu-id="1e3fe-115">To define the Director (single instance)</span></span>

1.  <span data-ttu-id="1e3fe-116">Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-116">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="1e3fe-117">En la página de bienvenida, haga clic en **Descargar topología de la implementación existente**.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-117">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="1e3fe-118">En el cuadro de diálogo **Guardar topología como**, escriba el nombre y la ubicación de la copia local de la topología existente y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-118">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="1e3fe-119">Expanda el sitio donde desee agregar el director, haga clic con el botón secundario en **Grupos de servidores de director** y, a continuación, haga clic en **Nuevo grupo de servidores de director**.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-119">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="1e3fe-120">En el cuadro de diálogo **Definir el FQDN del grupo director**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1e3fe-120">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="1e3fe-121">En **FQDN de grupo de servidores**, escriba el FQDN del grupo de servidores de director.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-121">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="1e3fe-122">Haga clic en **Grupo de servidores de un solo equipo** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-122">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="1e3fe-123">En el cuadro de diálogo **Definir el recurso compartido de archivos**, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="1e3fe-123">In the **Define the file share** dialog box, do one of the following:</span></span>
    
    1.  <span data-ttu-id="1e3fe-124">Para usar un recurso compartido de archivos existente, haga clic en **Usar un recurso compartido de archivos definido previamente**, seleccione un recurso compartido de la lista y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-124">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
    2.  <span data-ttu-id="1e3fe-125">Para crear un nuevo recurso compartido de archivos, haga clic en **Definir un nuevo recurso compartido de archivos**, escriba el FQDN de la ubicación del recurso compartido de archivos en **FQDN de servidor de archivos**, escriba el nombre del recurso compartido en **Recurso compartido de archivos** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-125">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1e3fe-126">El recurso compartido de archivos que especifique o que cree en este paso debe existir o debe haberse creado antes de publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-126">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="1e3fe-127">En realidad, el recurso compartido de archivos asignado a un director no se usa, de modo que puede asignar el recurso compartido de archivos de cualquier grupo de servidores de la organización.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-127">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

7.  <span data-ttu-id="1e3fe-128">En el cuadro de diálogo **Especificar la URL de servicios web**, en **URL de base externa**, especifique el FQDN de los directores y haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-128">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1e3fe-129">El nombre debe poder resolverse desde los servidores DNS de Internet, y debe apuntar a la dirección IP pública del proxy inverso, que escucha las solicitudes HTTP/HTTPS a esa URL y las redirige al directorio virtual de servicios web externos de ese director.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-129">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests to that URL and proxies them to the external Web Services virtual directory on that Director.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="1e3fe-130">Si tiene más de un grupo de servidores front-end o un servidor front-end, el FQDN de los servicios web externos debe ser único.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-130">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="1e3fe-131">Por ejemplo, si define el FQDN de servicios web externos de un servidor front-end como <STRONG>pool01.contoso.com</STRONG>, no puede usar <STRONG>pool01.contoso.com</STRONG> para otro grupo de servidores front-end o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-131">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="1e3fe-132">Si también está implementando directores, el FQDN de servicios Web externo definido para cualquier Director o grupo de directores debe ser único de cualquier otro director o grupo de directores, así como cualquier grupo de servidores front-end o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-132">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="1e3fe-133">Si decide reemplazar los servicios Web internos con un FQDN autodefinido, cada FQDN debe ser único en cualquier otro grupo de servidores front-end, director o grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-133">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

8.  <span data-ttu-id="1e3fe-134">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-134">Publish the topology.</span></span>

</div>

<div>

## <a name="to-define-the-director-multiple-director-pool"></a><span data-ttu-id="1e3fe-135">Para definir el Director (grupo de directores de múltiples)</span><span class="sxs-lookup"><span data-stu-id="1e3fe-135">To define the Director (multiple Director pool)</span></span>

1.  <span data-ttu-id="1e3fe-136">Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-136">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="1e3fe-137">En la página de bienvenida, haga clic en **Descargar topología de la implementación existente**.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-137">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="1e3fe-138">En el cuadro de diálogo **Guardar topología como**, escriba el nombre y la ubicación de la copia local de la topología existente y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-138">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="1e3fe-139">Expanda el sitio donde desee agregar el director, haga clic con el botón secundario en **Grupos de servidores de director** y, a continuación, haga clic en **Nuevo grupo de servidores de director**.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-139">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="1e3fe-140">En el cuadro de diálogo **Definir el FQDN del grupo director**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1e3fe-140">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="1e3fe-141">En **FQDN de grupo de servidores**, escriba el FQDN del grupo de servidores de director.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-141">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="1e3fe-142">Haga clic en **Grupo de servidores de varios equipos** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-142">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="1e3fe-143">En el cuadro de diálogo \*\*Definir los equipos de este grupo \*\*, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1e3fe-143">In the **Define the computers in this pool** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="1e3fe-144">Especifique el FQDN de equipo del primer miembro del grupo de servidores y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-144">Specify the computer FQDN of the first pool member, and then click **Add**.</span></span>
    
      - <span data-ttu-id="1e3fe-p104">Repita el paso anterior para cada equipo que quiera agregar. Cuando haya acabado, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-p104">Repeat the previous step for each computer that you want to add. When you are finished, click **Next**.</span></span>

7.  <span data-ttu-id="1e3fe-147">En el cuadro de diálogo **Definir el recurso compartido de archivos**, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="1e3fe-147">In the **Define the file share** dialog box, do one of the following:</span></span>
    
      - <span data-ttu-id="1e3fe-148">Para usar un recurso compartido de archivos existente, haga clic en **Usar un recurso compartido de archivos definido previamente**, seleccione un recurso compartido de la lista y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-148">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
      - <span data-ttu-id="1e3fe-149">Para crear un nuevo recurso compartido de archivos, haga clic en **Definir un nuevo recurso compartido de archivos**, escriba el FQDN de la ubicación del recurso compartido de archivos en **FQDN de servidor de archivos**, escriba el nombre del recurso compartido en **Recurso compartido de archivos** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-149">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1e3fe-150">El recurso compartido de archivos que especifique o que cree en este paso debe existir o debe haberse creado antes de publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-150">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="1e3fe-151">En realidad, el recurso compartido de archivos asignado a un director no se usa, de modo que puede asignar el recurso compartido de archivos de cualquier grupo de servidores de la organización.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-151">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

8.  <span data-ttu-id="1e3fe-152">En el cuadro de diálogo **Especificar la URL de servicios web**, en **URL de base externa**, especifique el FQDN de los directores y haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-152">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1e3fe-153">El nombre debe poder resolverse en servidores DNS de Internet y debe apuntar a la dirección IP pública del proxy inverso, que escucha las solicitudes HTTP/HTTPS enviadas a la dirección URL y lo envía mediante proxy al directorio virtual de servicios web externos del grupo de servidores de director.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-153">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests sent to that URL and proxies them to the external Web Services virtual directory on that Director pool.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="1e3fe-154">Si tiene más de un grupo de servidores front-end o un servidor front-end, el FQDN de los servicios web externos debe ser único.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-154">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="1e3fe-155">Por ejemplo, si define el FQDN de servicios web externos de un servidor front-end como <STRONG>pool01.contoso.com</STRONG>, no puede usar <STRONG>pool01.contoso.com</STRONG> para otro grupo de servidores front-end o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-155">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="1e3fe-156">Si también está implementando directores, el FQDN de servicios Web externo definido para cualquier Director o grupo de directores debe ser único de cualquier otro director o grupo de directores, así como cualquier grupo de servidores front-end o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-156">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="1e3fe-157">Si decide reemplazar los servicios Web internos con un FQDN autodefinido, cada FQDN debe ser único en cualquier otro grupo de servidores front-end, director o grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-157">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

9.  <span data-ttu-id="1e3fe-158">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="1e3fe-158">Publish the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

