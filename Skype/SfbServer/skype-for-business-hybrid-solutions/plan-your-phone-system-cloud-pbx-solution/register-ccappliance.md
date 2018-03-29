---
title: Registro CcAppliance
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: El cmdlet Register-CcAppliance registra la información de los dispositivos en un sitio RTC en una configuración de inquilinos en línea. Los dispositivos deben registrarse antes de que el servicio de administración de Skype Empresarial Cloud Connector Edition pueda implementarlos y administrarlos.
ms.openlocfilehash: 8f1156ccd32b101e6eab957bc3ce7549a3bcc7d7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="register-ccappliance"></a>Registro CcAppliance
 
El cmdlet Register-CcAppliance registra la información de los dispositivos en un sitio RTC en una configuración de inquilinos en línea. Los dispositivos deben registrarse antes de que el servicio de administración de Skype Empresarial Cloud Connector Edition pueda implementarlos y administrarlos.
  
```
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se registra la información del dispositivo actual a una configuración de inquilino en línea:
  
```
Register-CcAppliance
```

### <a name="example-2"></a>Ejemplo 2

En el siguiente ejemplo se comprueba la configuración del registro localmente sin conectar con una configuración de inquilino en línea:
  
```
Register-CcAppliance -Local
```

### <a name="example-3"></a>Ejemplo 3

En el siguiente ejemplo se registra el dispositivo actual con el nombre "Appliance1" en el sitio RTC "Site1":
  
```
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

Deberá proporcionar el nombre y la contraseña de la cuenta de administrador de inquilinos. Utilizar la cuenta que haya creado para administración en línea del conector de la nube. 
  
En versión 1.4.2 y versiones anteriores, siga las instrucciones para proporcionar la contraseña de certificado externo, contraseña de admin de modo seguro, contraseña de administrador de dominio y contraseña de administrador de la máquina virtual. 
  
En la versión 2.0 y posterior, siga las instrucciones para proporcionar la contraseña de certificado externo, contraseña de CceService y CABackupFile.
  
Al final del registro, reinicie el servicio de administración del conector de la nube y los servicios de inicio de sesión como cuenta de CceService.
  
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
|Nombre del sitio  <br/> |Opcional   <br/> |System.String  <br/> |Nombre del sitio RTC en el que está registrado el dispositivo. El valor predeterminado es SiteName en el archivo CloudConnector.ini.   <br/> |
|ApplianceName  <br/> |Opcional  <br/> |System.String  <br/> |Nombre del dispositivo actual. El valor predeterminado es el nombre del equipo del servidor host.  <br/> |
|Local  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Se comprueba la configuración del registro localmente sin conectar con la configuración del inquilino en línea.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Register-CcAppliance no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Anular el registro de CcAppliance](unregister-ccappliance.md)
  
[CcAppliance publicar](publish-ccappliance.md)
  
[Instalar CcAppliance](install-ccappliance.md)
  
[CcAppliance desinstalar](uninstall-ccappliance.md)
  

