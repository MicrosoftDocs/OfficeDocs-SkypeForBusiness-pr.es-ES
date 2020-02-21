---
title: 'Lync Server 2013: rellenar la base de datos de ubicaciones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Populate the location database
ms:assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413069(v=OCS.15)
ms:contentKeyID: 48185939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0216cada44f2512e33a0b33b627ed9a6d6582cda
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="populate-the-location-database-in-lync-server-2013"></a><span data-ttu-id="723e7-102">Rellenar la base de datos de ubicaciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="723e7-102">Populate the location database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="723e7-103">_**Última modificación del tema:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="723e7-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="723e7-p101">Para buscar clientes en una red de manera automática, primero es preciso rellenar la base de datos de ubicaciones con un *diagrama de cableado* de red, del cual asigna elementos de red a direcciones postales. Para definir el diagrama de cableado puede usar subredes, puntos de acceso inalámbrico, conmutadores y puertos.</span><span class="sxs-lookup"><span data-stu-id="723e7-p101">To automatically locate clients within a network, you first need to populate the location database with a network *wiremap*, which maps network elements to civic (that is, street) addresses. You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>

<span data-ttu-id="723e7-106">Puede agregar direcciones a la base de datos de ubicaciones una a una, pero también puede incorporar varias de ellas a la vez mediante un archivo en formato .csv con los formatos de columna que se describen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="723e7-106">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>

<span data-ttu-id="723e7-p102">Si utiliza una puerta de enlace de Número de identificación de ubicación de emergencia (ELIN), incluya el ELIN en el campo **CompanyName** de cada ubicación. Puede incluir varios ELIN para cada ubicación, separándolos por un punto y coma.</span><span class="sxs-lookup"><span data-stu-id="723e7-p102">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location. You can include multiple ELINs for each location, each separated by a semicolon.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="723e7-109">Elemento de red</span><span class="sxs-lookup"><span data-stu-id="723e7-109">Network Element</span></span></th>
<th><span data-ttu-id="723e7-110">Columnas obligatorias</span><span class="sxs-lookup"><span data-stu-id="723e7-110">Required Columns</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="723e7-111"><strong>Punto de acceso inalámbrico</strong></span><span class="sxs-lookup"><span data-stu-id="723e7-111"><strong>Wireless access point</strong></span></span></p></td>
<td><p><span data-ttu-id="723e7-112">&lt;BSSID&gt;,&lt;&gt;Description&lt;,&gt;Location&lt;,&gt;CompanyName&lt;,&gt;HouseNumber&lt;,&gt;HouseNumberSuffix&lt;, predirectional&gt;,...</span><span class="sxs-lookup"><span data-stu-id="723e7-112">&lt;BSSID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="723e7-113">... &lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;postdirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span><span class="sxs-lookup"><span data-stu-id="723e7-113">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="723e7-114"><strong>Subred</strong></span><span class="sxs-lookup"><span data-stu-id="723e7-114"><strong>Subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="723e7-115">&lt;Subnet&gt;,&lt;&gt;Description&lt;,&gt;Location&lt;,&gt;CompanyName&lt;,&gt;HouseNumber&lt;,&gt;HouseNumberSuffix&lt;, predirectional&gt;,...</span><span class="sxs-lookup"><span data-stu-id="723e7-115">&lt;Subnet&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="723e7-116">... &lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;postdirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span><span class="sxs-lookup"><span data-stu-id="723e7-116">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="723e7-117"><strong>Port</strong></span><span class="sxs-lookup"><span data-stu-id="723e7-117"><strong>Port</strong></span></span></p></td>
<td><p><span data-ttu-id="723e7-118">&lt;ChassisID&gt;,&lt;PortIDSubType&gt;,&lt;PortID&gt;,&lt;&gt;Description&lt;,&gt;Location&lt;,&gt;CompanyName&lt;,&gt;HouseNumber&lt;,&gt;HouseNumberSuffix,...</span><span class="sxs-lookup"><span data-stu-id="723e7-118">&lt;ChassisID&gt;,&lt;PortIDSubType&gt;,&lt;PortID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,…</span></span></p>
<p><span data-ttu-id="723e7-119">... &lt;Predirectional&gt;,&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;postdirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span><span class="sxs-lookup"><span data-stu-id="723e7-119">…&lt;PreDirectional&gt;,&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="723e7-120"><strong>Switch</strong></span><span class="sxs-lookup"><span data-stu-id="723e7-120"><strong>Switch</strong></span></span></p></td>
<td><p><span data-ttu-id="723e7-121">&lt;ChassisID&gt;,&lt;&gt;Description&lt;,&gt;Location&lt;,&gt;CompanyName&lt;,&gt;HouseNumber&lt;,&gt;HouseNumberSuffix&lt;, predirectional&gt;,...</span><span class="sxs-lookup"><span data-stu-id="723e7-121">&lt;ChassisID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="723e7-122">... &lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;postdirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span><span class="sxs-lookup"><span data-stu-id="723e7-122">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="723e7-123">Si no rellena la base de datos de ubicaciones y el valor de **Ubicación obligatoria** de la directiva de ubicación se define en **Sí** o **Declinación de responsabilidades**, el cliente indicará al usuario que especifique una ubicación manualmente.</span><span class="sxs-lookup"><span data-stu-id="723e7-123">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>

<span data-ttu-id="723e7-124">Para obtener información detallada sobre cómo rellenar la base de datos de ubicaciones, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="723e7-124">For details about populating the location database, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="723e7-125">**Get-CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="723e7-125">**Get-CsLisSubnet**</span></span>

  - <span data-ttu-id="723e7-126">**Set-CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="723e7-126">**Set-CsLisSubnet**</span></span>

  - <span data-ttu-id="723e7-127">Remove-CsLisSubnet</span><span class="sxs-lookup"><span data-stu-id="723e7-127">Remove-CsLisSubnet</span></span>

  - <span data-ttu-id="723e7-128">**Get-CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="723e7-128">**Get-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="723e7-129">**Set-CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="723e7-129">**Set-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="723e7-130">**Remove-CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="723e7-130">**Remove-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="723e7-131">**Get-CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="723e7-131">**Get-CsLisSwitch**</span></span>

  - <span data-ttu-id="723e7-132">**Set-CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="723e7-132">**Set-CsLisSwitch**</span></span>

  - <span data-ttu-id="723e7-133">**Remove-CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="723e7-133">**Remove-CsLisSwitch**</span></span>

  - <span data-ttu-id="723e7-134">**Get-CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="723e7-134">**Get-CsLisPort**</span></span>

  - <span data-ttu-id="723e7-135">**Set-CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="723e7-135">**Set-CsLisPort**</span></span>

  - <span data-ttu-id="723e7-136">**Remove-CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="723e7-136">**Remove-CsLisPort**</span></span>

<div>

## <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="723e7-137">Para agregar elementos de red a la base de datos de ubicaciones</span><span class="sxs-lookup"><span data-stu-id="723e7-137">To add network elements to the location database</span></span>

1.  <span data-ttu-id="723e7-138">Ejecute el cmdlet siguiente para agregar una ubicación de subred a la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="723e7-138">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="723e7-p103">Para las puertas de enlace ELIN, escriba el ELIN en el campo CompanyName. Puede incluir más de un ELIN. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="723e7-p103">For ELIN gateways, put the ELIN in the CompanyName field. You can include more than one ELIN. For example:</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="723e7-142">También es posible ejecutar los cmdlets siguientes para actualizar en una sola acción las ubicaciones de subred mediante un archivo denominado "subnets.csv".</span><span class="sxs-lookup"><span data-stu-id="723e7-142">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  <span data-ttu-id="723e7-143">Ejecute el cmdlet siguiente para agregar ubicaciones inalámbricas a la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="723e7-143">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="723e7-144">También es posible ejecutar los cmdlets siguientes para actualizar en una sola acción las ubicaciones inalámbricas mediante un archivo denominado "waps.csv".</span><span class="sxs-lookup"><span data-stu-id="723e7-144">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  <span data-ttu-id="723e7-145">Ejecute el cmdlet siguiente para agregar ubicaciones de conmutador a la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="723e7-145">Run the following cmdlet to add switch locations to the location database.</span></span>
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="723e7-146">También es posible ejecutar los cmdlets siguientes para actualizar en una sola acción las ubicaciones de conmutadores mediante un archivo denominado "switches.csv".</span><span class="sxs-lookup"><span data-stu-id="723e7-146">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  <span data-ttu-id="723e7-147">Ejecute el cmdlet siguiente para agregar ubicaciones de puertos a la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="723e7-147">Run the following cmdlet to add port locations to the location database</span></span>
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="723e7-p104">El valor predeterminado de PortIDSubType es LocallyAssigned. También se puede usar InterfaceAlias e InterfaceName</span><span class="sxs-lookup"><span data-stu-id="723e7-p104">The default for PortIDSubType is LocallyAssigned. You can also set it to InterfaceAlias or InterfaceName</span></span>
    
    <span data-ttu-id="723e7-150">También es posible ejecutar los cmdlets siguientes para actualizar en una sola acción las ubicaciones de puertos mediante un archivo denominado "ports.csv".</span><span class="sxs-lookup"><span data-stu-id="723e7-150">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

</div>

</div>

<span> </span>

</div>

</div>

</div>

