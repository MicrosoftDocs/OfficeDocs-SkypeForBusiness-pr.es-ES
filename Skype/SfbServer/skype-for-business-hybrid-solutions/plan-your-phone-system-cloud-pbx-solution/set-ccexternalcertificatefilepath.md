---
title: Set-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: El cmdlet Set-CcExternalCertificateFilePath especifica la ruta de acceso en la que se almacena el certificado del servidor de mediación o del servidor perimetral.
ms.openlocfilehash: e71a50f09a4ce3d085746c30f7591e8a07eb38de
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003210"
---
# <a name="set-ccexternalcertificatefilepath"></a>Set-CcExternalCertificateFilePath
 
El cmdlet Set-CcExternalCertificateFilePath especifica la ruta de acceso en la que se almacena el certificado del servidor de mediación o del servidor perimetral.
  
Este certificado es necesario durante la implementación o al agregar nuevos dispositivos de Skype Empresarial Cloud Connector Edition. El comando también permite la importación de un nuevo certificado para el servidor de mediación después de la implementación.
  
Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se establece la ruta de acceso del certificado del servidor perimetral:
  
```powershell
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a>Ejemplo 2

En el siguiente ejemplo se establece la ruta de acceso del certificado del servidor de mediación:
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a>Ejemplo 3

En el siguiente ejemplo se actualiza el certificado del servidor de mediación:
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

Durante la implementación, o al modificar la topología, deberá especificar la ruta del certificado del servidor perimetral y, opcionalmente, la del certificado del servidor de mediación. 
  
El certificado del servidor de mediación es necesario si se usa TLS entre las puertas de enlace y el servidor de mediación. Al implementar un dispositivo de conector de nube y desea implementar TLS, solo puede especificar la ruta de acceso al certificado que se implementará en el servidor de mediación. Sin embargo, si desea actualizar el certificado del servidor de mediación en un dispositivo que ya se ha implementado, deberá especificar la ruta y el parámetro -Import. Para ver la ruta, use el cmdlet Get-CCExternalCertificateFilePath.
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Requerida.**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
| Target <br/> | Requerido <br/> |System.String  <br/> |El tipo de ruta de archivo que se ha solicitado. Los tipos incluyen:  <br/> EdgeServer (predeterminado)  <br/> MediationServer  <br/> |
|Import  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Indica que el certificado se debe importar al servidor de mediación. Este parámetro no se necesita si se implementa un dispositivo por primera vez. El parámetro es necesario si desea cambiar el certificado existente en una versión que ya se ha implementado.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

El cmdlet Set-CcExternalCertificateFilePath no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md)
  

