---
title: Configurar la base de datos de ubicaciones en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: Configurar, rellenar y publicar la base de datos de ubicación de E9-1-1 en Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: 4c39ae7f3a73331c00a65a2fe364cb25d0010150
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-location-database-in-skype-for-business-server-2015"></a><span data-ttu-id="af316-103">Configurar la base de datos de ubicaciones en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="af316-103">Configure the location database in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="af316-104">Configurar, rellenar y publicar la base de datos de ubicación de E9-1-1 en Skype para Telefonía IP empresarial de Business Server.</span><span class="sxs-lookup"><span data-stu-id="af316-104">Configure, populate, and publish the E9-1-1 location database in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="af316-105">Para habilitar clientes de modo que detecten automáticamente su ubicación dentro de una red, primero tiene que configurar la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="af316-105">To enable clients to automatically detect their location within a network, you first need to configure the location database.</span></span> 
  
<span data-ttu-id="af316-106">Para configurar la base de datos de ubicación, realice las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="af316-106">To configure the location database, perform the following tasks:</span></span>
  
- <span data-ttu-id="af316-107">Llene la base de datos con una búsqueda de elementos de red a las ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="af316-107">Populate the database with a mapping of network elements to locations.</span></span> <span data-ttu-id="af316-108">Si se utiliza una puerta de enlace de número de identificación de ubicación de emergencia (ELIN), debe incluir el ELIN en la \<CompanyName\> campo.</span><span class="sxs-lookup"><span data-stu-id="af316-108">If you use an Emergency Location Identification Number (ELIN) gateway, you need to include the ELIN in the \<CompanyName\> field.</span></span>
    
    <span data-ttu-id="af316-109">Si no rellena la base de datos de ubicaciones y el valor de **Ubicación obligatoria** de la directiva de ubicación se define en **Sí** o **Declinación de responsabilidades**, el cliente indicará al usuario que especifique una ubicación manualmente.</span><span class="sxs-lookup"><span data-stu-id="af316-109">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>
    
- <span data-ttu-id="af316-110">Validar las direcciones contra la Guía maestra Calle (MSAG) que es mantenida por el proveedor de servicio de E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="af316-110">Validate the addresses against the master street address guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span>
    
- <span data-ttu-id="af316-111">Publique la base de datos actualizada.</span><span class="sxs-lookup"><span data-stu-id="af316-111">Publish the updated database.</span></span>
    
## <a name="populate-the-location-database"></a><span data-ttu-id="af316-112">Rellenar la base de datos de ubicación</span><span class="sxs-lookup"><span data-stu-id="af316-112">Populate the location database</span></span>

<span data-ttu-id="af316-113">Para buscar automáticamente los clientes dentro de una red, primero debe rellenar la base de datos de ubicación con un diagrama de cableado de red, que asigna a los elementos de red cívica (es decir, calle) direcciones.</span><span class="sxs-lookup"><span data-stu-id="af316-113">To automatically locate clients within a network, you first need to populate the location database with a network wiremap, which maps network elements to civic (that is, street) addresses.</span></span> <span data-ttu-id="af316-114">Para definir el diagrama de cableado, puede usar subredes, puntos de acceso inalámbrico, conmutadores y puertos.</span><span class="sxs-lookup"><span data-stu-id="af316-114">You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>
  
<span data-ttu-id="af316-115">Puede agregar direcciones a la base de datos de ubicaciones una a una, pero también puede incorporar varias de ellas a la vez mediante un archivo .csv con los formatos de columna que se describen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="af316-115">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>
  
<span data-ttu-id="af316-p103">Si utiliza una puerta de enlace de Número de identificación de ubicación de emergencia (ELIN), incluya el ELIN en el campo **CompanyName** de cada ubicación. Puede incluir varios ELIN para cada ubicación, separándolos por un punto y coma.</span><span class="sxs-lookup"><span data-stu-id="af316-p103">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location. You can include multiple ELINs for each location, each separated by a semicolon.</span></span>
  
|<span data-ttu-id="af316-118">**Elemento de red**</span><span class="sxs-lookup"><span data-stu-id="af316-118">**Network Element**</span></span>|<span data-ttu-id="af316-119">**Columnas necesarias**</span><span class="sxs-lookup"><span data-stu-id="af316-119">**Required Columns**</span></span>|
|:-----|:-----|
|<span data-ttu-id="af316-120">**Punto de acceso inalámbrico**</span><span class="sxs-lookup"><span data-stu-id="af316-120">**Wireless access point**</span></span> <br/> |<span data-ttu-id="af316-121">\<BSSID\>,\<descripción\>,\<ubicación\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...</span><span class="sxs-lookup"><span data-stu-id="af316-121">\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="af316-122">... \<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<estado\>,\<código postal\>,\<país\></span><span class="sxs-lookup"><span data-stu-id="af316-122">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="af316-123">**Subred**</span><span class="sxs-lookup"><span data-stu-id="af316-123">**Subnet**</span></span> <br/> |<span data-ttu-id="af316-124">\<Subred\>,\<descripción\>,\<ubicación\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...</span><span class="sxs-lookup"><span data-stu-id="af316-124">\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="af316-125">... \<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<estado\>,\<código postal\>,\<país\></span><span class="sxs-lookup"><span data-stu-id="af316-125">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="af316-126">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="af316-126">**Port**</span></span> <br/> |<span data-ttu-id="af316-127">\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<descripción\>,\<ubicación\>,\<CompanyName\>,\<HouseNumber\>,\< HouseNumberSuffix\>,...</span><span class="sxs-lookup"><span data-stu-id="af316-127">\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,…</span></span>  <br/> <span data-ttu-id="af316-128">... \<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<estado\>,\<código postal\>,\< País\></span><span class="sxs-lookup"><span data-stu-id="af316-128">…\<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="af316-129">**Conmutador**</span><span class="sxs-lookup"><span data-stu-id="af316-129">**Switch**</span></span> <br/> |<span data-ttu-id="af316-130">\<ChassisID\>,\<descripción\>,\<ubicación\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...</span><span class="sxs-lookup"><span data-stu-id="af316-130">\<ChassisID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="af316-131">... \<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<estado\>,\<código postal\>,\<país\></span><span class="sxs-lookup"><span data-stu-id="af316-131">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="af316-132">Para agregar elementos de red a la base de datos de ubicaciones</span><span class="sxs-lookup"><span data-stu-id="af316-132">To add network elements to the location database</span></span>

1. <span data-ttu-id="af316-133">Ejecute el cmdlet siguiente para agregar una ubicación de subred a la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="af316-133">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    <span data-ttu-id="af316-p104">Para las puertas de enlace ELIN, escriba el ELIN en el campo CompanyName. Puede incluir más de un ELIN. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="af316-p104">For ELIN gateways, put the ELIN in the CompanyName field. You can include more than one ELIN. For example:</span></span>
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    <span data-ttu-id="af316-137">También es posible ejecutar los cmdlets siguientes para actualizar en una sola acción las ubicaciones de subred mediante un archivo denominado "subnets.csv".</span><span class="sxs-lookup"><span data-stu-id="af316-137">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
   ```
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet

   ```

2. <span data-ttu-id="af316-138">Ejecute el cmdlet siguiente para agregar ubicaciones inalámbricas a la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="af316-138">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
   ```
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   <span data-ttu-id="af316-139">También es posible ejecutar los cmdlets siguientes para actualizar en una sola acción las ubicaciones inalámbricas mediante un archivo denominado "waps.csv".</span><span class="sxs-lookup"><span data-stu-id="af316-139">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
   ```
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. <span data-ttu-id="af316-140">Ejecute el cmdlet siguiente para agregar ubicaciones de conmutador a la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="af316-140">Run the following cmdlet to add switch locations to the location database.</span></span>
    
   ```
   Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   <span data-ttu-id="af316-141">También es posible ejecutar los cmdlets siguientes para actualizar en una sola acción las ubicaciones de conmutadores mediante un archivo denominado "switches.csv".</span><span class="sxs-lookup"><span data-stu-id="af316-141">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
   ```
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. <span data-ttu-id="af316-142">Ejecute el cmdlet siguiente para agregar ubicaciones de puertos a la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="af316-142">Run the following cmdlet to add port locations to the location database</span></span>
    
   ```
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   <span data-ttu-id="af316-p105">El valor predeterminado de PortIDSubType es LocallyAssigned. También se puede usar InterfaceAlias e InterfaceName</span><span class="sxs-lookup"><span data-stu-id="af316-p105">The default for PortIDSubType is LocallyAssigned. You can also set it to InterfaceAlias or InterfaceName</span></span>
    
   <span data-ttu-id="af316-145">También es posible ejecutar los cmdlets siguientes para actualizar en una sola acción las ubicaciones de puertos mediante un archivo denominado "ports.csv".</span><span class="sxs-lookup"><span data-stu-id="af316-145">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
   ```
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a><span data-ttu-id="af316-146">Validar direcciones</span><span class="sxs-lookup"><span data-stu-id="af316-146">Validate addresses</span></span>

### <a name="to-validate-addresses-located-in-the-location-database"></a><span data-ttu-id="af316-147">Para validar direcciones ubicadas en la base de datos de ubicaciones</span><span class="sxs-lookup"><span data-stu-id="af316-147">To validate addresses located in the location database</span></span>

1.  <span data-ttu-id="af316-148">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="af316-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="af316-149">Ejecute los cmdlets siguientes para configurar la conexión de proveedor de servicios de emergencia.</span><span class="sxs-lookup"><span data-stu-id="af316-149">Run the following cmdlets to configure the emergency service provider connection.</span></span>
    
   ```
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

   ```

3. <span data-ttu-id="af316-150">Ejecute el cmdlet siguiente para validar las direcciones en la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="af316-150">Run the following cmdlet to validate the addresses in the location database.</span></span>
    
   ```
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   <span data-ttu-id="af316-151">También puede utilizar el cmdlet **Test-CsLisCivicAddress** para validar las direcciones individuales.</span><span class="sxs-lookup"><span data-stu-id="af316-151">You can also use the **Test-CsLisCivicAddress** cmdlet to validate individual addresses.</span></span>
    
## <a name="publish-the-location-database"></a><span data-ttu-id="af316-152">Publicar la base de datos de ubicación</span><span class="sxs-lookup"><span data-stu-id="af316-152">Publish the location database</span></span>

<span data-ttu-id="af316-153">Las nuevas ubicaciones agregadas a la base de datos de ubicaciones no estarán disponibles para el cliente hasta que no se publiquen.</span><span class="sxs-lookup"><span data-stu-id="af316-153">The new locations that you added to the location database will not be made available to the client until they have been published.</span></span>
  
<span data-ttu-id="af316-154">Si usa puertas de enlace de número de identificación de ubicación de emergencia (ELIN), cargue también los ELIN en la base de datos de identificación de ubicación automática (ALI) del proveedor de la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="af316-154">If you use Emergency Location Identification Number (ELIN) gateways, you also need to upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span> <span data-ttu-id="af316-155">Probablemente el proveedor de RTC le solicite que use un formato específico para los registros de ELIN.</span><span class="sxs-lookup"><span data-stu-id="af316-155">Your PSTN carrier may require you to use a specific format for the ELIN records.</span></span> <span data-ttu-id="af316-156">Póngase en contacto con el proveedor de RTC para obtener más información al respecto.</span><span class="sxs-lookup"><span data-stu-id="af316-156">Contact your PSTN carrier for details.</span></span> <span data-ttu-id="af316-157">Puede exportar los registros de la base de datos del servicio de información de ubicación y darles formato según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="af316-157">You can export the records from the Location Information service database and format them as required.</span></span>
  
### <a name="to-publish-the-location-database"></a><span data-ttu-id="af316-158">Para publicar la base de datos de ubicaciones</span><span class="sxs-lookup"><span data-stu-id="af316-158">To publish the location database</span></span>

-  <span data-ttu-id="af316-159">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="af316-159">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
- <span data-ttu-id="af316-160">Ejecute el cmdlet siguiente para publicar la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="af316-160">Run the following cmdlet to publish the location database.</span></span>
    
  ```
  Publish-CsLisConfiguration

  ```


