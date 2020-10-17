---
title: 'Lync Server 2013: asociar una subred a un sitio de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate a subnet with a network site
ms:assetid: aa69e3ac-542a-4ba1-9582-2e6bee29f633
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412804(v=OCS.15)
ms:contentKeyID: 48185043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f961fef4fb9323c0eef642e4b7e70ede5da4ccf2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532747"
---
# <a name="associate-a-subnet-with-a-network-site-in-lync-server-2013"></a><span data-ttu-id="e7e55-102">Asociar una subred a un sitio de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7e55-102">Associate a subnet with a network site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7e55-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="e7e55-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="e7e55-104">Cada subred de la red debe estar asociada a un sitio de red específico, ya que la información de la subred se usa para determinar el sitio de red en el que se encuentra un extremo mientras se inicia una nueva sesión.</span><span class="sxs-lookup"><span data-stu-id="e7e55-104">Every subnet in your network must be associated with a specific network site, because subnet information is used to determine the network site on which an endpoint is located while a new session is initiated.</span></span> <span data-ttu-id="e7e55-105">Cuando se conoce la ubicación de cada parte en una sesión, las características avanzadas de telefonía IP empresarial pueden aplicarla para determinar cómo controlar la configuración o el enrutamiento de las llamadas.</span><span class="sxs-lookup"><span data-stu-id="e7e55-105">When the location of each party in a session is known, advanced Enterprise Voice features can apply that information to determine how to handle the call setup or routing.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e7e55-106">Todas las direcciones IP públicas de los servidores perimetrales de audio y vídeo en la implementación deben incluirse en los parámetros de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="e7e55-106">All configured public IP addresses of the Audio/Video Edge Servers in your deployment must be added to your network configuration settings.</span></span> <span data-ttu-id="e7e55-107">Estas direcciones IP se agregan como subredes con una máscara de 32.</span><span class="sxs-lookup"><span data-stu-id="e7e55-107">These IP addresses are added as subnets with a mask of 32.</span></span> <span data-ttu-id="e7e55-108">El sitio de red asociado debe corresponder con el sitio de red configurado adecuado.</span><span class="sxs-lookup"><span data-stu-id="e7e55-108">The associated network site should correspond to the appropriate configured network site.</span></span> <span data-ttu-id="e7e55-109">Por ejemplo, la dirección IP pública que corresponde a los servidores perimetrales A/V en el sitio central Chicago sería NetworkSiteID Chicago.</span><span class="sxs-lookup"><span data-stu-id="e7e55-109">For example, the public IP address that corresponds to the A/V Edge Server in central site Chicago would be NetworkSiteID Chicago.</span></span> <span data-ttu-id="e7e55-110">Para obtener más información acerca de las direcciones IP públicas, consulte <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">determinar el firewall externo a/V y los requisitos de puerto para Lync Server 2013</A> en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="e7e55-110">For details about public IP addresses, see <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determine external A/V firewall and port requirements for Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="e7e55-p103">Aparecerá una alerta de indicador de estado clave (KHI), que especifica una lista de direcciones IP que están incluidas en la red pero que no están asociadas a una subred, o bien la subred que incluye las direcciones IP no está asociada a un sitio de red. Esta alerta no aparecerá más que una vez en un período de ocho horas. A continuación se ofrece la información de alerta relevante y un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e7e55-p103">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site. This alert will not be raised more than once within an 8-hour period. The relevant alert information and an example are as follows:</span></span><BR><span data-ttu-id="e7e55-114"><STRONG>Origen:</STRONG> Servicio de directivas de ancho de banda (principal) de CS</span><span class="sxs-lookup"><span data-stu-id="e7e55-114"><STRONG>Source:</STRONG> CS Bandwidth Policy Service (Core)</span></span><BR><span data-ttu-id="e7e55-115"><STRONG>Número de evento:</STRONG> 36034</span><span class="sxs-lookup"><span data-stu-id="e7e55-115"><STRONG>Event number:</STRONG> 36034</span></span><BR><span data-ttu-id="e7e55-116"><STRONG>Nivel:</STRONG> 2</span><span class="sxs-lookup"><span data-stu-id="e7e55-116"><STRONG>Level:</STRONG> 2</span></span><BR><span data-ttu-id="e7e55-117"><STRONG>Descripción:</STRONG> Las subredes de las siguientes direcciones IP: &lt; la lista de direcciones IP &gt; no está configurada o las subredes no están asociadas a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="e7e55-117"><STRONG>Description:</STRONG> The subnets for the following IP addresses: &lt;List of IP Addresses&gt; are either not configured or the subnets are not associated to a Network Site.</span></span><BR><span data-ttu-id="e7e55-118"><STRONG>Causa:</STRONG> Las subredes de las direcciones IP correspondientes faltan en las opciones de configuración de red o las subredes no están asociadas a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="e7e55-118"><STRONG>Cause:</STRONG> The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="e7e55-119"><STRONG>Solución:</STRONG> Agregue subredes correspondientes a la lista de direcciones IP a las opciones de configuración de red y asocie cada subred a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="e7e55-119"><STRONG>Resolution:</STRONG> Add subnets corresponding to the list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span><BR><span data-ttu-id="e7e55-p104">Por ejemplo, si la lista de direcciones IP de la alerta especifica 10.121.248.226 y 10.121.249.20, estas direcciones IP no están asociadas a una subred o la subred a la que están asociadas no pertenece a un sitio de red. Si 10.121.248.0/24 y 10.121.249.0/24 son las subredes correspondientes a estas direcciones, este problema se puede resolver de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="e7e55-p104">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet or the subnet they are associated with does not belong to a network site. If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="e7e55-122">Asegúrese de que la dirección IP 10.121.248.226 está asociada a la subred 10.121.248.0/24 y la dirección IP 10.121.249.20 está asociada a la subred 10.121.249.0/24.</span><span class="sxs-lookup"><span data-stu-id="e7e55-122">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span></P>
> <LI>
> <P><span data-ttu-id="e7e55-123">Asegúrese de que cada una de las subredes 10.121.248.0/24 y 10.121.249.0/24 está asociada a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="e7e55-123">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span></P></LI></OL>



</div>

<span data-ttu-id="e7e55-124">Para obtener información detallada sobre cómo trabajar con subredes de red, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="e7e55-124">For details about working with network subnets, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="e7e55-125">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="e7e55-125">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)

  - [<span data-ttu-id="e7e55-126">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="e7e55-126">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)

  - [<span data-ttu-id="e7e55-127">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="e7e55-127">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)

  - [<span data-ttu-id="e7e55-128">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="e7e55-128">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)

<div>


> [!TIP]  
> <span data-ttu-id="e7e55-p105">Si trabaja con un gran número de subredes, es aconsejable usar un archivo CSV (valores separados por comas) para asociar las subredes a los sitios. El archivo CSV debe tener las cuatro columnas siguientes: <STRONG>IPAddress</STRONG>, <STRONG>mask</STRONG>, <STRONG>description</STRONG>, <STRONG>NetworkSiteID</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="e7e55-p105">If you are working with a large number of subnets, we recommend using a comma-separated values (CSV) file to associate the subnets to sites. The CSV file must have the following four columns: <STRONG>IPAddress</STRONG>, <STRONG>mask</STRONG>, <STRONG>description</STRONG>, <STRONG>NetworkSiteID</STRONG>.</span></span>



</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-management-shell"></a><span data-ttu-id="e7e55-131">Para asociar una subred a un sitio de red mediante el Shell de administración</span><span class="sxs-lookup"><span data-stu-id="e7e55-131">To associate a subnet with a network site by using Management Shell</span></span>

1.  <span data-ttu-id="e7e55-132">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e7e55-132">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e7e55-133">Ejecute el cmdlet **New-CsNetworkSubnet** para asociar una subred a un sitio de red:</span><span class="sxs-lookup"><span data-stu-id="e7e55-133">Run the **New-CsNetworkSubnet** cmdlet to associate a subnet with a network site:</span></span>
    
        New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
    
    <span data-ttu-id="e7e55-134">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e7e55-134">For example:</span></span>
    
        New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
    
    <span data-ttu-id="e7e55-135">En este ejemplo, ha creado una asociación entre la subred 172.11.12.13 y el sitio de red “Chicago”.</span><span class="sxs-lookup"><span data-stu-id="e7e55-135">In this example, you created an association between the subnet 172.11.12.13 and the network site “Chicago”.</span></span>

3.  <span data-ttu-id="e7e55-136">Repita el paso 2 para todas las subredes de la topología.</span><span class="sxs-lookup"><span data-stu-id="e7e55-136">Repeat step 2 for all subnets in your topology.</span></span>

</div>

<div>

## <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a><span data-ttu-id="e7e55-137">Para asociar subredes a sitios de red mediante la importación de un archivo CSV</span><span class="sxs-lookup"><span data-stu-id="e7e55-137">To associate subnets with network sites by importing a CSV file</span></span>

1.  <span data-ttu-id="e7e55-p106">Cree un archivo CSV que incluya todas las subredes que quiera agregar. Por ejemplo, cree un archivo denominado **subnet.csv** con el contenido siguiente:</span><span class="sxs-lookup"><span data-stu-id="e7e55-p106">Create a CSV file that includes all of the subnets you want to add. For example, create a file named **subnet.csv** with the following content:</span></span>
    
    `IPAddress, mask, description, NetworkSiteID`
    
    `172.11.12.0, 24, "NA:Subnet in Portland", Portland`
    
    `172.11.13.0, 24, "NA:Subnet in Reno", Reno`
    
    `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`
    
    `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2.  <span data-ttu-id="e7e55-140">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e7e55-140">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e7e55-141">Ejecute el siguiente cmdlet para importar **subnet.csv**y, a continuación, almacene su contenido en el almacén de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="e7e55-141">Run the following cmdlet to import **subnet.csv**, and then store its contents in the Lync Server management store:</span></span>
    
        import-csv subnet.csv | foreach {New-CSNCSSubnet  _.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}

</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="e7e55-142">Para asociar una subred a un sitio de red mediante el Panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e7e55-142">To associate a subnet with a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e7e55-143">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e7e55-143">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e7e55-144">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e7e55-144">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="e7e55-145">En la barra de navegación izquierda, haga clic en **Configuración de red**.</span><span class="sxs-lookup"><span data-stu-id="e7e55-145">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="e7e55-146">Haga clic en el botón de navegación **Subred**.</span><span class="sxs-lookup"><span data-stu-id="e7e55-146">Click the **Subnet** navigation button.</span></span>

4.  <span data-ttu-id="e7e55-147">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="e7e55-147">Click **New**.</span></span>

5.  <span data-ttu-id="e7e55-148">En la página **Nueva subred**, haga clic en **Id. de subred** y escriba la primera dirección en el intervalo de direcciones IP definido mediante la subred que quiere asociar al sitio de red.</span><span class="sxs-lookup"><span data-stu-id="e7e55-148">On the **New Subnet** page, click **Subnet ID**, and then type the first address in the IP address range defined by the subnet you want to associate with a network site.</span></span>

6.  <span data-ttu-id="e7e55-149">Haga clic en **Máscara** y escriba la máscara de bits que quiere aplicar a la subred.</span><span class="sxs-lookup"><span data-stu-id="e7e55-149">Click **Mask**, and then type the bitmask to apply to the subnet.</span></span>

7.  <span data-ttu-id="e7e55-150">Haga clic en **Id. de sitio de red** y seleccione el identificador de sitio del sitio al que agrega esta subred.</span><span class="sxs-lookup"><span data-stu-id="e7e55-150">Click **Network site ID**, and then select the site ID of the site to which you are adding this subnet.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e7e55-151">Si todavía no ha creado sitios de red, esta lista estará vacía.</span><span class="sxs-lookup"><span data-stu-id="e7e55-151">If you have not yet created network sites, this list will be empty.</span></span> <span data-ttu-id="e7e55-152">Para obtener más información sobre el procedimiento, consulte <A href="lync-server-2013-create-or-modify-a-network-site.md">crear o modificar un sitio de red en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e7e55-152">For details about the procedure, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span> <span data-ttu-id="e7e55-153">También puede recuperar identificadores de sitio para su implementación mediante la ejecución del cmdlet <STRONG>Get-CsNetworkSite</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="e7e55-153">You can also retrieve site IDs for your deployment by running the <STRONG>Get-CsNetworkSite</STRONG> cmdlet.</span></span> <span data-ttu-id="e7e55-154">Para obtener más información, vea la documentación referente a Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e7e55-154">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="e7e55-155">Si lo desea, haga clic en **Descripción** y escriba información adicional para describir esta subred.</span><span class="sxs-lookup"><span data-stu-id="e7e55-155">Optionally, click **Description**, and then type additional information to describe this subnet.</span></span>

9.  <span data-ttu-id="e7e55-156">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e7e55-156">Click **Commit**.</span></span>

<span data-ttu-id="e7e55-157">Repita estos pasos para agregar otras subredes a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="e7e55-157">Repeat these steps to add other subnets to a network site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

