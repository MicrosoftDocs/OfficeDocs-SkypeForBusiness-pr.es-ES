---
title: Unregister-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: El cmdlet Unregister-CcAppliance anula el registro del dispositivo actual de Skype Empresarial Cloud Connector Edition de un sitio RTC en la configuración del inquilino en línea.
ms.openlocfilehash: 6ee21f66c2b189aff8c8aa7d831369536618b18c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892007"
---
# <a name="unregister-ccappliance"></a>Unregister-CcAppliance
 
El cmdlet Unregister-CcAppliance anula el registro del dispositivo actual de Skype Empresarial Cloud Connector Edition de un sitio RTC en la configuración del inquilino en línea.
  
```
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se anula el registro de un dispositivo actual de la configuración del inquilino en línea.
  
```
Unregister-CcAppliance
```

### <a name="example-2"></a>Ejemplo 2

En el siguiente ejemplo se comprueba la configuración para anular el registro localmente sin conectar con la configuración del inquilino en línea:
  
```
Unregister-CcAppliance -Local
```

### <a name="example-3"></a>Ejemplo 3

En el siguiente ejemplo se anula el registro del dispositivo actual con el nombre "Appliance1" del sitio RTC "Site1":
  
```
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

Igual que con el cmdlet Register-CcAppliance, la combinación de SiteName con el FQDN externo del servidor perimetral en el archivo CloudConnector.ini file se considera una identidad de sitio RTC. Del mismo modo, la combinación de ApplianceName con el FQDN del servidor de mediación en el archivo CloudConnector.ini se considera una identidad de dispositivo.
  
Después de que el dispositivo se anula el registro, reinicie el servicio de administración de conector en la nube e inicie sesión como la cuenta de NetworkService.
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Requerida.**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
| SiteName <br/> |Opcional   <br/> |System.String  <br/> |Nombre del sitio RTC en el que está registrado el dispositivo. El valor predeterminado es SiteName en el archivo CloudConnector.ini.  <br/> |
|ApplianceName  <br/> |Opcional   <br/> |System.String  <br/> |Nombre del dispositivo actual. El valor predeterminado es el nombre del equipo del servidor host.  <br/> |
|Local  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Se comprueba la configuración del registro localmente sin conectar con la configuración del inquilino en línea.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Unregister-CcAppliance no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Register-CcAppliance](register-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  

