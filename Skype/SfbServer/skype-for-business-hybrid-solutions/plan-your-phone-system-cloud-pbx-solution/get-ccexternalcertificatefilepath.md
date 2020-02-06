---
title: Get-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: El cmdlet Get-CcExternalCertificateFilePath devuelve la ruta de acceso del archivo de certificados externos de la implementación de Skype Empresarial Cloud Connector Edition. El usuario debe preparar este certificado.
ms.openlocfilehash: 143595d30bb71756544a16ad464da05a229f476d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799910"
---
# <a name="get-ccexternalcertificatefilepath"></a>Get-CcExternalCertificateFilePath
 
El cmdlet Get-CcExternalCertificateFilePath devuelve la ruta de acceso del archivo de certificados externos de la implementación de Skype Empresarial Cloud Connector Edition. El usuario debe preparar este certificado.
  
Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se muestra la ruta de acceso del certificado del servidor perimetral:
  
```powershell
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a>Ejemplo 2

En el siguiente ejemplo se muestra el certificado establecido para el servidor de mediación:
  
```powershell
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

Durante la implementación o al modificar la topología, deberá especificar la ruta del certificado del servidor perimetral y, opcionalmente, la del servidor de mediación. El certificado del servidor de mediación se requiere si TLS se usa entre las puertas de enlace y el servidor de mediación. Para cambiar la ruta de acceso, use el cmdlet Set-CcExternalCertificateFilePath.
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Requerida.**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|Destino   <br/> |Opcional  <br/> | System.Management.Automation.SwitchParameter <br/> |El tipo de ruta de archivo que se ha solicitado. Los tipos incluyen:  <br/> EdgeServer (predeterminado)  <br/> MediationServer  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

El cmdlet Get-CcExternalCertificateFilePath no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

El comando devuelve una ruta de archivo.
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)
  

