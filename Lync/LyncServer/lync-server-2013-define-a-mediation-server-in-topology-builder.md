---
title: 'Lync Server 2013: definir un servidor de mediación en el generador de topologías'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a Mediation Server in Topology Builder
ms:assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398391(v=OCS.15)
ms:contentKeyID: 48184217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f284b793c79ff3dcf8589a60469ed8525426de1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043702"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-mediation-server-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="a270f-102">Definir un servidor de mediación en el generador de topologías de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a270f-102">Define a Mediation Server in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a270f-103">_**Última modificación del tema:** 2013-03-25_</span><span class="sxs-lookup"><span data-stu-id="a270f-103">_**Topic Last Modified:** 2013-03-25_</span></span>

<span data-ttu-id="a270f-104">Siga los pasos de este tema para usar el generador de topologías para definir un servidor de mediación independiente o un grupo combinado con un grupo de servidores front-end en un sitio en el que no implementó anteriormente la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="a270f-104">Follow the steps in this topic to use Topology Builder to define a stand-alone Mediation Server or a pool collocated with a Front End pool at a site for which you did not previously deploy Enterprise Voice.</span></span>

<span data-ttu-id="a270f-105">Puede definir una topología mediante una cuenta que sea miembro del grupo de administradores.</span><span class="sxs-lookup"><span data-stu-id="a270f-105">You can define a topology using an account that is a member of the Administrators group.</span></span>

<div>

## <a name="define-mediation-server-collocated-to-a-front-end-pool"></a><span data-ttu-id="a270f-106">Definir un servidor de mediación combinado con un grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="a270f-106">Define Mediation Server collocated to a Front End pool</span></span>

<span data-ttu-id="a270f-107">Siga los pasos descritos en este tema para usar el generador de topologías para definir un servidor de mediación combinado con un grupo de servidores front-end en un sitio en el que no se ha implementado la telefonía IP empresarial anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a270f-107">Follow the steps in this topic to use Topology Builder to define a Mediation Server collocated to a Front End pool in a site where Enterprise Voice has not been previously deployed.</span></span>

<div>

## <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="a270f-108">Para agregar un servidor de mediación a un grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="a270f-108">To Add a Mediation Server to a Front End pool</span></span>

1.  <span data-ttu-id="a270f-109">Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a270f-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="a270f-110">En el generador de topologías, en el árbol de la consola, expanda el nombre del sitio para el que desea definir un grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="a270f-110">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>

3.  <span data-ttu-id="a270f-111">En el árbol de la consola, haga clic con el botón secundario en el tipo de grupo de servidores front-end que desee y, a continuación, haga clic en **nuevo grupo de servidores front-end..**.</span><span class="sxs-lookup"><span data-stu-id="a270f-111">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>

4.  <span data-ttu-id="a270f-112">Desplácese por el asistente **definir nuevo grupo de servidores front-end** hasta llegar a la página **Seleccionar roles de servidor combinados** .</span><span class="sxs-lookup"><span data-stu-id="a270f-112">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>

5.  <span data-ttu-id="a270f-113">En **Seleccionar roles de servidor combinados**, Compruebe la opción **combinar servidor de mediación**.</span><span class="sxs-lookup"><span data-stu-id="a270f-113">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="a270f-114">Si el tipo de grupo de servidores front-end que seleccionó es Enterprise Edition, el componente de servidor de mediación se instalará en todos los servidores front-end de ese grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="a270f-114">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="a270f-115">El grupo de servidores del <STRONG>próximo salto</STRONG> usado por el servidor de mediación será el grupo de servidores front-end en el que se encuentra el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="a270f-115">The <STRONG>Next hop pool</STRONG> used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="a270f-116">El <STRONG>grupo de servidores perimetrales</STRONG> usado por el servidor de mediación será el mismo grupo de servidores perimetrales asociado con el grupo de servidores front-end en el que se encuentra el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="a270f-116">The <STRONG>Edge pool</STRONG> used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span></P></LI></UL>

    
    </div>

6.  <span data-ttu-id="a270f-117">Haga clic en **establecer como predeterminado** para usar este grupo de servidores front-end para enrutar las llamadas de Microsoft Office Communications Server 2007 R2 a la RTC.</span><span class="sxs-lookup"><span data-stu-id="a270f-117">Click **Make Default** to use this Front End pool to route calls from Microsoft Office Communications Server 2007 R2 to the PSTN.</span></span>

7.  <span data-ttu-id="a270f-118">Haga clic en **Finalizar** cuando haya terminado de asociar uno o más elementos del mismo nivel con el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="a270f-118">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a270f-119">Antes de continuar con el paso siguiente del proceso de implementación de Enterprise Voice, asegúrese de que el grupo de servidores de mediación (es decir, el grupo de servidores front-end con el componente de servidor de mediación combinado) esté usando los FQDN que especificó.</span><span class="sxs-lookup"><span data-stu-id="a270f-119">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span>

    
    </div>

8.  <span data-ttu-id="a270f-120">A continuación, siga los procedimientos que se describen en [publicar la topología en Lync Server 2013](lync-server-2013-publish-the-topology.md) en la documentación de la guía de implementación para agregar el servidor de mediación a la topología antes de continuar con el siguiente paso de la modificación de los puertos de escucha del servidor de mediación, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="a270f-120">Next, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment Guide documentation to add the Mediation Server to your topology before proceeding to the next step of modifying the listening ports of the Mediation Server if needed.</span></span> <span data-ttu-id="a270f-121">Debe publicar la topología cada vez que use el generador de topologías para definir o modificar la topología.</span><span class="sxs-lookup"><span data-stu-id="a270f-121">You must publish your topology each time you use Topology Builder to define or modify your topology.</span></span>

</div>

</div>

<div>

## <a name="define-stand-alone-mediation-server"></a><span data-ttu-id="a270f-122">Definir servidor de mediación independiente</span><span class="sxs-lookup"><span data-stu-id="a270f-122">Define stand-alone Mediation Server</span></span>

<span data-ttu-id="a270f-123">Siga los pasos de este tema para usar el generador de topologías para definir un servidor o un grupo de servidores de mediación independiente en un sitio en el que no se haya implementado anteriormente la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="a270f-123">Follow the steps in this topic to use Topology Builder to define a stand-alone Mediation Server or pool at a site where Enterprise Voice has not been previously deployed.</span></span>

<span data-ttu-id="a270f-124">Si ya ha implementado servidores de mediación combinados en grupos de servidores front-end en este sitio, puede omitir esta sección e [instalar los archivos del servidor de mediación en Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md) antes de continuar con la [configuración de troncos en Lync Server 2013](lync-server-2013-configuring-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="a270f-124">If you already deployed Mediation Servers collocated to Front End pools at this site, you can skip this section and [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) before proceeding to [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a270f-125">En esta sección se presupone que ya ha configurado al menos un grupo de servidores front-end, como se describe en <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync server 2013</A> y <A href="lync-server-2013-publish-the-topology.md">publicar la topología en Lync Server 2013</A> , en la documentación de la guía de implementación.</span><span class="sxs-lookup"><span data-stu-id="a270f-125">This section assumes that you have already setup at least one Front End pool, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment Guide documentation.</span></span>



</div>

<div>

## <a name="to-add-a-mediation-server"></a><span data-ttu-id="a270f-126">Para agregar un servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="a270f-126">To Add a Mediation Server</span></span>

1.  <span data-ttu-id="a270f-127">Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a270f-127">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="a270f-128">En el generador de topologías, en el árbol de la consola, expanda el nombre del sitio para el que desea definir un servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="a270f-128">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>

3.  <span data-ttu-id="a270f-129">En el árbol de la consola, haga clic con el botón secundario en el nodo grupos de servidores de **mediación** y haga clic en **grupo de servidores de mediación**.</span><span class="sxs-lookup"><span data-stu-id="a270f-129">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>

4.  <span data-ttu-id="a270f-130">En **definir nuevo grupo de mediación**, escriba el nombre de dominio completo (FQDN) del grupo de servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="a270f-130">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>

5.  <span data-ttu-id="a270f-131">A continuación, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="a270f-131">Next, do one of the following:</span></span>
    
      - <span data-ttu-id="a270f-132">Si quiere implementar varios servidores de mediación en el grupo para proporcionar alta disponibilidad, seleccione **grupo de varios equipos**.</span><span class="sxs-lookup"><span data-stu-id="a270f-132">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a270f-133">Debe implementar el equilibrio de carga de DNS para admitir grupos de servidores de mediación que tengan varios servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="a270f-133">You must deploy DNS load balancing to support Mediation Server pools that have multiple Mediation Servers.</span></span> <span data-ttu-id="a270f-134">Para obtener más información, consulte la sección usar el equilibrio de carga de DNS en grupos de servidores de mediación de <A href="lync-server-2013-dns-load-balancing.md">equilibrio de carga de DNS en Lync Server 2013</A> en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="a270f-134">For details, see the Using DNS Load Balancing on Mediation Server Pools section of <A href="lync-server-2013-dns-load-balancing.md">DNS load balancing in Lync Server 2013</A> in the Planning documentation.</span></span>

        
        </div>
    
      - <span data-ttu-id="a270f-135">Si desea implementar un solo servidor de mediación en el grupo de servidores porque no necesita alta disponibilidad, seleccione **grupo de un solo equipo**.</span><span class="sxs-lookup"><span data-stu-id="a270f-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="a270f-136">Omita el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="a270f-136">Skip the following step.</span></span>

6.  <span data-ttu-id="a270f-137">Si seleccionó **Grupo** de servidores de varios equipos en el paso anterior, en el elemento **definir los equipos de este grupo** , haga clic en **FQDN de equipo**, escriba el FQDN de cada servidor del grupo y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a270f-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="a270f-138">Repita este paso para todos los servidores de mediación que desee agregar al grupo.</span><span class="sxs-lookup"><span data-stu-id="a270f-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="a270f-139">Cuando haya definido todos los equipos del grupo, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a270f-139">When you have defined all the computers in the pool, click **Next**.</span></span>

7.  <span data-ttu-id="a270f-140">En la página **seleccionar el próximo salto** , haga clic en grupo de servidores de **próximo salto**, haga clic en el FQDN del grupo de servidores front-end que usará este grupo de servidores de mediación y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a270f-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>

8.  <span data-ttu-id="a270f-141">En la página **seleccionar un servidor perimetral** , realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="a270f-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
      - <span data-ttu-id="a270f-142">Si desea proporcionar conectividad con RTC a los usuarios externos habilitados para telefonía IP empresarial, en **Seleccionar grupo de servidores perimetrales usado por este servidor de mediación**, haga clic en el FQDN del grupo de servidores perimetrales que usará este grupo de servidores de mediación para proporcionar conectividad con RTC a dichos usuarios externos y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a270f-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
      - <span data-ttu-id="a270f-143">Si no va a habilitar a los usuarios externos para telefonía IP empresarial o si no desea proporcionar conectividad con RTC a los usuarios cuando están fuera de la red interna, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a270f-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>

9.  <span data-ttu-id="a270f-144">A continuación, siga los procedimientos que se describen en publicación de la [topología en Lync Server 2013](lync-server-2013-publish-the-topology.md) en la documentación sobre implementación para agregar el servidor de mediación a la topología.</span><span class="sxs-lookup"><span data-stu-id="a270f-144">Next, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation to add the Mediation Server to the topology.</span></span> <span data-ttu-id="a270f-145">Debe publicar la topología cada vez que use el generador de topologías para crear o modificar la topología, de modo que los datos puedan usarse para instalar los archivos de los servidores que ejecutan Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a270f-145">You must publish your topology each time you use Topology Builder to build or modify your topology so that the data can be used to install the files for servers that are running Lync Server.</span></span> <span data-ttu-id="a270f-146">A continuación, continúe con los pasos siguientes para modificar los puertos de escucha en el servidor de mediación, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="a270f-146">Then continue to the next steps to modify the listening ports on the Mediation Server, if necessary.</span></span>

</div>

</div>

<div>

## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="a270f-147">Definir los puertos de escucha del servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="a270f-147">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="a270f-148">Siga los pasos que se indican en este tema para usar el generador de topologías para definir los puertos de escucha que un servidor de mediación o un grupo de servidores aceptará conexiones entrantes de una puerta de enlace del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="a270f-148">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>

<div>

## <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="a270f-149">Para modificar los puertos de escucha del servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="a270f-149">To Modify the Mediation Server Listening Ports</span></span>

1.  <span data-ttu-id="a270f-150">Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a270f-150">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="a270f-151">En el generador de topologías, en el árbol de la consola, expanda el nodo grupos de servidores de **mediación** y haga clic con el botón secundario en el servidor de mediación creado previamente.</span><span class="sxs-lookup"><span data-stu-id="a270f-151">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>

3.  <span data-ttu-id="a270f-152">De forma predeterminada, los puertos de escucha SIP en el servidor de mediación son 5070 para el tráfico TLS de Lync Server, 5067 para el tráfico TLS de pares (gateways, PBXes o SBC).</span><span class="sxs-lookup"><span data-stu-id="a270f-152">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Lync Server, 5067 for TLS traffic from peers (gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="a270f-153">El puerto TCP está deshabilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a270f-153">TCP port is disabled by default.</span></span> <span data-ttu-id="a270f-154">Debe habilitar el puerto TCP si tiene puertas de enlace que no admiten TLS.</span><span class="sxs-lookup"><span data-stu-id="a270f-154">You must enable TCP port if you have gateways that do not support TLS.</span></span>

4.  <span data-ttu-id="a270f-155">Especifique el intervalo de puertos de escucha TLS o TCP que desea que el servidor de mediación acepte conexiones entrantes de las puertas de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="a270f-155">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a270f-156">No es necesario escribir un intervalo de puertos TCP si no se ha seleccionado <STRONG>Habilitar el puerto TCP</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="a270f-156">Entering a TCP port range is not required if <STRONG>Enable TCP port</STRONG> is not checked.</span></span> <span data-ttu-id="a270f-157">Este valor es opcional.</span><span class="sxs-lookup"><span data-stu-id="a270f-157">This setting is optional.</span></span>

    
    </div>

<span data-ttu-id="a270f-158">A continuación, [defina una puerta de enlace en el generador de topologías de Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md) e instale los archivos en cada servidor de mediación del grupo siguiendo los procedimientos descritos en [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="a270f-158">Next, [Define a gateway in Topology Builder in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md) and install the files on each Mediation Server in the pool by following the procedures in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md).</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

