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
localization_priority: Normal
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: El cmdlet Reset-CcCACertificate reinstala el servidor de AD del servicio de entidad de certificación para crear un nuevo certificado de CA raíz.
ms.openlocfilehash: 50c3b1afc29503b2b292ce578ea01b03aeeba368
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003260"
---
# <a name="reset-cccacertificate"></a>Reset-CcCACertificate
 
El cmdlet Reset-CcCACertificate reinstala el servidor de AD del servicio de entidad de certificación para crear un nuevo certificado de CA raíz.
  
```powershell
Reset-CcCACertificate
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se reinstala el servidor de AD del servicio de entidad de certificación para crear un nuevo certificado de CA raíz:
  
```powershell
Reset-CcCACertificate
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

Si el certificado de CA raíz está en peligro o ya no es seguro, deberá actualizar este certificado y todos los certificados emitidos por la CA raíz. El cmdlet Reset-CcCACertificate revoca todos los certificados, desinstala y vuelve a instalar la entidad de certificación, y limpia todos los certificados relacionados con el servicio de la entidad de certificación antigua. 
  
Para obtener más información, consulte "los certificados de la entidad emisora de certificados o los certificados internos emitidos para CMS, servidor de mediación y servidor perimetral están cerca de la fecha de expiración o se han visto comprometidos" en solucionar problemas de implementación en la nube.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Reset-CcCACertificate no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno.
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Renovar-CcCACertificate](renew-cccacertificate.md) Versión 1.4.2
  
[Renovar-CcServerCertificate](renew-ccservercertificate.md) Versión 1.4.2
  
[Update-CcCACertificate](update-cccacertificate.md) Versión 2,0 y posteriores
  
[Renovar-CcServerCertificate](renew-ccservercertificate.md) Versión 2,0 y posteriores
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

