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
description: El cmdlet Register-CcAppliance registra la información del dispositivo en un sitio RTC en una configuración de inquilino en línea. Un dispositivo debe registrarse para poder implementarse y administrarse mediante el servicio de administración de Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: a94f9d7189f4872fcee2439afd2b210933f8bb06
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824306"
---
# <a name="register-ccappliance"></a>Register-CcAppliance
 
El cmdlet Register-CcAppliance registra la información del dispositivo en un sitio RTC en una configuración de inquilino en línea. Un dispositivo debe registrarse para poder implementarse y administrarse mediante el servicio de administración de Skype Empresarial Cloud Connector Edition.
  
```powershell
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se registra la información del dispositivo actual en una configuración de inquilino en línea:
  
```powershell
Register-CcAppliance
```

### <a name="example-2"></a>Ejemplo 2

En el siguiente ejemplo se comprueba la configuración del registro localmente sin conectarse a una configuración de inquilino en línea:
  
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

Debe proporcionar el nombre y la contraseña de la cuenta de administrador de inquilinos. Use la cuenta que ha creado para la administración en línea de Cloud Connector. 
  
En la versión 1.4.2 y anteriores, siga las instrucciones para proporcionar la contraseña del certificado externo, la contraseña de administrador de modo seguro, la contraseña de administrador de dominio y la contraseña de administrador de máquina virtual. 
  
En la versión 2.0 y posteriores, siga las instrucciones para proporcionar la contraseña del certificado externo, la contraseña de CceService y la contraseña caBackupFile.
  
Al final del registro, reinicie el servicio de administración de Cloud Connector e inicie sesión en los servicios como cuenta CceService.
  
SiteName combinado con el FQDN externo del servidor perimetral en el CloudConnector.ini se considera una identidad de sitio RTC. Si no se ha usado ni siteName ni el FQDN externo del servidor perimetral para registrar un sitio, se creará un nuevo sitio para este dispositivo en una configuración de inquilino en línea. Si se encuentra una identidad de sitio RTC, un sitio RTC usará esta identidad y el dispositivo se registrará en este sitio RTC. 
  
En la siguiente situación, se producirá un error en el cmdlet e indicará que Site1 ya está registrado: 
  
- SiteName es Site1 y el FQDN externo del servidor perimetral es edgserver1.contoso.com. 
    
- Un sitio RTC cuyo SiteName es Site1 y el FQDN externo del servidor perimetral es edgserver.contoso.com.
    
- Se ha registrado un sitio RTC cuyo SiteName es NewSite y el FQDN externo edgserver1.contoso.com servidor perimetral. 
    
ApplianceName combinado con el FQDN del servidor de mediación en CloudConnector.ini archivo se considera una identidad de dispositivo. Si no se han usado ni el ApplianceName ni el FQDN del servidor de mediación para registrar un dispositivo, se creará un nuevo dispositivo en la configuración del inquilino en línea. Si el dispositivo ya está registrado, se producirá un error en el cmdlet.
  
En la siguiente situación, se producirá un error en el cmdlet e indicará que el dispositivo ya está registrado: 
  
- ApplianceName es Appliance1 y el FQDN del servidor de mediación es ms1.vdomain.com.
    
- En el sitio RTC actual, si un dispositivo cuyo nombre es Appliance1 y FQDN del servidor de mediación es ms.vdomain.com o un dispositivo cuyo nombre es NewAppliance y FQDN del servidor de mediación ms1.vdomain.com se ha registrado.
    
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Required**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|SiteName  <br/> |Opcional  <br/> |System.String  <br/> |Nombre del sitio RTC en el que está registrado el dispositivo. El valor predeterminado es SiteName en el CloudConnector.ini archivo.  <br/> |
|ApplianceName  <br/> |Opcional  <br/> |System.String  <br/> |Nombre del dispositivo actual. El valor predeterminado es el nombre de equipo del servidor host.  <br/> |
|Local  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Compruebe las configuraciones para el registro localmente sin conectarse a la configuración de inquilinos en línea.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El Register-CcAppliance no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Vea también
<a name="ReturnTypes"> </a>

[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

