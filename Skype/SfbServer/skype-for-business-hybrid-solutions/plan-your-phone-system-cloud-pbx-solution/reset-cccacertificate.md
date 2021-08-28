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
ms.localizationpriority: medium
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: El cmdlet Reset-CcCACertificate reinstala el servidor AD del servicio de entidad de certificación para crear un nuevo certificado de CA raíz.
ms.openlocfilehash: 21f62724f74504216bcd38f5498b3a7068722512
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624972"
---
# <a name="reset-cccacertificate"></a>Reset-CcCACertificate
 
El cmdlet Reset-CcCACertificate reinstala el servidor AD del servicio de entidad de certificación para crear un nuevo certificado de CA raíz.
  
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

Si el certificado de ca raíz está en peligro o ya no es seguro, debe actualizar el certificado de ca raíz y todos los certificados emitidos por la CA raíz. El cmdlet Reset-CcCACertificate revoca todos los certificados, desinstala y reinstala la entidad de certificación y, a continuación, limpia todos los certificados relacionados con el servicio de entidad de certificación anterior. 
  
Para obtener más información, vea "Certificados de entidad de certificación o certificados internos emitidos a CMS, servidor de mediación y servidor perimetral están a punto de expirar o están en peligro" en Troubleshooting your Cloud Connector deployment.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Reset-CcCACertificate no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno.
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Renew-CcCACertificate](renew-cccacertificate.md) Solo versión 1.4.2
  
[Renew-CcServerCertificate](renew-ccservercertificate.md) Solo versión 1.4.2
  
[Update-CcCACertificate](update-cccacertificate.md) Versión 2.0 y posterior
  
[Renew-CcServerCertificate](renew-ccservercertificate.md) Versión 2.0 y posterior
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

