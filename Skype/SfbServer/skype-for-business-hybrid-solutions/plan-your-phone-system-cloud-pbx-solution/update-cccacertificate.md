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
localization_priority: Normal
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: El cmdlet Update-CcCACertificate renueva el certificado de la entidad emisora raíz de Skype empresarial Cloud Connector Edition que está cerca de la fecha de expiración o ya ha expirado.
ms.openlocfilehash: e32b910d07aa4f2370af72d0a04bb939b80b3034
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286848"
---
# <a name="update-cccacertificate"></a>Update-CcCACertificate
 
El cmdlet Update-CcCACertificate renueva el certificado de la entidad emisora raíz de Skype empresarial Cloud Connector Edition que está cerca de la fecha de expiración o ya ha expirado. 
  
```
Update-CcCACertificate
```

## <a name="parameters"></a>Parámetros

Ninguno.
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se renueva el certificado de CA raíz:  
  
```
Update-CcCACertificate 
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

El certificado de CA raíz de Cloud Connector es válido durante cinco años a partir de la fecha en que se instaló el servicio de entidad de certificación.
  
Si el certificado raíz está cerca o expirado, ejecute el cmdlet Update-CcCACertificate para renovar el certificado. Después de la renovación del certificado raíz, se emitirán nuevos certificados automáticamente para el servidor de AD, el almacén de administración central y el servidor perimetral.
  
Si hay varios dispositivos en el mismo sitio de la RTC, ejecute el cmdlet Update-CcCACertificate en todos los dispositivos del mismo sitio de la RTC.
  
Como último paso, ejecute Export-CcRootCertificate para exportar el certificado raíz a un archivo local en el primer dispositivo y después copie e instale el certificado exportado a sus puertas de enlace RTC.
  
Este comando reemplaza el cmdlet Renew-CcCACertificate en el conector en la nube 2,0 y versiones posteriores.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Update-CcCACertificate no acepta la entrada canalizada.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno. 
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

