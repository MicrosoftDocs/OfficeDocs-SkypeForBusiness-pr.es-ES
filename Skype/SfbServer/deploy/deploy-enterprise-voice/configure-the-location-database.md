---
title: Configurar la base de datos de ubicación en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: Configurar, rellenar y publicar la base de datos de ubicaciones E9-1-1 en Skype empresarial Enterprise Voice.
ms.openlocfilehash: 1e972e78af1a83e68c2d28d0f636128b7c339cf2
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001310"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a>Configurar la base de datos de ubicación en Skype empresarial Server
 
Configurar, rellenar y publicar la base de datos de ubicaciones E9-1-1 en Skype empresarial Enterprise Voice. 
  
Para habilitar clientes de modo que detecten automáticamente su ubicación dentro de una red, primero tiene que configurar la base de datos de ubicaciones. 
  
Para configurar la base de datos de ubicaciones, deberá realizar las siguientes tareas:
  
- Llene la base de datos con una búsqueda de elementos de red a las ubicaciones. Si usa una puerta de enlace de número de identificación de ubicación de emergencia (ELIN), tendrá que incluir \<la\> Elin en el campo NombreCompañía.
    
    Si no rellena la base de datos de ubicaciones y el valor de **Ubicación obligatoria** de la directiva de ubicación se define en **Sí** o **Declinación de responsabilidades**, el cliente indicará al usuario que especifique una ubicación manualmente.
    
- Valide las direcciones comparándolas con la Guía de calles maestra (MSAG) mantenida por el proveedor de servicios E9-1-1.
    
- Publique la base de datos actualizada.
    
## <a name="populate-the-location-database"></a>Rellenar la base de datos de ubicación

Para buscar clientes en una red de manera automática, primero es preciso rellenar la base de datos de ubicaciones con un diagrama de cableado de red, que asigna elementos de red a direcciones postales. Para definir el diagrama de cableado, puede usar subredes, puntos de acceso inalámbrico, conmutadores y puertos.
  
Puede agregar direcciones a la base de datos de ubicaciones una a una, pero también puede incorporar varias de ellas a la vez mediante un archivo .csv con los formatos de columna que se describen en la tabla siguiente.
  
Si utiliza una puerta de enlace de Número de identificación de ubicación de emergencia (ELIN), incluya el ELIN en el campo **CompanyName** de cada ubicación. Puede incluir varios ELIN para cada ubicación, separándolos por un punto y coma.
  
|**Elemento de red**|**Columnas obligatorias**|
|:-----|:-----|
|**Punto de acceso inalámbrico** <br/> |\<BSSID\>,\<Descripción\>,\<ubicación\>,\<NombreCompañía\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<predireccional\>,...  <br/> ... \<StreetName\>,\<StreetSuffix\>,\<posdireccional\>,\<ciudad\>,\<estado\>,\<CódigoPostal\>,\<país\>  <br/> |
|**Subred** <br/> |\<Subred\>,\<Descripción\>,\<ubicación\>,\<NombreCompañía\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<predireccional\>,...  <br/> ... \<StreetName\>,\<StreetSuffix\>,\<posdireccional\>,\<ciudad\>,\<estado\>,\<CódigoPostal\>,\<país\>  <br/> |
|**Puerto** <br/> |\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Descripción\>,\<ubicación\>,\<NombreCompañía\>,\<HouseNumber\>,\<HouseNumberSuffix\>,...  <br/> ... \<Predireccionales\>,\<StreetName\>,\<StreetSuffix\>,\<posdireccionales\>,\<ciudad\>,\<estado\>,\<CódigoPostal\>,\<país\>  <br/> |
|**Conmutador** <br/> |\<ChassisID\>,\<Descripción\>,\<ubicación\>,\<NombreCompañía\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<predireccional\>,...  <br/> ... \<StreetName\>,\<StreetSuffix\>,\<posdireccional\>,\<ciudad\>,\<estado\>,\<CódigoPostal\>,\<país\>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a>Para agregar elementos de red a la base de datos de ubicaciones

1. Ejecute el cmdlet siguiente para agregar una ubicación de subred a la base de datos de ubicaciones.
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    Para las puertas de enlace ELIN, escriba el ELIN en el campo CompanyName. Puede incluir más de un ELIN. Por ejemplo:
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    También es posible ejecutar los cmdlets siguientes para actualizar en una sola acción las ubicaciones de subred mediante un archivo denominado "subnets.csv".
    
   ```powershell
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. Ejecute el cmdlet siguiente para agregar ubicaciones inalámbricas a la base de datos de ubicaciones.
    
   ```powershell
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   También es posible ejecutar los cmdlets siguientes para actualizar en una sola acción las ubicaciones inalámbricas mediante un archivo denominado "waps.csv".
    
   ```powershell
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. Ejecute el cmdlet siguiente para agregar ubicaciones de conmutador a la base de datos de ubicaciones.
    
   ```powershell
   Set-CsLisSwitch -ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   También es posible ejecutar los cmdlets siguientes para actualizar en una sola acción las ubicaciones de conmutadores mediante un archivo denominado "switches.csv".
    
   ```powershell
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. Ejecute el cmdlet siguiente para agregar ubicaciones de puertos a la base de datos de ubicaciones.
    
   ```powershell
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   El valor predeterminado de PortIDSubType es LocallyAssigned. También se puede usar InterfaceAlias e InterfaceName
    
   También es posible ejecutar los cmdlets siguientes para actualizar en una sola acción las ubicaciones de puertos mediante un archivo denominado "ports.csv".
    
   ```powershell
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a>Validar direcciones

### <a name="to-validate-addresses-located-in-the-location-database"></a>Para validar direcciones ubicadas en la base de datos de ubicaciones

1.  Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Ejecute los cmdlets siguientes para configurar la conexión de proveedor de servicios de emergencia.
    
   ```powershell
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd
   ```

3. Ejecute el cmdlet siguiente para validar las direcciones en la base de datos de ubicaciones.
    
   ```powershell
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   También puede usar el cmdlet **Test-CsLisCivicAddress** para validar direcciones individuales.
    
## <a name="publish-the-location-database"></a>Publicar la base de datos de ubicación

Las nuevas ubicaciones agregadas a la base de datos de ubicaciones no estarán disponibles para el cliente hasta que no se publiquen.
  
Si usa puertas de enlace de número de identificación de ubicación de emergencia (ELIN), cargue también los ELIN en la base de datos de identificación de ubicación automática (ALI) del proveedor de la red telefónica conmutada (RTC). Probablemente el proveedor de RTC le solicite que use un formato específico para los registros de ELIN. Póngase en contacto con el proveedor de RTC para obtener más información al respecto. Puede exportar los registros de la base de datos de servicios de información de ubicación y darles formato según sea necesario.
  
### <a name="to-publish-the-location-database"></a>Para publicar la base de datos de ubicaciones

-  Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
- Ejecute el cmdlet siguiente para publicar la base de datos de ubicaciones.
    
  ```powershell
  Publish-CsLisConfiguration
  ```


