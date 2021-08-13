---
title: Update-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: El cmdlet Update-CcCACertificate renueva el Skype for Business Edición de conector de nube ca raíz que está cerca de expirar o que ya ha expirado.
ms.openlocfilehash: 640ca982cd005e9805d7214212d847edcc6856456b6995fe1ae689778da58f61
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344539"
---
# <a name="update-cccacertificate"></a>Update-CcCACertificate
 
El cmdlet Update-CcCACertificate renueva el Skype for Business Edición de conector de nube ca raíz que está cerca de expirar o que ya ha expirado. 
  
```powershell
Update-CcCACertificate
```

## <a name="parameters"></a>Parámetros

Ninguno.
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se renueva el certificado de ca raíz: 
  
```powershell
Update-CcCACertificate 
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

El certificado de CA raíz de Cloud Connector es válido durante cinco años a partir de la fecha en que se instaló el servicio de entidad de certificación.
  
Si el certificado raíz está cerca de expirar o ya ha expirado, ejecute el cmdlet Update-CcCACertificate para renovar el certificado. Una vez renovado el certificado raíz, el servidor AD, el Almacén de administración central y el servidor perimetral se emitirán automáticamente nuevos certificados.
  
Si hay varios dispositivos en el mismo sitio RTC, ejecute el cmdlet Update-CcCACertificate en todos los dispositivos del mismo sitio RTC.
  
Como último paso, ejecute Export-CcRootCertificate para exportar el certificado raíz a un archivo local en el primer dispositivo y, a continuación, copie e instale el certificado exportado en las puertas de enlace RTC.
  
Este comando reemplaza el cmdlet Renew-CcCACertificate en Cloud Connector 2.0 y versiones posteriores.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Update-CcCACertificate no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno. 
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

