---
title: Get-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: 'The Get-CcCredential cmdlet returns the credential of the current Skype for Business Cloud Connector Edition deployment. '
ms.openlocfilehash: 87dd3934767a4be7afb57889fd0641e8507fba13
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287338"
---
# <a name="get-cccredential"></a>Get-CcCredential
 
The Get-CcCredential cmdlet returns the credential of the current Skype for Business Cloud Connector Edition deployment.  
  
Con la versión 2,0 y posteriores, también puede usar el parámetro-DisplayPassword para mostrar las contraseñas de TenantAdmin, esusuario y VMAdmin.
  
```
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

El siguiente ejemplo devuelve las credenciales del administrador de dominio del dominio de la máquina virtual de Cloud Connector.
  
```
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

El cmdlet Get-CcCredential devuelve información de las credenciales sobre el tipo de cuenta especificada. Estas credenciales las especifica el administrador que ejecuta los cmdlets Register-CcAppliance e Install-CcAppliance al implementar el dispositivo actual.  
  
El cmdlet Get-CcCredential devuelve una instancia del objeto System.Management.Automation.PSCredential. La propiedad de contraseña del objeto devuelto es System.Security.SecureString.
  
Si desea obtener el texto claro de la contraseña del administrador de dominio, asegúrese la cuenta que haya iniciado la sesión introduzca la contraseña en el servidor host. Después abra una consola de PowerShell como administrador y ejecute el siguiente script:
  
```
$cred = Get-CcCredential -AccountType DomainAdmin
$password =  $cred.Password
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($password);
$text = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr);
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr);
Write-Host $text
```

## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Requerida.**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> |Requerido  <br/> | System.String <br/> | AccountType value can be one of the following: <br/>  VmAdmin: el administrador local de máquinas virtuales del conector en la nube. <br/>  DomainAdmin: Domain administrator of Cloud Connector virtual machine domain. <br/>  SafeModeAdmin: SafeModeAdmin del controlador de dominio de la máquina virtual de Cloud Connector. <br/>  ExternalCert: cuenta del certificado interno instalado en el servidor perimetral. <br/>  TenantAdmin: administrador del inquilino de O365. <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Get-CcCredential no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

The Get-CcCredential cmdlet returns an instance of the System.Management.Automation.PSCredential object.
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Set-CcCredential](set-cccredential.md)
  

