---
title: Configuración de la base de datos de ubicación en Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: Configurar, rellenar y publicar la base de datos de ubicación de E9-1-1 en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: ab97fae05a74f95e618cebacac9be5ac011eb921
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873881"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a><span data-ttu-id="9109c-103">Configuración de la base de datos de ubicación en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="9109c-103">Configure the location database in Skype for Business Server</span></span>
 
<span data-ttu-id="9109c-104">Configurar, rellenar y publicar la base de datos de ubicación de E9-1-1 en Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="9109c-104">Configure, populate, and publish the E9-1-1 location database in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="9109c-105">Para habilitar clientes de modo que detecten automáticamente su ubicación dentro de una red, primero tiene que configurar la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="9109c-105">To enable clients to automatically detect their location within a network, you first need to configure the location database.</span></span> 
  
<span data-ttu-id="9109c-106">Para configurar la base de datos de ubicaciones, deberá realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="9109c-106">To configure the location database, perform the following tasks:</span></span>
  
- <span data-ttu-id="9109c-107">Llene la base de datos con una búsqueda de elementos de red a las ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="9109c-107">Populate the database with a mapping of network elements to locations.</span></span> <span data-ttu-id="9109c-108">Si utiliza una puerta de enlace de número de identificación de ubicación de emergencia (ELIN), debe incluir los ELIN en la \<CompanyName\> campo.</span><span class="sxs-lookup"><span data-stu-id="9109c-108">If you use an Emergency Location Identification Number (ELIN) gateway, you need to include the ELIN in the \<CompanyName\> field.</span></span>
    
    <span data-ttu-id="9109c-109">Si no rellena la base de datos de ubicaciones y el valor de **Ubicación obligatoria** de la directiva de ubicación se define en **Sí** o **Declinación de responsabilidades**, el cliente indicará al usuario que especifique una ubicación manualmente.</span><span class="sxs-lookup"><span data-stu-id="9109c-109">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>
    
- <span data-ttu-id="9109c-110">Valide las direcciones comparándolas con la Guía de calles maestra (MSAG) mantenida por el proveedor de servicios E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="9109c-110">Validate the addresses against the master street address guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span>
    
- <span data-ttu-id="9109c-111">Publique la base de datos actualizada.</span><span class="sxs-lookup"><span data-stu-id="9109c-111">Publish the updated database.</span></span>
    
## <a name="populate-the-location-database"></a><span data-ttu-id="9109c-112">Rellenar la base de datos de ubicación</span><span class="sxs-lookup"><span data-stu-id="9109c-112">Populate the location database</span></span>

<span data-ttu-id="9109c-113">Para buscar clientes en una red de manera automática, primero es preciso rellenar la base de datos de ubicaciones con un diagrama de cableado de red, que asigna elementos de red a direcciones postales.</span><span class="sxs-lookup"><span data-stu-id="9109c-113">To automatically locate clients within a network, you first need to populate the location database with a network wiremap, which maps network elements to civic (that is, street) addresses.</span></span> <span data-ttu-id="9109c-114">Para definir el diagrama de cableado, puede usar subredes, puntos de acceso inalámbrico, conmutadores y puertos.</span><span class="sxs-lookup"><span data-stu-id="9109c-114">You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>
  
<span data-ttu-id="9109c-115">Puede agregar direcciones a la base de datos de ubicaciones una a una, pero también puede incorporar varias de ellas a la vez mediante un archivo .csv con los formatos de columna que se describen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="9109c-115">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>
  
<span data-ttu-id="9109c-p103">Si utiliza una puerta de enlace de Número de identificación de ubicación de emergencia (ELIN), incluya el ELIN en el campo **CompanyName** de cada ubicación. Puede incluir varios ELIN para cada ubicación, separándolos por un punto y coma.</span><span class="sxs-lookup"><span data-stu-id="9109c-p103">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location. You can include multiple ELINs for each location, each separated by a semicolon.</span></span>
  
|<span data-ttu-id="9109c-118">**Elemento de red**</span><span class="sxs-lookup"><span data-stu-id="9109c-118">**Network Element**</span></span>|<span data-ttu-id="9109c-119">**Columnas obligatorias**</span><span class="sxs-lookup"><span data-stu-id="9109c-119">**Required Columns**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9109c-120">**Punto de acceso inalámbrico**</span><span class="sxs-lookup"><span data-stu-id="9109c-120">**Wireless access point**</span></span> <br/> |<span data-ttu-id="9109c-121">\<BSSID\>,\<descripción\>,\<ubicación\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...</span><span class="sxs-lookup"><span data-stu-id="9109c-121">\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="9109c-122">... \<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<Ciudad\>,\<estado\>,\<PostalCode\>,\<país\></span><span class="sxs-lookup"><span data-stu-id="9109c-122">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="9109c-123">**Subred**</span><span class="sxs-lookup"><span data-stu-id="9109c-123">**Subnet**</span></span> <br/> |<span data-ttu-id="9109c-124">\<Subred\>,\<descripción\>,\<ubicación\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...</span><span class="sxs-lookup"><span data-stu-id="9109c-124">\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="9109c-125">... \<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<Ciudad\>,\<estado\>,\<PostalCode\>,\<país\></span><span class="sxs-lookup"><span data-stu-id="9109c-125">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="9109c-126">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="9109c-126">**Port**</span></span> <br/> |<span data-ttu-id="9109c-127">\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<descripción\>,\<ubicación\>,\<CompanyName\>,\<HouseNumber\>,\< HouseNumberSuffix\>,...</span><span class="sxs-lookup"><span data-stu-id="9109c-127">\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,…</span></span>  <br/> <span data-ttu-id="9109c-128">... \<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<Ciudad\>,\<estado\>,\<PostalCode\>,\< País\></span><span class="sxs-lookup"><span data-stu-id="9109c-128">…\<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="9109c-129">**Conmutador**</span><span class="sxs-lookup"><span data-stu-id="9109c-129">**Switch**</span></span> <br/> |<span data-ttu-id="9109c-130">\<ChassisID\>,\<descripción\>,\<ubicación\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...</span><span class="sxs-lookup"><span data-stu-id="9109c-130">\<ChassisID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="9109c-131">... \<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<Ciudad\>,\<estado\>,\<PostalCode\>,\<país\></span><span class="sxs-lookup"><span data-stu-id="9109c-131">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="9109c-132">Para agregar elementos de red a la base de datos de ubicaciones</span><span class="sxs-lookup"><span data-stu-id="9109c-132">To add network elements to the location database</span></span>

1. <span data-ttu-id="9109c-133">Ejecute el cmdlet siguiente para agregar una ubicación de subred a la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="9109c-133">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    <span data-ttu-id="9109c-p104">Para las puertas de enlace ELIN, escriba el ELIN en el campo CompanyName. Puede incluir más de un ELIN. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9109c-p104">For ELIN gateways, put the ELIN in the CompanyName field. You can include more than one ELIN. For example:</span></span>
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    <span data-ttu-id="9109c-137">También es posible ejecutar los cmdlets siguientes para actualizar en una sola acción las ubicaciones de subred mediante un archivo denominado "subnets.csv".</span><span class="sxs-lookup"><span data-stu-id="9109c-137">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
   ```
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. <span data-ttu-id="9109c-138">Ejecute el cmdlet siguiente para agregar ubicaciones inalámbricas a la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="9109c-138">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
   ```
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   <span data-ttu-id="9109c-139">También es posible ejecutar los cmdlets siguientes para actualizar en una sola acción las ubicaciones inalámbricas mediante un archivo denominado "waps.csv".</span><span class="sxs-lookup"><span data-stu-id="9109c-139">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
   ```
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. <span data-ttu-id="9109c-140">Ejecute el cmdlet siguiente para agregar ubicaciones de conmutador a la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="9109c-140">Run the following cmdlet to add switch locations to the location database.</span></span>
    
   ```
   Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   <span data-ttu-id="9109c-141">También es posible ejecutar los cmdlets siguientes para actualizar en una sola acción las ubicaciones de conmutadores mediante un archivo denominado "switches.csv".</span><span class="sxs-lookup"><span data-stu-id="9109c-141">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
   ```
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. <span data-ttu-id="9109c-142">Ejecute el cmdlet siguiente para agregar ubicaciones de puertos a la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="9109c-142">Run the following cmdlet to add port locations to the location database</span></span>
    
   ```
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   <span data-ttu-id="9109c-p105">El valor predeterminado de PortIDSubType es LocallyAssigned. También se puede usar InterfaceAlias e InterfaceName</span><span class="sxs-lookup"><span data-stu-id="9109c-p105">The default for PortIDSubType is LocallyAssigned. You can also set it to InterfaceAlias or InterfaceName</span></span>
    
   <span data-ttu-id="9109c-145">También es posible ejecutar los cmdlets siguientes para actualizar en una sola acción las ubicaciones de puertos mediante un archivo denominado "ports.csv".</span><span class="sxs-lookup"><span data-stu-id="9109c-145">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
   ```
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a><span data-ttu-id="9109c-146">Validar direcciones</span><span class="sxs-lookup"><span data-stu-id="9109c-146">Validate addresses</span></span>

### <a name="to-validate-addresses-located-in-the-location-database"></a><span data-ttu-id="9109c-147">Para validar direcciones ubicadas en la base de datos de ubicaciones</span><span class="sxs-lookup"><span data-stu-id="9109c-147">To validate addresses located in the location database</span></span>

1.  <span data-ttu-id="9109c-148">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="9109c-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="9109c-149">Ejecute los cmdlets siguientes para configurar la conexión de proveedor de servicios de emergencia.</span><span class="sxs-lookup"><span data-stu-id="9109c-149">Run the following cmdlets to configure the emergency service provider connection.</span></span>
    
   ```
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd
   ```

3. <span data-ttu-id="9109c-150">Ejecute el cmdlet siguiente para validar las direcciones en la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="9109c-150">Run the following cmdlet to validate the addresses in the location database.</span></span>
    
   ```
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   <span data-ttu-id="9109c-151">También puede usar el cmdlet **Test-CsLisCivicAddress** para validar direcciones individuales.</span><span class="sxs-lookup"><span data-stu-id="9109c-151">You can also use the **Test-CsLisCivicAddress** cmdlet to validate individual addresses.</span></span>
    
## <a name="publish-the-location-database"></a><span data-ttu-id="9109c-152">Publicar la base de datos de ubicación</span><span class="sxs-lookup"><span data-stu-id="9109c-152">Publish the location database</span></span>

<span data-ttu-id="9109c-153">Las nuevas ubicaciones agregadas a la base de datos de ubicaciones no estarán disponibles para el cliente hasta que no se publiquen.</span><span class="sxs-lookup"><span data-stu-id="9109c-153">The new locations that you added to the location database will not be made available to the client until they have been published.</span></span>
  
<span data-ttu-id="9109c-154">Si usa puertas de enlace de número de identificación de ubicación de emergencia (ELIN), cargue también los ELIN en la base de datos de identificación de ubicación automática (ALI) del proveedor de la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="9109c-154">If you use Emergency Location Identification Number (ELIN) gateways, you also need to upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span> <span data-ttu-id="9109c-155">Probablemente el proveedor de RTC le solicite que use un formato específico para los registros de ELIN.</span><span class="sxs-lookup"><span data-stu-id="9109c-155">Your PSTN carrier may require you to use a specific format for the ELIN records.</span></span> <span data-ttu-id="9109c-156">Póngase en contacto con el proveedor de RTC para obtener más información al respecto.</span><span class="sxs-lookup"><span data-stu-id="9109c-156">Contact your PSTN carrier for details.</span></span> <span data-ttu-id="9109c-157">Puede exportar los registros de la base de datos de servicio de información de ubicación y aplicarles formato según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="9109c-157">You can export the records from the Location Information service database and format them as required.</span></span>
  
### <a name="to-publish-the-location-database"></a><span data-ttu-id="9109c-158">Para publicar la base de datos de ubicaciones</span><span class="sxs-lookup"><span data-stu-id="9109c-158">To publish the location database</span></span>

-  <span data-ttu-id="9109c-159">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="9109c-159">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
- <span data-ttu-id="9109c-160">Ejecute el cmdlet siguiente para publicar la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="9109c-160">Run the following cmdlet to publish the location database.</span></span>
    
  ```
  Publish-CsLisConfiguration
  ```


