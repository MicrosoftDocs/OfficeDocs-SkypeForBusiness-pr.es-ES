---
title: Renew-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: El Renew-CcCACertificate cmdlet renueva el certificado de CA raíz de Skype Empresarial Cloud Connector Edition que está a punto de expirar o que ya ha expirado. Este comando se cambió a Update-CcCACertificate cloud connector 2.0 y versiones posteriores.
ms.openlocfilehash: e92709cd1da0ffccd2b356000dbd2345ba56a1d9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824276"
---
# <a name="renew-cccacertificate"></a>Renew-CcCACertificate
 
El Renew-CcCACertificate cmdlet renueva el certificado de CA raíz de Skype Empresarial Cloud Connector Edition que está a punto de expirar o que ya ha expirado. Este comando se cambió a Update-CcCACertificate cloud connector 2.0 y versiones posteriores.
  
```powershell
Renew-CcCACertificate
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se renueva el certificado de ca raíz: 
  
```powershell
Renew-CcCACertificate 
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

El certificado de entidad de certificación raíz de Cloud Connector es válido durante cinco años a partir de la fecha en que se instala el servicio de entidad de certificación.
  
Si el certificado raíz está a punto de expirar o ya ha expirado, ejecute el cmdlet Renew-CcCACertificate para renovar el certificado. Una vez renovado el certificado raíz, el servidor de AD, el Almacén de administración central y el servidor perimetral recibirán nuevos certificados automáticamente.
  
Si hay varios dispositivos en el mismo sitio RTC, ejecute el cmdlet Renew-CcCACertificate en todos los dispositivos del mismo sitio RTC.
  
Como último paso, ejecute Export-CcRootCertificate para exportar el certificado raíz a un archivo local en el primer dispositivo y, a continuación, copie e instale el certificado exportado en las puertas de enlace RTC.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El Renew-CcCACertificate no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Vea también
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

