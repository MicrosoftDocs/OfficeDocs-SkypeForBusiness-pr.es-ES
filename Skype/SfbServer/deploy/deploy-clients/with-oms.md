---
title: Implementar la administración de Sistemas de salas de Skype v2 con OMS
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: En este artículo se describe cómo implementar la administración de dispositivos de sistemas de salas de Skype v2 de manera integrada, end-to-end usando Microsoft Operations Management Suite.
ms.openlocfilehash: 0d0490d92a5513dad38a9ff6348a957204274878
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-management-with-oms"></a><span data-ttu-id="b4b0d-103">Implementar la administración de Sistemas de salas de Skype v2 con OMS</span><span class="sxs-lookup"><span data-stu-id="b4b0d-103">Deploy Skype Room Systems v2 management with OMS</span></span>
 
<span data-ttu-id="b4b0d-104">En este artículo se describe cómo implementar la administración de dispositivos de sistemas de salas de Skype v2 de manera integrada, end-to-end usando Microsoft Operations Management Suite.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-104">This article discusses how to deploy management of Skype Room Systems v2 devices in an integrated, end-to-end manner using Microsoft Operations Management Suite.</span></span> 
  
<span data-ttu-id="b4b0d-p101">Microsoft Operations Management Suite (OMS) se puede configurar para proporcionar telemetría básica que le ayude a administrar los dispositivos de salas de reuniones de Skype. A medida que se desarrolle la solución de administración, podrá comprar más funciones de administración y datos para crear una vista más detallada del rendimiento de los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-p101">You can configure Microsoft Operations Management Suite (OMS) to provide basic telemetry that will help you manage Skype meeting room devices. As your management solution matures, you can purchase additional data and management capabilities to create a more detailed view of device performance.</span></span>
  
<span data-ttu-id="b4b0d-107">A un mayor nivel, debe realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="b4b0d-107">At a high level, you need to perform the following tasks:</span></span>
  
1. [<span data-ttu-id="b4b0d-108">Configurar dispositivos para la administración de OMS </span><span class="sxs-lookup"><span data-stu-id="b4b0d-108">Configure devices for OMS Management </span></span>](with-oms.md#config_devices)
    
2. [<span data-ttu-id="b4b0d-109">Asignar campos personalizados</span><span class="sxs-lookup"><span data-stu-id="b4b0d-109">Map custom fields</span></span>](with-oms.md#Custom_fields)
    
3. [<span data-ttu-id="b4b0d-110">Definir las vistas de SRS v2 en OMS</span><span class="sxs-lookup"><span data-stu-id="b4b0d-110">Define the SRS v2 views in OMS</span></span>](with-oms.md#Views)
    
## <a name="find-and-record-device-locations-capabilities-and-configurations"></a><span data-ttu-id="b4b0d-111">Buscar y registrar las ubicaciones, las funcionalidades y las configuraciones de los dispositivos</span><span class="sxs-lookup"><span data-stu-id="b4b0d-111">Find and record device locations, capabilities, and configurations</span></span>
<span data-ttu-id="b4b0d-112"><a name="find_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="b4b0d-112"></span></span>

<span data-ttu-id="b4b0d-p102">El primer paso consiste en crear una base de datos con detalles de todo el equipo del sistema, sus funcionalidades y su configuración, además de su ubicación. En el caso de empresas medianas o pequeñas, basta con una hoja de cálculo, pero si trabaja en una organización más grande, es posible que tenga que usar herramientas de administración de activos y servicios de terceros. Lo importante es que registre la ubicación y todos los detalles relevantes de cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-p102">The first step is to create a detailed database of all of the equipment in the system, the details of its capabilities and configuration, and its location. A spreadsheet may be adequate for this task in small to medium organizations. If you work at a larger organization, you may need to consider asset management tools and third-party services. What is important is that you record the location and all the relevant details of every device.</span></span>
  
<span data-ttu-id="b4b0d-117">Cuando este trabajo esté hecho, podrá usar esta información para distribuir técnicos y administrar actualizaciones y revisiones de los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-117">Once that work is done, you can use this information to dispatch technicians and manage device patches and upgrades.</span></span>
  
## <a name="configure-devices-for-oms-management"></a><span data-ttu-id="b4b0d-118">Configurar dispositivos para la administración de OMS </span><span class="sxs-lookup"><span data-stu-id="b4b0d-118">Configure devices for OMS Management</span></span>
<span data-ttu-id="b4b0d-119"><a name="config_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="b4b0d-119"></span></span>

<span data-ttu-id="b4b0d-120">Para cada dispositivo SRS, siga las instrucciones que se encuentra en [equipos de Windows conectarse al servicio de análisis de registro en Azure](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents).</span><span class="sxs-lookup"><span data-stu-id="b4b0d-120">For each SRS device, follow the instructions found in [Connect Windows computers to the Log Analytics service in Azure](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents).</span></span>
  
## <a name="configure-oms-to-collect-device-event-logs"></a><span data-ttu-id="b4b0d-121">Configurar OMS para recopilar registros de eventos de dispositivos</span><span class="sxs-lookup"><span data-stu-id="b4b0d-121">Configure OMS to collect device event logs</span></span>
<span data-ttu-id="b4b0d-122"><a name="config_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="b4b0d-122"></span></span>

<span data-ttu-id="b4b0d-123">Debe configurar específicamente OMS para recopilar los registros de sucesos desde dispositivos SRS siguiendo los pasos en [orígenes de datos de registro de sucesos de Windows en análisis de registro](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events).</span><span class="sxs-lookup"><span data-stu-id="b4b0d-123">You will need to specifically configure OMS to collect event logs from SRS devices using the steps at [Windows event log data sources in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events).</span></span> <span data-ttu-id="b4b0d-124">El registro de sucesos SRS que seleccione es "Sistema de sala de Skype" y debería comprobar los cuadros de opción para todos los tipos: Error, advertencia e información.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-124">The SRS event log to select is "Skype Room System" and you should check the option boxes for all types: Error, Warning and Information.</span></span>
  
## <a name="map-custom-fields"></a><span data-ttu-id="b4b0d-125">Asignar campos personalizados</span><span class="sxs-lookup"><span data-stu-id="b4b0d-125">Map custom fields</span></span>
<span data-ttu-id="b4b0d-126"><a name="Custom_fields"> </a></span><span class="sxs-lookup"><span data-stu-id="b4b0d-126"></span></span>

<span data-ttu-id="b4b0d-127">Antes de que se pueden utilizar los mosaicos creados en las [vistas de definir el v2 SRS de OMS](with-oms.md#Views) , necesitará crear campos personalizados para la vista.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-127">Before the tiles created in the [Define the SRS v2 views in OMS](with-oms.md#Views) can be used, you'll need to create custom fields for your view.</span></span> <span data-ttu-id="b4b0d-128">ver [campos personalizados en el registro de análisis](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-custom-fields) para obtener información detallada sobre la creación de campos personalizados.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-128">see [Custom fields in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-custom-fields) for details on creating custom fields.</span></span>
  
<span data-ttu-id="b4b0d-129">Utilice las asignaciones que se muestra a continuación, OMS agregará automáticamente el _CF al definir el nuevo campo.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-129">Use the mappings shown below, OMS will automatically add the _CF when defining the new field.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b4b0d-130">Recuerde que en todos los campos JSON y OMS se distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-130">Remember that all JSON and OMS fields are case sensitive.</span></span> 
  
<span data-ttu-id="b4b0d-131">**Asignación de campos personalizados**</span><span class="sxs-lookup"><span data-stu-id="b4b0d-131">**Custom fields mapping**</span></span>

|<span data-ttu-id="b4b0d-132">**Campo JSON**</span><span class="sxs-lookup"><span data-stu-id="b4b0d-132">**JSON field**</span></span>|<span data-ttu-id="b4b0d-133">**Campo personalizado de OMS**</span><span class="sxs-lookup"><span data-stu-id="b4b0d-133">**OMS custom field**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b4b0d-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4b0d-134">Description</span></span>  <br/> |<span data-ttu-id="b4b0d-135">SRSEventDescription_CF</span><span class="sxs-lookup"><span data-stu-id="b4b0d-135">SRSEventDescription_CF</span></span>  <br/> |
|<span data-ttu-id="b4b0d-136">ResourceState</span><span class="sxs-lookup"><span data-stu-id="b4b0d-136">ResourceState</span></span>  <br/> |<span data-ttu-id="b4b0d-137">SRSResourceState_CF</span><span class="sxs-lookup"><span data-stu-id="b4b0d-137">SRSResourceState_CF</span></span>  <br/> |
|<span data-ttu-id="b4b0d-138">OperationName</span><span class="sxs-lookup"><span data-stu-id="b4b0d-138">OperationName</span></span>  <br/> |<span data-ttu-id="b4b0d-139">SRSOperationName_CF</span><span class="sxs-lookup"><span data-stu-id="b4b0d-139">SRSOperationName_CF</span></span>  <br/> |
|<span data-ttu-id="b4b0d-140">OperationResult</span><span class="sxs-lookup"><span data-stu-id="b4b0d-140">OperationResult</span></span>  <br/> |<span data-ttu-id="b4b0d-141">SRSOperationResult_CF</span><span class="sxs-lookup"><span data-stu-id="b4b0d-141">SRSOperationResult_CF</span></span>  <br/> |
|<span data-ttu-id="b4b0d-142">OS</span><span class="sxs-lookup"><span data-stu-id="b4b0d-142">OS</span></span>  <br/> |<span data-ttu-id="b4b0d-143">SRSOSVersion_CF</span><span class="sxs-lookup"><span data-stu-id="b4b0d-143">SRSOSVersion_CF</span></span>  <br/> |
|<span data-ttu-id="b4b0d-144">OSVersion</span><span class="sxs-lookup"><span data-stu-id="b4b0d-144">OSVersion</span></span>  <br/> |<span data-ttu-id="b4b0d-145">SRSOSLongVersion_CF</span><span class="sxs-lookup"><span data-stu-id="b4b0d-145">SRSOSLongVersion_CF</span></span>  <br/> |
|<span data-ttu-id="b4b0d-146">Alias</span><span class="sxs-lookup"><span data-stu-id="b4b0d-146">Alias</span></span>  <br/> |<span data-ttu-id="b4b0d-147">SRSAlias_CF</span><span class="sxs-lookup"><span data-stu-id="b4b0d-147">SRSAlias_CF</span></span>  <br/> |
|<span data-ttu-id="b4b0d-148">DisplayName</span><span class="sxs-lookup"><span data-stu-id="b4b0d-148">DisplayName</span></span>  <br/> |<span data-ttu-id="b4b0d-149">SRSDisplayName_CF</span><span class="sxs-lookup"><span data-stu-id="b4b0d-149">SRSDisplayName_CF</span></span>  <br/> |
|<span data-ttu-id="b4b0d-150">AppVersion</span><span class="sxs-lookup"><span data-stu-id="b4b0d-150">AppVersion</span></span>  <br/> |<span data-ttu-id="b4b0d-151">SRSAppVersion_CF</span><span class="sxs-lookup"><span data-stu-id="b4b0d-151">SRSAppVersion_CF</span></span>  <br/> |
|<span data-ttu-id="b4b0d-152">IPv4Address</span><span class="sxs-lookup"><span data-stu-id="b4b0d-152">IPv4Address</span></span>  <br/> |<span data-ttu-id="b4b0d-153">SRSIPv4Address_CF</span><span class="sxs-lookup"><span data-stu-id="b4b0d-153">SRSIPv4Address_CF</span></span>  <br/> |
|<span data-ttu-id="b4b0d-154">IPv6Address</span><span class="sxs-lookup"><span data-stu-id="b4b0d-154">IPv6Address</span></span>  <br/> |<span data-ttu-id="b4b0d-155">SRSIPv6Address_CF</span><span class="sxs-lookup"><span data-stu-id="b4b0d-155">SRSIPv6Address_CF</span></span>  <br/> |
   
## <a name="define-the-srs-v2-views-in-oms"></a><span data-ttu-id="b4b0d-156">Definir las vistas de SRS v2 en OMS</span><span class="sxs-lookup"><span data-stu-id="b4b0d-156">Define the SRS v2 views in OMS</span></span>
<span data-ttu-id="b4b0d-157"><a name="Views"> </a></span><span class="sxs-lookup"><span data-stu-id="b4b0d-157"></span></span>

<span data-ttu-id="b4b0d-158">Una vez que los datos se recopilan y se asignan los campos personalizados, puede utilizar OMS Ver diseñador para desarrollar una consola con mosaicos para supervisar los sucesos SRS v2.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-158">Once data is collected and custom fields are mapped, you can use OMS View Designer to develop a Dashboard containing Tiles to monitor SRS v2 events.</span></span> <span data-ttu-id="b4b0d-159">Utilizar el Diseñador de vistas para crear los siguientes mosaicos, consulte [Utilizar el Diseñador de vistas para crear vistas personalizadas de análisis de registro](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-view-designer) según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-159">Use View Designer to create the following tiles, refer to [Use View Designer to create custom views in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-view-designer) as necessary.</span></span>
  
### <a name="create-a-tile-that-shows-healthy-devices"></a><span data-ttu-id="b4b0d-160">Crear un icono que muestre los dispositivos en buen estado</span><span class="sxs-lookup"><span data-stu-id="b4b0d-160">Create a tile that shows healthy devices</span></span>

1. <span data-ttu-id="b4b0d-161">Defina el caso: </span><span class="sxs-lookup"><span data-stu-id="b4b0d-161">Define the case:</span></span> 
    
    <span data-ttu-id="b4b0d-162">Este icono muestra todos los dispositivos que han enviado un mensaje de latido en los últimos 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-162">This tile displays all devices that have sent a heartbeat message in the last 10 minutes.</span></span>
    
2. <span data-ttu-id="b4b0d-163">Asigne el título del grupo. </span><span class="sxs-lookup"><span data-stu-id="b4b0d-163">Assign Group Title</span></span> 
    
   ```
   SRS v2
   ```

3. <span data-ttu-id="b4b0d-164">Active la casilla de grupo nuevo</span><span class="sxs-lookup"><span data-stu-id="b4b0d-164">Check the new group box</span></span>
    
4. <span data-ttu-id="b4b0d-165">Agregue el texto de la leyenda del icono.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-165">Add the Tile legend text</span></span>
    
   ```
   All healthy devices (Heartbeat sent in last 10 minutes)
   ```

5. <span data-ttu-id="b4b0d-166">Introduzca la consulta del icono.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-166">Enter the tile query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" TimeGenerated >NOW-10MINUTES|measure count() by SRSDisplayName_CF 
   ```

6. <span data-ttu-id="b4b0d-167">Introduzca la consulta de lista.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-167">Enter the list query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by SRSDisplayName_CF |Where LastHB>NOW-10MINUTES
   ```

7. <span data-ttu-id="b4b0d-168">Defina el nombre de los títulos de columna.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-168">Define column titles name</span></span>
    
   ```
   Display Name
   ```

8. <span data-ttu-id="b4b0d-169">Definir el valor de los títulos de columna</span><span class="sxs-lookup"><span data-stu-id="b4b0d-169">Define Column titles value</span></span>
    
   ```
   Last HB
   ```

9. <span data-ttu-id="b4b0d-170">Introduzca la consulta de navegación.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-170">Enter Navigation query</span></span>
    
   ```
   {selected item} EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat"|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="create-the-tile-that-shows-devices-with-connectivity-issues"></a><span data-ttu-id="b4b0d-171">Crear el icono que muestra los dispositivos con problemas de conectividad</span><span class="sxs-lookup"><span data-stu-id="b4b0d-171">Create the tile that shows devices with connectivity issues</span></span>

1. <span data-ttu-id="b4b0d-172">Defina el caso: </span><span class="sxs-lookup"><span data-stu-id="b4b0d-172">Define the case:</span></span> 
    
    <span data-ttu-id="b4b0d-p106">Este icono muestra todos los dispositivos que no han enviado un mensaje de latido en los últimos 10 minutos. Estos dispositivos pueden estar experimentando problemas con la conectividad de red, la conectividad de Exchange o la conectividad de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-p106">This tile displays all devices that have not sent a heartbeat message in the last 10 minutes. These devices may be experiencing issues with network connectivity, Exchange connectivity, or Skype for Business connectivity.</span></span>
    
2. <span data-ttu-id="b4b0d-175">Asigne el título del grupo. </span><span class="sxs-lookup"><span data-stu-id="b4b0d-175">Assign Group Title</span></span> 
    
   ```
   SRS v2
   ```

3. <span data-ttu-id="b4b0d-176">No active el cuadro del grupo nuevo.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-176">Do not check the new group box.</span></span> <span data-ttu-id="b4b0d-177">Ya lo hizo cuando creó el icono 1 y no es necesario hacerlo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-177">You already did this when creating tile 1, and don't need to do it again.</span></span>
    
4. <span data-ttu-id="b4b0d-178">Agregue el texto de la leyenda del icono.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-178">Add the Tile legend text</span></span>
    
   ```
   Devices no longer sending Heartbeat messages
   ```

5. <span data-ttu-id="b4b0d-179">Introduzca la consulta del icono.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-179">Enter the tile query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by Computer|Where LastHB<NOW-10MINUTES
   ```

6. <span data-ttu-id="b4b0d-180">Introduzca la consulta de lista.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-180">Enter the list query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by Computer|Where LastHB<NOW-10MINUTES
   ```

7. <span data-ttu-id="b4b0d-181">Defina el nombre de los títulos de columna.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-181">Define column titles name</span></span>
    
   ```
   Device Name
   ```

8. <span data-ttu-id="b4b0d-182">Defina el valor de los títulos de columna. </span><span class="sxs-lookup"><span data-stu-id="b4b0d-182">Define Column titles Value</span></span> 
    
   ```
   Last HB
   ```

9. <span data-ttu-id="b4b0d-183">Introduzca la consulta de navegación.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-183">Enter Navigation query</span></span>
    
   ```
   {selected item} EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-with-a-hardware-error"></a><span data-ttu-id="b4b0d-184">Enumerar dispositivos con un error de hardware </span><span class="sxs-lookup"><span data-stu-id="b4b0d-184">List devices with a hardware error</span></span>

1. <span data-ttu-id="b4b0d-185">Defina el caso: </span><span class="sxs-lookup"><span data-stu-id="b4b0d-185">Define the case:</span></span> 
    
   <span data-ttu-id="b4b0d-186">Esta ficha muestra todos los dispositivos que envían un mensaje que indica un uno o más problemas de componentes de hardware en los últimos 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-186">This tile displays all devices that sent a message indicating a one or more hardware component issues in the last 10 minutes.</span></span> 
    
2. <span data-ttu-id="b4b0d-187">Asigne el título del grupo. </span><span class="sxs-lookup"><span data-stu-id="b4b0d-187">Assign Group Title</span></span> 
    
   ```
   SRS v2
   ```

3. <span data-ttu-id="b4b0d-188">No active el cuadro del grupo nuevo.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-188">Do not check the new group box.</span></span> <span data-ttu-id="b4b0d-189">Ya lo hizo cuando creó el icono 1 y no es necesario hacerlo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-189">You already did this when creating tile 1, and don't need to do it again.</span></span>
    
4. <span data-ttu-id="b4b0d-190">Leyenda del mosaico: </span><span class="sxs-lookup"><span data-stu-id="b4b0d-190">Tile legend:</span></span> 
    
   ```
   Devices with a Hardware Error
   ```

5. <span data-ttu-id="b4b0d-191">Consulta de icono</span><span class="sxs-lookup"><span data-stu-id="b4b0d-191">Tile Query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:3001 TimeGenerated>NOW-10MINUTES|measure count() by SRSDisplayName_CF
   ```

6. <span data-ttu-id="b4b0d-192">Consulta de lista:</span><span class="sxs-lookup"><span data-stu-id="b4b0d-192">List query:</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:3001 TimeGenerated>NOW-10MINUTES|measure max(TimeGenerated) by SRSDisplayName_CF
   ```

7. <span data-ttu-id="b4b0d-193">Nombre de los títulos de columna: </span><span class="sxs-lookup"><span data-stu-id="b4b0d-193">Column titles Name:</span></span> 
    
   ```
   Display Name
   ```

8. <span data-ttu-id="b4b0d-194">Valor de títulos de columna: </span><span class="sxs-lookup"><span data-stu-id="b4b0d-194">Column titles Value:</span></span> 
    
   ```
   Last Error
   ```

9. <span data-ttu-id="b4b0d-195">Consulta de navegación: </span><span class="sxs-lookup"><span data-stu-id="b4b0d-195">Navigation query:</span></span> 
    
   ```
   {selected item}  EventLevelName:Error EventID:3001|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-with-an-app-error"></a><span data-ttu-id="b4b0d-196">Enumerar dispositivos con un error de aplicación  </span><span class="sxs-lookup"><span data-stu-id="b4b0d-196">List devices with an App error</span></span>

1. <span data-ttu-id="b4b0d-197">Defina el caso:</span><span class="sxs-lookup"><span data-stu-id="b4b0d-197">Define the case:</span></span> 
    
   <span data-ttu-id="b4b0d-198">Este icono muestra todos los dispositivos de SRS que notifican uno o varios errores en los componentes de las aplicaciones en los últimos 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-198">This tile displays all SRS devices that report 1 or more app component errors within the last 10 minutes</span></span>
    
2. <span data-ttu-id="b4b0d-199">Asigne el título del grupo. </span><span class="sxs-lookup"><span data-stu-id="b4b0d-199">Assign Group Title</span></span> 
    
   ```
   SRS v2
   ```

3. <span data-ttu-id="b4b0d-200">No active el cuadro del grupo nuevo.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-200">Do not check the new group box.</span></span> <span data-ttu-id="b4b0d-201">Ya lo hizo cuando creó el icono 1 y no es necesario hacerlo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-201">You already did this when creating tile 1, and don't need to do it again.</span></span>
    
4. <span data-ttu-id="b4b0d-202">Leyenda del mosaico: </span><span class="sxs-lookup"><span data-stu-id="b4b0d-202">Tile legend:</span></span> 
   ``` 
    Device with App Errors (in prior 10 minutes)
   ``` 
5. <span data-ttu-id="b4b0d-203">Consulta de icono: </span><span class="sxs-lookup"><span data-stu-id="b4b0d-203">Tile Query:</span></span> 
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:2001 TimeGenerated>NOW-10MINUTES|measure count() by Computer
   ```

6. <span data-ttu-id="b4b0d-204">Consulta de lista: </span><span class="sxs-lookup"><span data-stu-id="b4b0d-204">List query:</span></span> 
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:2001 TimeGenerated>NOW-10MINUTES|measure max(TimeGenerated) by Computer
   ```

7. <span data-ttu-id="b4b0d-205">Nombre de los títulos de columna: </span><span class="sxs-lookup"><span data-stu-id="b4b0d-205">Column titles Name:</span></span> 
    
   ```
   Device Name
   ```

8. <span data-ttu-id="b4b0d-206">Valor de títulos de columna: </span><span class="sxs-lookup"><span data-stu-id="b4b0d-206">Column titles Value:</span></span> 
    
   ```
   Last Error
   ```

9. <span data-ttu-id="b4b0d-207">Consulta de navegación:</span><span class="sxs-lookup"><span data-stu-id="b4b0d-207">Navigation query:</span></span>
    
   ```
   {selected item} EventLevelName:Error|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-requiring-a-restart"></a><span data-ttu-id="b4b0d-208">Enumerar los dispositivos que se deben reiniciar</span><span class="sxs-lookup"><span data-stu-id="b4b0d-208">List devices requiring a restart</span></span>

1. <span data-ttu-id="b4b0d-209">Defina el caso:</span><span class="sxs-lookup"><span data-stu-id="b4b0d-209">Define the case:</span></span> 
    
   <span data-ttu-id="b4b0d-210">Este icono muestra todos los dispositivos de SRS que se han reiniciado en las últimas 24 horas y el número de reinicios.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-210">This tile displays all SRS devices that have been restarted in the past 24 hours and number of restarts</span></span>
    
2. <span data-ttu-id="b4b0d-211">Asigne el título del grupo. </span><span class="sxs-lookup"><span data-stu-id="b4b0d-211">Assign Group Title</span></span> 
    
  ```
  SRS v2
  ```

3. <span data-ttu-id="b4b0d-212">No active el cuadro del grupo nuevo.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-212">Do not check the new group box.</span></span> <span data-ttu-id="b4b0d-213">Ya lo hizo cuando creó el icono 1 y no es necesario hacerlo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-213">You already did this when creating tile 1, and don't need to do it again.</span></span>
    
4. <span data-ttu-id="b4b0d-214">Leyenda del mosaico: </span><span class="sxs-lookup"><span data-stu-id="b4b0d-214">Tile legend:</span></span> 
    
   ```
   Devices with App restarted (past 24 hours)
   ```

5. <span data-ttu-id="b4b0d-215">Consulta de icono: </span><span class="sxs-lookup"><span data-stu-id="b4b0d-215">Tile Query:</span></span> 
    
   ```
   Type:Event EventLog:"Skype Room System" EventID:4000 TimeGenerated>NOW-24HOURS|measure count() by Computer
   ```

6. <span data-ttu-id="b4b0d-216">Consulta de lista: </span><span class="sxs-lookup"><span data-stu-id="b4b0d-216">List query:</span></span> 
    
   ```
   Type:Event EventLog:"Skype Room System" EventID:4000 TimeGenerated>NOW-24HOURS|measure count(EventID) by SRSDisplayName_CF
   ```

7. <span data-ttu-id="b4b0d-217">Nombre de los títulos de columna: </span><span class="sxs-lookup"><span data-stu-id="b4b0d-217">Column titles Name:</span></span> 
    
   ```
   Display Name
   ```

8. <span data-ttu-id="b4b0d-218">Valor de títulos de columna: </span><span class="sxs-lookup"><span data-stu-id="b4b0d-218">Column titles Value:</span></span> 
    
   ```
   Number of restarts
   ```

9. <span data-ttu-id="b4b0d-219">Consulta de navegación: </span><span class="sxs-lookup"><span data-stu-id="b4b0d-219">Navigation query:</span></span> 
    
   ```
   {selected item} EventID:4000 TimeGenerated >NOW-24HOURS|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

<span data-ttu-id="b4b0d-p111">Con esto finaliza la creación de vistas. Todas las alertas que están disponibles en este momento están reflejadas en uno o en varios de estos iconos.</span><span class="sxs-lookup"><span data-stu-id="b4b0d-p111">That completes view creation. The alerts currently available are all reflected in one or more of these tiles.</span></span>
## <a name="see-also"></a><span data-ttu-id="b4b0d-222">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4b0d-222">See also</span></span>
<span data-ttu-id="b4b0d-223"><a name="Views"> </a></span><span class="sxs-lookup"><span data-stu-id="b4b0d-223"></span></span>

#### 

[<span data-ttu-id="b4b0d-224">Planear la administración de sistemas de salas de Skype v2 con OMS</span><span class="sxs-lookup"><span data-stu-id="b4b0d-224">Plan Skype Room Systems v2 management with OMS</span></span>](../../plan-your-deployment/clients-and-devices/oms-management.md)
  
[<span data-ttu-id="b4b0d-225">Administrar dispositivos de sistemas de salas de Skype v2 con OMS</span><span class="sxs-lookup"><span data-stu-id="b4b0d-225">Manage Skype Room Systems v2 devices with OMS</span></span>](../../manage/skype-room-systems-v2/oms.md)

