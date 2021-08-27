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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: El cmdlet Get-CcCredential devuelve la credencial de la implementación Skype for Business Edición de conector de nube actual.
ms.openlocfilehash: 158f6e35f667410a0070e2f7030932bd6fc35ade
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596364"
---
# <a name="get-cccredential"></a>Get-CcCredential
 
El cmdlet Get-CcCredential devuelve la credencial de la implementación Skype for Business Edición de conector de nube actual. 
  
Con la versión 2.0 y versiones posteriores, también puede usar el parámetro -DisplayPassword para mostrar las contraseñas de TenantAdmin, DomainAdmin y VMAdmin.
  
```powershell
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se devuelve la credencial del administrador de dominio del dominio de máquina virtual de Cloud Connector:
  
```powershell
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

El cmdlet Get-CcCredential devuelve la información de credenciales sobre el tipo de cuenta especificado. Estas credenciales las especifica el administrador que ejecuta los cmdlets Register-CcAppliance y Install-CcAppliance al implementar el dispositivo actual. 
  
El cmdlet Get-CcCredential devuelve una instancia del objeto System.Management.Automation.PSCredential. La propiedad password del objeto devuelto es System.Security.SecureString.
  
Si desea obtener el texto sin formato de la contraseña de administrador de dominio, asegúrese de que la cuenta de inicio de sesión actual la introduzca en el servidor host y, a continuación, abra una consola de PowerShell como administrador y ejecute el script siguiente:
  
```powershell
$cred = Get-CcCredential -AccountType DomainAdmin
$password =  $cred.Password
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($password);
$text = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr);
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr);
Write-Host $text
```

## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Required**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> |Obligatorio  <br/> | System.String <br/> | El valor AccountType puede ser uno de los siguientes: <br/>  VmAdmin: el administrador local de máquinas virtuales de Cloud Connector. <br/>  DomainAdmin: administrador de dominio del dominio de máquina virtual de Cloud Connector. <br/>  SafeModeAdmin: SafeModeAdmin del controlador de dominio de máquina virtual de Cloud Connector. <br/>  ExternalCert: cuenta del certificado externo instalado en el servidor perimetral. <br/>  TenantAdmin: administrador del inquilino de O365. <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Get-CcCredential no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

El cmdlet Get-CcCredential devuelve una instancia del objeto System.Management.Automation.PSCredential.
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Set-CcCredential](set-cccredential.md)
  

