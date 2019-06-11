---
title: 'Lync Server 2013: Definir topologías de Director opcionales en la topología'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define optional Director topologies in your topology
ms:assetid: 8e9a659d-23b0-401d-b296-59c7df414d49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398717(v=OCS.15)
ms:contentKeyID: 48184808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 524259226b44d68367b631c2b7cef5513e0770e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-optional-director-topologies-in-your-topology-for-lync-server-2013"></a><span data-ttu-id="664f3-102">Definir topologías de Director opcionales en la topología para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="664f3-102">Define optional Director topologies in your topology for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="664f3-103">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="664f3-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="664f3-104">Los directores de Lync Server 2013 pueden ser servidores de instancia única o se pueden instalar como un grupo de varios directores con equilibrio de carga para ofrecer mayor disponibilidad y capacidad.</span><span class="sxs-lookup"><span data-stu-id="664f3-104">Lync Server 2013 Directors can be single-instance servers or they can be installed as a load-balanced pool of multiple Directors for higher availability and capacity.</span></span> <span data-ttu-id="664f3-105">Se admiten el equilibrio de carga de hardware y el equilibrio de carga del sistema de nombres de dominio (DNS).</span><span class="sxs-lookup"><span data-stu-id="664f3-105">Both hardware load balancing and Domain Name System (DNS) load balancing are supported.</span></span> <span data-ttu-id="664f3-106">En este tema se explica cómo configurar el equilibrio de carga de DNS para los grupos de directores.</span><span class="sxs-lookup"><span data-stu-id="664f3-106">This topic explains how to configure DNS load balancing for Director pools.</span></span>

<span data-ttu-id="664f3-107">Para publicar, habilitar o deshabilitar correctamente una topología al agregar o quitar un rol de servidor, debe haber iniciado sesión como un usuario que sea miembro de los grupos **administradores de dominio** y **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="664f3-107">To successfully publish, enable, or disable a topology when you add or remove a server role, you should be logged on as a user who is a member of the **RTCUniversalServerAdmins** and **Domain Admins** groups.</span></span> <span data-ttu-id="664f3-108">También puede delegar los derechos y permisos adecuados para agregar roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="664f3-108">You can also delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="664f3-109">Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) en la documentación de implementación de servidor Standard Edition o Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="664f3-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="664f3-110">Para otros cambios de configuración, solo es necesario pertenecer al grupo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="664f3-110">For other configuration changes, only membership in the **RTCUniversalServerAdmins** group is required.</span></span>

<span data-ttu-id="664f3-111">En este tema se describen los pasos necesarios para definir y publicar la topología de las dos topologías de Director:</span><span class="sxs-lookup"><span data-stu-id="664f3-111">This topic describes the steps to define and publish the topology for the two Director topologies:</span></span>

  - <span data-ttu-id="664f3-112">Para definir el director (instancia única)</span><span class="sxs-lookup"><span data-stu-id="664f3-112">To define the Director (single instance)</span></span>

  - <span data-ttu-id="664f3-113">Para definir el director (grupo de varios directores)</span><span class="sxs-lookup"><span data-stu-id="664f3-113">To define the Director (multiple Director pool)</span></span>

<div>

## <a name="to-define-the-director-single-instance"></a><span data-ttu-id="664f3-114">Para definir el director (instancia única)</span><span class="sxs-lookup"><span data-stu-id="664f3-114">To define the Director (single instance)</span></span>

1.  <span data-ttu-id="664f3-115">Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="664f3-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="664f3-116">En la Página principal, haga clic en **Descargar topología de la implementación existente**.</span><span class="sxs-lookup"><span data-stu-id="664f3-116">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="664f3-117">En el cuadro de diálogo **Guardar topología como** , escriba el nombre y la ubicación de la copia local de la topología existente y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="664f3-117">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="664f3-118">Expanda el sitio en el que planea agregar el director, haga clic con el botón secundario en **grupos de directores**y, a continuación, haga clic en **nuevo grupo de directores**.</span><span class="sxs-lookup"><span data-stu-id="664f3-118">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="664f3-119">En el cuadro de diálogo **definir el FQDN del grupo de directores** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="664f3-119">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="664f3-120">En **FQDN del grupo**, escriba el FQDN del grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="664f3-120">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="664f3-121">Haga clic en **grupo de equipos únicos**y, a continuación, en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="664f3-121">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="664f3-122">En el cuadro de diálogo **definir el uso compartido de archivos** , realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="664f3-122">In the **Define the file share** dialog box, do one of the following:</span></span>
    
    1.  <span data-ttu-id="664f3-123">Para usar un recurso compartido de archivos existente, haga clic en usar un recurso compartido de archivos **definido previamente**, seleccione un recurso compartido de archivos de la lista y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="664f3-123">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
    2.  <span data-ttu-id="664f3-124">Para crear un nuevo recurso compartido de archivos, haga clic en **definir un nuevo recurso compartido de archivos**, escriba el FQDN de la ubicación del recurso compartido de archivos en **FQDN del servidor de archivos**, escriba el nombre del recurso compartido en el **recurso compartido de archivos**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="664f3-124">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="664f3-125">El recurso compartido de archivos que especifique o cree en este paso debe existir o crearse antes de publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="664f3-125">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="664f3-126">El recurso compartido de archivos asignado a un director no se utiliza realmente, por lo que puede asignar el recurso compartido de archivos de cualquier grupo de la organización.</span><span class="sxs-lookup"><span data-stu-id="664f3-126">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

7.  <span data-ttu-id="664f3-127">En el cuadro de diálogo **especificar dirección URL de servicios web** , en **dirección URL base externa**, especifique el FQDN de los directores y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="664f3-127">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="664f3-128">El nombre debe poder resolverse desde los servidores DNS de Internet y apuntar a la dirección IP pública del proxy inverso, que escucha las solicitudes HTTP/HTTPS a esa dirección URL y los envía al directorio virtual de servicios Web externo de ese director.</span><span class="sxs-lookup"><span data-stu-id="664f3-128">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests to that URL and proxies them to the external Web Services virtual directory on that Director.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="664f3-129">Si tiene más de un grupo de servidores front-end o un servidor front-end, el FQDN de los servicios web externos debe ser único.</span><span class="sxs-lookup"><span data-stu-id="664f3-129">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="664f3-130">Por ejemplo, si define el FQDN de los servicios web externos de un servidor front-end como <STRONG>pool01.contoso.com</STRONG>, no puede usar <STRONG>pool01.contoso.com</STRONG> para otro grupo de servidores front-end o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="664f3-130">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="664f3-131">Si también va a implementar directores, el FQDN de servicios Web externo definido para cualquier Director o grupo de directores debe ser único de cualquier otro grupo de directores o directores, así como de cualquier grupo de servidores front-end o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="664f3-131">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="664f3-132">Si decide invalidar los servicios Web internos con un FQDN definido por el usuario, cada FQDN debe ser único de cualquier otro grupo de servidores front-end, director o grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="664f3-132">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

8.  <span data-ttu-id="664f3-133">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="664f3-133">Publish the topology.</span></span>

</div>

<div>

## <a name="to-define-the-director-multiple-director-pool"></a><span data-ttu-id="664f3-134">Para definir el director (grupo de varios directores)</span><span class="sxs-lookup"><span data-stu-id="664f3-134">To define the Director (multiple Director pool)</span></span>

1.  <span data-ttu-id="664f3-135">Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="664f3-135">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="664f3-136">En la Página principal, haga clic en **Descargar topología de la implementación existente**.</span><span class="sxs-lookup"><span data-stu-id="664f3-136">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="664f3-137">En el cuadro de diálogo **Guardar topología como** , escriba el nombre y la ubicación de la copia local de la topología existente y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="664f3-137">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="664f3-138">Expanda el sitio en el que planea agregar el director, haga clic con el botón secundario en **grupos de directores**y, a continuación, haga clic en **nuevo grupo de directores**.</span><span class="sxs-lookup"><span data-stu-id="664f3-138">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="664f3-139">En el cuadro de diálogo **definir el FQDN del grupo de directores** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="664f3-139">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="664f3-140">En **FQDN del grupo**, escriba el FQDN del grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="664f3-140">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="664f3-141">Haga clic en **grupo de varios equipos**y, a continuación, en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="664f3-141">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="664f3-142">En el cuadro de diálogo **definir los equipos de este grupo** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="664f3-142">In the **Define the computers in this pool** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="664f3-143">Especifique el FQDN del equipo del primer miembro del grupo y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="664f3-143">Specify the computer FQDN of the first pool member, and then click **Add**.</span></span>
    
      - <span data-ttu-id="664f3-144">Repita el paso anterior para cada equipo que desee agregar.</span><span class="sxs-lookup"><span data-stu-id="664f3-144">Repeat the previous step for each computer that you want to add.</span></span> <span data-ttu-id="664f3-145">Cuando haya terminado, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="664f3-145">When you are finished, click **Next**.</span></span>

7.  <span data-ttu-id="664f3-146">En el cuadro de diálogo **definir el uso compartido de archivos** , realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="664f3-146">In the **Define the file share** dialog box, do one of the following:</span></span>
    
      - <span data-ttu-id="664f3-147">Para usar un recurso compartido de archivos existente, haga clic en usar un recurso compartido de archivos **definido previamente**, seleccione un recurso compartido de archivos de la lista y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="664f3-147">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
      - <span data-ttu-id="664f3-148">Para crear un nuevo recurso compartido de archivos, haga clic en **definir un nuevo recurso compartido de archivos**, escriba el FQDN de la ubicación del recurso compartido de archivos en **FQDN del servidor de archivos**, escriba el nombre del recurso compartido en el **recurso compartido de archivos**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="664f3-148">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="664f3-149">El recurso compartido de archivos que especifique o cree en este paso debe existir o crearse antes de publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="664f3-149">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="664f3-150">El recurso compartido de archivos asignado a un director no se utiliza realmente, por lo que puede asignar el recurso compartido de archivos de cualquier grupo de la organización.</span><span class="sxs-lookup"><span data-stu-id="664f3-150">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

8.  <span data-ttu-id="664f3-151">En el cuadro de diálogo **especificar dirección URL de servicios web** , en **dirección URL base externa**, especifique el FQDN de los directores y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="664f3-151">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="664f3-152">El nombre debe poder resolverse desde los servidores DNS de Internet y apuntar a la dirección IP pública del proxy inverso, que escucha las solicitudes HTTP/HTTPS enviadas a esa dirección URL y las envía al directorio virtual de servicios Web externo de ese grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="664f3-152">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests sent to that URL and proxies them to the external Web Services virtual directory on that Director pool.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="664f3-153">Si tiene más de un grupo de servidores front-end o un servidor front-end, el FQDN de los servicios web externos debe ser único.</span><span class="sxs-lookup"><span data-stu-id="664f3-153">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="664f3-154">Por ejemplo, si define el FQDN de los servicios web externos de un servidor front-end como <STRONG>pool01.contoso.com</STRONG>, no puede usar <STRONG>pool01.contoso.com</STRONG> para otro grupo de servidores front-end o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="664f3-154">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="664f3-155">Si también va a implementar directores, el FQDN de servicios Web externo definido para cualquier Director o grupo de directores debe ser único de cualquier otro grupo de directores o directores, así como de cualquier grupo de servidores front-end o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="664f3-155">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="664f3-156">Si decide invalidar los servicios Web internos con un FQDN definido por el usuario, cada FQDN debe ser único de cualquier otro grupo de servidores front-end, director o grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="664f3-156">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

9.  <span data-ttu-id="664f3-157">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="664f3-157">Publish the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

