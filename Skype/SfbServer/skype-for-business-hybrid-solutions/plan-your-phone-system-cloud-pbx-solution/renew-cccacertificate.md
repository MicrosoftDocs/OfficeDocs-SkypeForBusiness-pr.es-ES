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
ms.localizationpriority: medium
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: El cmdlet Renew-CcCACertificate renueva el Skype for Business Edición de conector de nube ca raíz que está cerca de expirar o que ya ha expirado. Este comando se cambió a Update-CcCACertificate cloud connector 2.0 y versiones posteriores.
ms.openlocfilehash: f48839360af0be72279547e1e1f9cbd695c48b39
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624982"
---
# <a name="renew-cccacertificate"></a>Renew-CcCACertificate
 
El cmdlet Renew-CcCACertificate renueva el Skype for Business Edición de conector de nube ca raíz que está cerca de expirar o que ya ha expirado. Este comando se cambió a Update-CcCACertificate cloud connector 2.0 y versiones posteriores.
  
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

El certificado de CA raíz de Cloud Connector es válido durante cinco años a partir de la fecha en que se instaló el servicio de entidad de certificación.
  
Si el certificado raíz está cerca de expirar o ya ha expirado, ejecute el cmdlet Renew-CcCACertificate para renovar el certificado. Una vez renovado el certificado raíz, el servidor AD, el Almacén de administración central y el servidor perimetral se emitirán automáticamente nuevos certificados.
  
Si hay varios dispositivos en el mismo sitio RTC, ejecute el cmdlet Renew-CcCACertificate en todos los dispositivos del mismo sitio RTC.
  
Como último paso, ejecute Export-CcRootCertificate para exportar el certificado raíz a un archivo local en el primer dispositivo y, a continuación, copie e instale el certificado exportado en las puertas de enlace RTC.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Renew-CcCACertificate no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

