---
title: 'Lync Server 2013: definir topologías de Director opcionales en la topología'
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
ms.openlocfilehash: e1da76c885eb290673836f518ab9a1bac9e516c3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-optional-director-topologies-in-your-topology-for-lync-server-2013"></a><span data-ttu-id="454ec-102">Definir topologías de Director opcionales en la topología para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="454ec-102">Define optional Director topologies in your topology for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="454ec-103">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="454ec-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="454ec-104">Los directores de Lync Server 2013 pueden ser servidores de instancia única o se pueden instalar como un grupo de carga equilibrada de varios directores para obtener una mayor disponibilidad y capacidad.</span><span class="sxs-lookup"><span data-stu-id="454ec-104">Lync Server 2013 Directors can be single-instance servers or they can be installed as a load-balanced pool of multiple Directors for higher availability and capacity.</span></span> <span data-ttu-id="454ec-105">Se admiten el equilibrio de carga de hardware y el equilibrio de carga del sistema de nombres de dominio (DNS).</span><span class="sxs-lookup"><span data-stu-id="454ec-105">Both hardware load balancing and Domain Name System (DNS) load balancing are supported.</span></span> <span data-ttu-id="454ec-106">En este tema se explica cómo configurar el equilibrio de carga de DNS para grupos de directores.</span><span class="sxs-lookup"><span data-stu-id="454ec-106">This topic explains how to configure DNS load balancing for Director pools.</span></span>

<span data-ttu-id="454ec-107">Para publicar, habilitar o deshabilitar una topología correctamente al agregar o quitar un rol de servidor, debe haber iniciado sesión con un usuario que sea miembro de los grupos **RTCUniversalServerAdmins** y **Administradores de dominio**.</span><span class="sxs-lookup"><span data-stu-id="454ec-107">To successfully publish, enable, or disable a topology when you add or remove a server role, you should be logged on as a user who is a member of the **RTCUniversalServerAdmins** and **Domain Admins** groups.</span></span> <span data-ttu-id="454ec-108">También es posible delegar los permisos apropiados para agregar roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="454ec-108">You can also delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="454ec-109">Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) en la documentación de implementación de servidor Standard Edition o Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="454ec-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="454ec-110">Para realizar otros cambios en la configuración, solo se necesita ser miembro del grupo **RTCUniversalServerAdmins**.</span><span class="sxs-lookup"><span data-stu-id="454ec-110">For other configuration changes, only membership in the **RTCUniversalServerAdmins** group is required.</span></span>

<span data-ttu-id="454ec-111">En este tema se describen los pasos para definir y publicar la topología para las dos topologías de Director:</span><span class="sxs-lookup"><span data-stu-id="454ec-111">This topic describes the steps to define and publish the topology for the two Director topologies:</span></span>

  - <span data-ttu-id="454ec-112">Para definir el director (una sola instancia)</span><span class="sxs-lookup"><span data-stu-id="454ec-112">To define the Director (single instance)</span></span>

  - <span data-ttu-id="454ec-113">Para definir el Director (grupo de varios directores)</span><span class="sxs-lookup"><span data-stu-id="454ec-113">To define the Director (multiple Director pool)</span></span>

<div>

## <a name="to-define-the-director-single-instance"></a><span data-ttu-id="454ec-114">Para definir el Director (instancia única)</span><span class="sxs-lookup"><span data-stu-id="454ec-114">To define the Director (single instance)</span></span>

1.  <span data-ttu-id="454ec-115">Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="454ec-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="454ec-116">En la página de bienvenida, haga clic en **Descargar topología de la implementación existente**.</span><span class="sxs-lookup"><span data-stu-id="454ec-116">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="454ec-117">En el cuadro de diálogo **Guardar topología como**, escriba el nombre y la ubicación de la copia local de la topología existente y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="454ec-117">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="454ec-118">Expanda el sitio donde desee agregar el director, haga clic con el botón secundario en **Grupos de servidores de director** y, a continuación, haga clic en **Nuevo grupo de servidores de director**.</span><span class="sxs-lookup"><span data-stu-id="454ec-118">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="454ec-119">En el cuadro de diálogo **Definir el FQDN del grupo director**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="454ec-119">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="454ec-120">En **FQDN de grupo de servidores**, escriba el FQDN del grupo de servidores de director.</span><span class="sxs-lookup"><span data-stu-id="454ec-120">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="454ec-121">Haga clic en **Grupo de servidores de un solo equipo** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="454ec-121">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="454ec-122">En el cuadro de diálogo **Definir el recurso compartido de archivos**, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="454ec-122">In the **Define the file share** dialog box, do one of the following:</span></span>
    
    1.  <span data-ttu-id="454ec-123">Para usar un recurso compartido de archivos existente, haga clic en **Usar un recurso compartido de archivos definido previamente**, seleccione un recurso compartido de la lista y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="454ec-123">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
    2.  <span data-ttu-id="454ec-124">Para crear un nuevo recurso compartido de archivos, haga clic en **Definir un nuevo recurso compartido de archivos**, escriba el FQDN de la ubicación del recurso compartido de archivos en **FQDN de servidor de archivos**, escriba el nombre del recurso compartido en **Recurso compartido de archivos** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="454ec-124">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="454ec-125">El recurso compartido de archivos que especifique o que cree en este paso debe existir o debe haberse creado antes de publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="454ec-125">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="454ec-126">En realidad, el recurso compartido de archivos asignado a un director no se usa, de modo que puede asignar el recurso compartido de archivos de cualquier grupo de servidores de la organización.</span><span class="sxs-lookup"><span data-stu-id="454ec-126">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

7.  <span data-ttu-id="454ec-127">En el cuadro de diálogo **Especificar la URL de servicios web**, en **URL de base externa**, especifique el FQDN de los directores y haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="454ec-127">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="454ec-128">El nombre debe poder resolverse desde los servidores DNS de Internet, y debe apuntar a la dirección IP pública del proxy inverso, que escucha las solicitudes HTTP/HTTPS a esa URL y las redirige al directorio virtual de servicios web externos de ese director.</span><span class="sxs-lookup"><span data-stu-id="454ec-128">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests to that URL and proxies them to the external Web Services virtual directory on that Director.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="454ec-129">Si tiene más de un grupo de servidores front-end o un servidor front-end, el FQDN de los servicios web externos debe ser único.</span><span class="sxs-lookup"><span data-stu-id="454ec-129">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="454ec-130">Por ejemplo, si define el FQDN de servicios web externos de un servidor front-end como <STRONG>pool01.contoso.com</STRONG>, no puede usar <STRONG>pool01.contoso.com</STRONG> para otro grupo de servidores front-end o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="454ec-130">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="454ec-131">Si también está implementando directores, el FQDN de servicios Web externo definido para cualquier Director o grupo de directores debe ser único de cualquier otro director o grupo de directores, así como cualquier grupo de servidores front-end o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="454ec-131">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="454ec-132">Si decide reemplazar los servicios Web internos con un FQDN autodefinido, cada FQDN debe ser único en cualquier otro grupo de servidores front-end, director o grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="454ec-132">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

8.  <span data-ttu-id="454ec-133">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="454ec-133">Publish the topology.</span></span>

</div>

<div>

## <a name="to-define-the-director-multiple-director-pool"></a><span data-ttu-id="454ec-134">Para definir el Director (grupo de directores de múltiples)</span><span class="sxs-lookup"><span data-stu-id="454ec-134">To define the Director (multiple Director pool)</span></span>

1.  <span data-ttu-id="454ec-135">Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="454ec-135">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="454ec-136">En la página de bienvenida, haga clic en **Descargar topología de la implementación existente**.</span><span class="sxs-lookup"><span data-stu-id="454ec-136">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="454ec-137">En el cuadro de diálogo **Guardar topología como**, escriba el nombre y la ubicación de la copia local de la topología existente y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="454ec-137">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="454ec-138">Expanda el sitio donde desee agregar el director, haga clic con el botón secundario en **Grupos de servidores de director** y, a continuación, haga clic en **Nuevo grupo de servidores de director**.</span><span class="sxs-lookup"><span data-stu-id="454ec-138">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="454ec-139">En el cuadro de diálogo **Definir el FQDN del grupo director**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="454ec-139">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="454ec-140">En **FQDN de grupo de servidores**, escriba el FQDN del grupo de servidores de director.</span><span class="sxs-lookup"><span data-stu-id="454ec-140">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="454ec-141">Haga clic en **Grupo de servidores de varios equipos** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="454ec-141">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="454ec-142">En el cuadro de diálogo \*\*Definir los equipos de este grupo \*\*, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="454ec-142">In the **Define the computers in this pool** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="454ec-143">Especifique el FQDN de equipo del primer miembro del grupo de servidores y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="454ec-143">Specify the computer FQDN of the first pool member, and then click **Add**.</span></span>
    
      - <span data-ttu-id="454ec-p104">Repita el paso anterior para cada equipo que quiera agregar. Cuando haya acabado, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="454ec-p104">Repeat the previous step for each computer that you want to add. When you are finished, click **Next**.</span></span>

7.  <span data-ttu-id="454ec-146">En el cuadro de diálogo **Definir el recurso compartido de archivos**, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="454ec-146">In the **Define the file share** dialog box, do one of the following:</span></span>
    
      - <span data-ttu-id="454ec-147">Para usar un recurso compartido de archivos existente, haga clic en **Usar un recurso compartido de archivos definido previamente**, seleccione un recurso compartido de la lista y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="454ec-147">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
      - <span data-ttu-id="454ec-148">Para crear un nuevo recurso compartido de archivos, haga clic en **Definir un nuevo recurso compartido de archivos**, escriba el FQDN de la ubicación del recurso compartido de archivos en **FQDN de servidor de archivos**, escriba el nombre del recurso compartido en **Recurso compartido de archivos** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="454ec-148">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="454ec-149">El recurso compartido de archivos que especifique o que cree en este paso debe existir o debe haberse creado antes de publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="454ec-149">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="454ec-150">En realidad, el recurso compartido de archivos asignado a un director no se usa, de modo que puede asignar el recurso compartido de archivos de cualquier grupo de servidores de la organización.</span><span class="sxs-lookup"><span data-stu-id="454ec-150">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

8.  <span data-ttu-id="454ec-151">En el cuadro de diálogo **Especificar la URL de servicios web**, en **URL de base externa**, especifique el FQDN de los directores y haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="454ec-151">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="454ec-152">El nombre debe poder resolverse en servidores DNS de Internet y debe apuntar a la dirección IP pública del proxy inverso, que escucha las solicitudes HTTP/HTTPS enviadas a la dirección URL y lo envía mediante proxy al directorio virtual de servicios web externos del grupo de servidores de director.</span><span class="sxs-lookup"><span data-stu-id="454ec-152">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests sent to that URL and proxies them to the external Web Services virtual directory on that Director pool.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="454ec-153">Si tiene más de un grupo de servidores front-end o un servidor front-end, el FQDN de los servicios web externos debe ser único.</span><span class="sxs-lookup"><span data-stu-id="454ec-153">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="454ec-154">Por ejemplo, si define el FQDN de servicios web externos de un servidor front-end como <STRONG>pool01.contoso.com</STRONG>, no puede usar <STRONG>pool01.contoso.com</STRONG> para otro grupo de servidores front-end o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="454ec-154">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="454ec-155">Si también está implementando directores, el FQDN de servicios Web externo definido para cualquier Director o grupo de directores debe ser único de cualquier otro director o grupo de directores, así como cualquier grupo de servidores front-end o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="454ec-155">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="454ec-156">Si decide reemplazar los servicios Web internos con un FQDN autodefinido, cada FQDN debe ser único en cualquier otro grupo de servidores front-end, director o grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="454ec-156">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

9.  <span data-ttu-id="454ec-157">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="454ec-157">Publish the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

