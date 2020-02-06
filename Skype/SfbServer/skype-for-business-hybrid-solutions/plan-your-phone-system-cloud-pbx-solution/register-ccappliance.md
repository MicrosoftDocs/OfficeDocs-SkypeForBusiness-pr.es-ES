---
title: Register-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: El cmdlet Register-CcAppliance registra la información de los dispositivos en un sitio RTC en una configuración de inquilinos en línea. Los dispositivos deben registrarse antes de que el servicio de administración de Skype Empresarial Cloud Connector Edition pueda implementarlos y administrarlos.
ms.openlocfilehash: a94f9d7189f4872fcee2439afd2b210933f8bb06
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824306"
---
# <a name="register-ccappliance"></a>Register-CcAppliance
 
El cmdlet Register-CcAppliance registra la información de los dispositivos en un sitio RTC en una configuración de inquilinos en línea. Los dispositivos deben registrarse antes de que el servicio de administración de Skype Empresarial Cloud Connector Edition pueda implementarlos y administrarlos.
  
```powershell
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se registra la información del dispositivo actual a una configuración de inquilino en línea:
  
```powershell
Register-CcAppliance
```

### <a name="example-2"></a>Ejemplo 2

En el siguiente ejemplo se comprueba la configuración del registro localmente sin conectar con una configuración de inquilino en línea:
  
```powershell
Register-CcAppliance -Local
```

### <a name="example-3"></a>Ejemplo 3

En el siguiente ejemplo se registra el dispositivo actual con el nombre "Appliance1" en el sitio RTC "Site1":
  
```powershell
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

Deberá proporcionar el nombre y la contraseña de la cuenta de administrador de inquilinos. Use la cuenta que creó para la administración en línea de Cloud Connector. 
  
En la versión 1.4.2 y anterior, siga las instrucciones para proporcionar la contraseña del certificado externo, la contraseña del administrador en el modo seguro, la contraseña del administrador del dominio y la contraseña de administrador de la VM. 
  
En la versión 2,0 y posteriores, siga las instrucciones para proporcionar la contraseña del certificado externo, CceService contraseña y CABackupFile contraseña.
  
Al final del registro, reinicie el servicio de administración de conector de nube e inicie sesión en la cuenta servicios como CceService.
  
El SiteName combinado con el FQDN externo del servidor perimetral en el archivo CloudConnector.ini file se considera la identidad del sitio RTC. Si no se han usado ni el SiteName ni el FQDN externo del servidor perimetral para registrar un sitio, se creará un sitio nuevo para este dispositivo en una configuración de inquilino en línea. Si se encuentra una identidad de sitio RTC, un sitio RTC usará esta identidad y el dispositivo se registrará en este sitio RTC.  
  
En la siguiente situación, se producirá un error del cmdlet, que indicará que Site1 ya está registrado:  
  
- El SiteName es Site1 y el FQDN externo del servidor perimetral es edgserver1.contoso.com.  
    
- Un sitio RTC cuyo SiteName es Site1 y cuyo FQDN externo del servidor perimetral es edgserver.contoso.com.
    
- Se ha registrado un sitio RTC cuyo SiteName es NewSite y cuyo FQDN externo del servidor perimetral es edgserver1.contoso.com.  
    
El ApplianceName combinado con el FQDN del servidor de mediación en el archivo CloudConnector.ini file se considera la identidad de un dispositivo. Si no se han usado ni el ApplianceName ni el FQDN del servidor de mediación para registrar un dispositivo, se creará un dispositivo nuevo en la configuración de inquilino en línea. Si el dispositivo ya se ha registrado, se producirá un error del cmdlet.
  
En la siguiente situación, se producirá un error del cmdlet, que indicará que el dispositivo ya está registrado:  
  
- El ApplianceName es Appliance1 y el FQDN del servidor de mediación es ms1.vdomain.com.
    
- En el sitio RTC actual, si un dispositivo cuyo nombre es Appliance1 y cuyo FQDN del servidor de mediación es ms.vdomain.com, o el dispositivo cuyo nombre es NewAppliance y el FQDN del servidor de mediación es ms1.vdomain.com ya se ha registrado.
    
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Requerida.**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|SiteName  <br/> |Opcional   <br/> |System.String  <br/> |Nombre del sitio RTC en el que está registrado el dispositivo. El valor predeterminado es SiteName en el archivo CloudConnector.ini.   <br/> |
|ApplianceName  <br/> |Opcional   <br/> |System.String  <br/> |Nombre del dispositivo actual. El valor predeterminado es el nombre del equipo del servidor host.  <br/> |
|Local  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Se comprueba la configuración del registro localmente sin conectar con la configuración del inquilino en línea.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Register-CcAppliance no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

