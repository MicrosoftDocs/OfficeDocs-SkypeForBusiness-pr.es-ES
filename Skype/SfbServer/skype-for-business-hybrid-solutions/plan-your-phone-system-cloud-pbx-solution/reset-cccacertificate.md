---
title: Reset-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: El Reset-CcCACertificate cmdlet reinstala el servidor ad de servicio de entidad de certificación para crear un nuevo certificado de CA raíz.
ms.openlocfilehash: 6a7f377642ca8aa8722933e503a6c0c2f2613544
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824256"
---
# <a name="reset-cccacertificate"></a>Reset-CcCACertificate
 
El Reset-CcCACertificate cmdlet reinstala el servidor ad de servicio de entidad de certificación para crear un nuevo certificado de CA raíz.
  
```powershell
Reset-CcCACertificate
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se vuelve a instalar el servidor ad de servicio de entidad de certificación para crear un nuevo certificado de entidad de certificación raíz:
  
```powershell
Reset-CcCACertificate
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

Si el certificado de ca raíz está en peligro o ya no es seguro, debe actualizar el certificado de ca raíz y todos los certificados emitidos por la CA raíz. El Reset-CcCACertificate revoca todos los certificados, desinstala y reinstala la entidad de certificación y, a continuación, limpia todos los certificados relacionados con el antiguo servicio de entidad de certificación. 
  
Para obtener más información, consulte "Los certificados de entidad de certificación o los certificados internos emitidos a CMS, al servidor de mediación y al servidor perimetral están a punto de expirar o están en peligro" en la solución de problemas de la implementación de Cloud Connector.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El Reset-CcCACertificate no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno.
  
## <a name="see-also"></a>Vea también
<a name="ReturnTypes"> </a>

[Renew-CcCACertificate](renew-cccacertificate.md) Solo la versión 1.4.2
  
[Renew-CcServerCertificate](renew-ccservercertificate.md) Solo la versión 1.4.2
  
[Update-CcCACertificate](update-cccacertificate.md) Versión 2.0 y posteriores
  
[Renew-CcServerCertificate](renew-ccservercertificate.md) Versión 2.0 y posteriores
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

