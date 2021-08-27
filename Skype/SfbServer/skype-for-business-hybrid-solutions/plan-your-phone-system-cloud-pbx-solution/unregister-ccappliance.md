---
title: Unregister-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: El cmdlet Unregister-CcAppliance anula el registro de la aplicación Skype for Business Edición de conector de nube actual de un sitio RTC en la configuración del espacio empresarial en línea.
ms.openlocfilehash: c48a7b53d757dab446a8939a3e3203d8e66fccab
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58603659"
---
# <a name="unregister-ccappliance"></a>Unregister-CcAppliance
 
El cmdlet Unregister-CcAppliance anula el registro de la aplicación Skype for Business Edición de conector de nube actual de un sitio RTC en la configuración del espacio empresarial en línea.
  
```powershell
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se anula el registro de un dispositivo actual de la configuración del espacio empresarial en línea:
  
```powershell
Unregister-CcAppliance
```

### <a name="example-2"></a>Ejemplo 2

En el siguiente ejemplo se comprueba la configuración para anular el registro localmente sin conectarse a la configuración del espacio empresarial en línea:
  
```powershell
Unregister-CcAppliance -Local
```

### <a name="example-3"></a>Ejemplo 3

En el siguiente ejemplo se anula el registro del dispositivo actual con el nombre "Appliance1" al sitio RTC "Site1":
  
```powershell
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

Al igual que el cmdlet Register-CcAppliance, SiteName combinado con el FQDN externo del servidor perimetral en el archivo CloudConnector.ini se considera una identidad de sitio RTC. Del mismo modo, ApplianceName combinado con el FQDN del servidor de mediación en el archivo CloudConnector.ini se considera una identidad de dispositivo.
  
Después de anular el registro del dispositivo, reinicie el servicio de administración de Cloud Connector e inicie sesión como la cuenta NetworkService.
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Required**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
| SiteName <br/> |Opcional  <br/> |System.String  <br/> |Nombre del sitio RTC donde está registrado el dispositivo. El valor predeterminado es SiteName en CloudConnector.ini archivo.  <br/> |
|ApplianceName  <br/> |Opcional  <br/> |System.String  <br/> |Nombre del dispositivo actual. El valor predeterminado es el nombre del equipo del servidor host.  <br/> |
|Local  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Compruebe la configuración para el registro localmente sin conectarse a una configuración de inquilino en línea.  <br/> |
   
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
  

