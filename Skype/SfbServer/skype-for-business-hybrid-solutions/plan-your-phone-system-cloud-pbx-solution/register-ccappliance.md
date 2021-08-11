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
description: El cmdlet Register-CcAppliance registra la información del dispositivo en un sitio RTC en una configuración de inquilino en línea. Un dispositivo debe registrarse para poder implementarlo y administrarlo mediante el servicio Skype for Business Edición de conector de nube administración.
ms.openlocfilehash: 5b63ce38b358d41fea15551df1e8134d1b56db00851317cbc5c81ac8f3aea058
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288808"
---
# <a name="register-ccappliance"></a>Register-CcAppliance
 
El cmdlet Register-CcAppliance registra la información del dispositivo en un sitio RTC en una configuración de inquilino en línea. Un dispositivo debe registrarse para poder implementarlo y administrarlo mediante el servicio Skype for Business Edición de conector de nube administración.
  
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

Debe proporcionar el nombre y la contraseña de la cuenta de administrador del espacio empresarial. Use la cuenta que ha creado para la administración en línea de Cloud Connector. 
  
En la versión 1.4.2 y versiones anteriores, siga las instrucciones para proporcionar la contraseña de certificado externo, la contraseña de administrador del modo seguro, la contraseña de administrador de dominio y la contraseña de administrador de vm. 
  
En la versión 2.0 y posteriores, siga las instrucciones para proporcionar la contraseña del certificado externo, la contraseña de CceService y la contraseña CABackupFile.
  
Al final del registro, reinicie el servicio de administración de Cloud Connector e inicie sesión en los servicios como cuenta CceService.
  
SiteName combinado con el FQDN externo del servidor perimetral en el archivo CloudConnector.ini se considera una identidad de sitio RTC. Si no se ha usado siteName ni el FQDN externo del servidor perimetral para registrar un sitio, se creará un nuevo sitio para este dispositivo en una configuración de inquilino en línea. Si se encuentra una identidad de sitio RTC, un sitio RTC usará esta identidad y el dispositivo se registrará en este sitio RTC. 
  
En la siguiente situación, el cmdlet producirá un error e indicará que Site1 ya está registrado: 
  
- SiteName es Site1 y el FQDN externo del servidor perimetral es edgserver1.contoso.com. 
    
- Un sitio RTC cuyo SiteName es Site1 y el FQDN externo del servidor perimetral es edgserver.contoso.com.
    
- Se ha registrado un sitio RTC cuyo SiteName es NewSite y el FQDN externo del servidor perimetral edgserver1.contoso.com. 
    
ApplianceName combinado con el FQDN del servidor de mediación en CloudConnector.ini se considera una identidad de dispositivo. Si no se han usado appliancename ni el FQDN del servidor de mediación para registrar un dispositivo, se creará un nuevo dispositivo en la configuración del espacio empresarial en línea. Si el dispositivo ya está registrado, se producirá un error en el cmdlet.
  
En la siguiente situación, el cmdlet producirá un error e indicará que el dispositivo ya está registrado: 
  
- ApplianceName es Appliance1 y el FQDN del servidor de mediación es ms1.vdomain.com.
    
- En el sitio RTC actual, si un dispositivo cuyo nombre Appliance1 y FQDN del servidor de mediación es ms.vdomain.com o un dispositivo cuyo nombre NewAppliance y FQDN del servidor de mediación ms1.vdomain.com se ha registrado.
    
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Required**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|SiteName  <br/> |Opcional  <br/> |System.String  <br/> |Nombre del sitio RTC en el que está registrado el dispositivo. El valor predeterminado es SiteName value en el CloudConnector.ini archivo.  <br/> |
|ApplianceName  <br/> |Opcional  <br/> |System.String  <br/> |Nombre del dispositivo actual. El valor predeterminado es el nombre del equipo del servidor host.  <br/> |
|Local  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Compruebe las configuraciones para el registro localmente sin conectarse a la configuración del espacio empresarial en línea.  <br/> |
   
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
  

