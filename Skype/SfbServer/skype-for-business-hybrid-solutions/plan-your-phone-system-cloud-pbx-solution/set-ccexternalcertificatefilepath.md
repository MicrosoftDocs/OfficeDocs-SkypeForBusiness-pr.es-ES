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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: El cmdlet Set-CcExternalCertificateFilePath especifica la ruta de acceso donde se almacena el certificado para el servidor de mediación o el servidor perimetral.
ms.openlocfilehash: b8555d3a3c6770481e1a66f79fd4a1060d3d9936
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615526"
---
# <a name="set-ccexternalcertificatefilepath"></a>Set-CcExternalCertificateFilePath
 
El cmdlet Set-CcExternalCertificateFilePath especifica la ruta de acceso donde se almacena el certificado para el servidor de mediación o el servidor perimetral.
  
Este certificado es necesario durante la implementación o al agregar nuevos dispositivos de Skype for Business Edición de conector de nube. El comando también permite importar un nuevo certificado para el servidor de mediación después de la implementación.
  
Este cmdlet se aplica a Skype for Business Edición de conector de nube 1.4.1, 1.4.2.
  
```powershell
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se establece la ruta de acceso del certificado para el servidor perimetral:
  
```powershell
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a>Ejemplo 2

En el siguiente ejemplo se establece la ruta de acceso del certificado para el servidor de mediación:
  
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

Durante la implementación o al modificar la topología, debe especificar la ruta de acceso para el certificado del servidor perimetral y, opcionalmente, para el certificado del servidor de mediación. 
  
El certificado para el servidor de mediación es necesario si se usará TLS entre las puertas de enlace y el servidor de mediación. Al implementar un dispositivo de Cloud Connector y desea implementar TLS, solo puede especificar la ruta de acceso al certificado que se implementará en el servidor de mediación. Sin embargo, si desea actualizar el certificado de mediación en un dispositivo ya implementado, debe especificar la ruta de acceso y el parámetro -Import. Para ver la ruta de acceso, use el cmdlet Get-CCExternalCertificateFilePath.
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Required**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
| Objetivo <br/> | Obligatorio <br/> |System.String  <br/> |Tipo de ruta de acceso de archivo solicitada. Los tipos incluyen:  <br/> EdgeServer (predeterminado)  <br/> MediationServer  <br/> |
|Importar  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Indica que el certificado debe importarse al servidor de mediación. Este parámetro no es necesario si implementa un dispositivo por primera vez. El parámetro es necesario si desea cambiar el certificado existente en una versión ya implementada.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

El cmdlet Set-CcExternalCertificateFilePath no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md)
  

