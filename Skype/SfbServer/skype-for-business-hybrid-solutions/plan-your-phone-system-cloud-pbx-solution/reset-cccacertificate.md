---
title: Restablecer CcCACertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: El cmdlet Reset-CcCACertificate reinstala el servidor de AD del servicio de entidad de certificación para crear un nuevo certificado de CA raíz.
ms.openlocfilehash: dc86c39e844accc789ba7a3503aa6261d40e5cb2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="reset-cccacertificate"></a>Restablecer CcCACertificate
 
El cmdlet Reset-CcCACertificate reinstala el servidor de AD del servicio de entidad de certificación para crear un nuevo certificado de CA raíz.
  
```
Reset-CcCACertificate
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se reinstala el servidor de AD del servicio de entidad de certificación para crear un nuevo certificado de CA raíz:
  
```
Reset-CcCACertificate
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

Si el certificado de CA raíz está en peligro o ya no es seguro, deberá actualizar este certificado y todos los certificados emitidos por la CA raíz. El cmdlet Reset-CcCACertificate revoca todos los certificados, desinstala y vuelve a instalar la entidad de certificación, y limpia todos los certificados relacionados con el servicio de la entidad de certificación antigua. 
  
Para obtener más información, consulte "Certificado de autoridad de certificados internos certificados emitidos al servidor perimetral, servidor de mediación y CMS cerca de caducidad o se estén en peligro" en solución de problemas de la implementación del conector de la nube.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Reset-CcCACertificate no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno.
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[CcCACertificate renovar](renew-cccacertificate.md) Versión 1.4.2
  
[CcServerCertificate renovar](renew-ccservercertificate.md) Versión 1.4.2
  
[Actualización CcCACertificate](update-cccacertificate.md) Versión 2.0 y versiones posterior
  
[CcServerCertificate renovar](renew-ccservercertificate.md) Versión 2.0 y versiones posterior
  
[CcRootCertificate de exportación](export-ccrootcertificate.md)
  

