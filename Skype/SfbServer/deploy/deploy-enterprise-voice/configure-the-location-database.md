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
# <a name="configure-the-location-database-in-skype-for-business-server"></a>Configuración de la base de datos de ubicación en Skype para Business Server
 
Configurar, rellenar y publicar la base de datos de ubicación de E9-1-1 en Skype para Business Server Enterprise Voice. 
  
Para habilitar clientes de modo que detecten automáticamente su ubicación dentro de una red, primero tiene que configurar la base de datos de ubicaciones. 
  
Para configurar la base de datos de ubicaciones, deberá realizar las siguientes tareas:
  
- Llene la base de datos con una búsqueda de elementos de red a las ubicaciones. Si utiliza una puerta de enlace de número de identificación de ubicación de emergencia (ELIN), debe incluir los ELIN en la \<CompanyName\> campo.
    
    Si no rellena la base de datos de ubicaciones y el valor de **Ubicación obligatoria** de la directiva de ubicación se define en **Sí** o **Declinación de responsabilidades**, el cliente indicará al usuario que especifique una ubicación manualmente.
    
- Valide las direcciones comparándolas con la Guía de calles maestra (MSAG) mantenida por el proveedor de servicios E9-1-1.
    
- Publique la base de datos actualizada.
    
## <a name="populate-the-location-database"></a>Rellenar la base de datos de ubicación

Para buscar clientes en una red de manera automática, primero es preciso rellenar la base de datos de ubicaciones con un diagrama de cableado de red, que asigna elementos de red a direcciones postales. Para definir el diagrama de cableado, puede usar subredes, puntos de acceso inalámbrico, conmutadores y puertos.
  
Puede agregar direcciones a la base de datos de ubicaciones una a una, pero también puede incorporar varias de ellas a la vez mediante un archivo .csv con los formatos de columna que se describen en la tabla siguiente.
  
Si utiliza una puerta de enlace de Número de identificación de ubicación de emergencia (ELIN), incluya el ELIN en el campo **CompanyName** de cada ubicación. Puede incluir varios ELIN para cada ubicación, separándolos por un punto y coma.
  
|**Elemento de red**|**Columnas obligatorias**|
|:-----|:-----|
|**Punto de acceso inalámbrico** <br/> |\<BSSID\>,\<descripción\>,\<ubicación\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...  <br/> ... \<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<Ciudad\>,\<estado\>,\<PostalCode\>,\<país\>  <br/> |
|**Subred** <br/> |\<Subred\>,\<descripción\>,\<ubicación\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...  <br/> ... \<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<Ciudad\>,\<estado\>,\<PostalCode\>,\<país\>  <br/> |
|**Puerto** <br/> |\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<descripción\>,\<ubicación\>,\<CompanyName\>,\<HouseNumber\>,\< HouseNumberSuffix\>,...  <br/> ... \<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<Ciudad\>,\<estado\>,\<PostalCode\>,\< País\>  <br/> |
|**Conmutador** <br/> |\<ChassisID\>,\<descripción\>,\<ubicación\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...  <br/> ... \<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<Ciudad\>,\<estado\>,\<PostalCode\>,\<país\>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a>Para agregar elementos de red a la base de datos de ubicaciones

1. Ejecute el cmdlet siguiente para agregar una ubicación de subred a la base de datos de ubicaciones.
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    Para las puertas de enlace ELIN, escriba el ELIN en el campo CompanyName. Puede incluir más de un ELIN. Por ejemplo:
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    También es posible ejecutar los cmdlets siguientes para actualizar en una sola acción las ubicaciones de subred mediante un archivo denominado "subnets.csv".
    
   ```
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. Ejecute el cmdlet siguiente para agregar ubicaciones inalámbricas a la base de datos de ubicaciones.
    
   ```
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   También es posible ejecutar los cmdlets siguientes para actualizar en una sola acción las ubicaciones inalámbricas mediante un archivo denominado "waps.csv".
    
   ```
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. Ejecute el cmdlet siguiente para agregar ubicaciones de conmutador a la base de datos de ubicaciones.
    
   ```
   Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   También es posible ejecutar los cmdlets siguientes para actualizar en una sola acción las ubicaciones de conmutadores mediante un archivo denominado "switches.csv".
    
   ```
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. Ejecute el cmdlet siguiente para agregar ubicaciones de puertos a la base de datos de ubicaciones.
    
   ```
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   El valor predeterminado de PortIDSubType es LocallyAssigned. También se puede usar InterfaceAlias e InterfaceName
    
   También es posible ejecutar los cmdlets siguientes para actualizar en una sola acción las ubicaciones de puertos mediante un archivo denominado "ports.csv".
    
   ```
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a>Validar direcciones

### <a name="to-validate-addresses-located-in-the-location-database"></a>Para validar direcciones ubicadas en la base de datos de ubicaciones

1.  Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Ejecute los cmdlets siguientes para configurar la conexión de proveedor de servicios de emergencia.
    
   ```
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd
   ```

3. Ejecute el cmdlet siguiente para validar las direcciones en la base de datos de ubicaciones.
    
   ```
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   También puede usar el cmdlet **Test-CsLisCivicAddress** para validar direcciones individuales.
    
## <a name="publish-the-location-database"></a>Publicar la base de datos de ubicación

Las nuevas ubicaciones agregadas a la base de datos de ubicaciones no estarán disponibles para el cliente hasta que no se publiquen.
  
Si usa puertas de enlace de número de identificación de ubicación de emergencia (ELIN), cargue también los ELIN en la base de datos de identificación de ubicación automática (ALI) del proveedor de la red telefónica conmutada (RTC). Probablemente el proveedor de RTC le solicite que use un formato específico para los registros de ELIN. Póngase en contacto con el proveedor de RTC para obtener más información al respecto. Puede exportar los registros de la base de datos de servicio de información de ubicación y aplicarles formato según sea necesario.
  
### <a name="to-publish-the-location-database"></a>Para publicar la base de datos de ubicaciones

-  Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
- Ejecute el cmdlet siguiente para publicar la base de datos de ubicaciones.
    
  ```
  Publish-CsLisConfiguration
  ```


