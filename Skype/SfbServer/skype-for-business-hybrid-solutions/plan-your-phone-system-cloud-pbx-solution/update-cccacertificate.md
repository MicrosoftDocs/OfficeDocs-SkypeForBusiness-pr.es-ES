---
title: Actualización CcCACertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: El cmdlet Update-CcCACertificate renueva el Skype para el certificado de CA raíz de conector de nube Business Edition que está cerca de caducidad o ya expiró.
ms.openlocfilehash: f23298f1be30ab96b3e77ff0625ff6e3b419e111
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="update-cccacertificate"></a>Actualización CcCACertificate
 
El cmdlet Update-CcCACertificate renueva el Skype para el certificado de CA raíz de conector de nube Business Edition que está cerca de caducidad o ya expiró. 
  
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
  
Si el certificado raíz está cerca de caducidad o ya expiró, ejecute el cmdlet Update-CcCACertificate para renovar el certificado. Después de la renovación del certificado raíz, se emitirán nuevos certificados automáticamente para el servidor de AD, el almacén de administración central y el servidor perimetral.
  
Si hay varios dispositivos en el mismo sitio de RTC, ejecute el cmdlet Update-CcCACertificate en todos los equipos del mismo sitio PSTN.
  
Como último paso, ejecute Export-CcRootCertificate para exportar el certificado raíz a un archivo local en el primer dispositivo y después copie e instale el certificado exportado a sus puertas de enlace RTC.
  
Este comando reemplaza el cmdlet renovar CcCACertificate en nube conector 2.0 y versiones posteriores.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Update-CcCACertificate no acepta entrada canalizada.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno. 
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Restablecer CcCACertificate](reset-cccacertificate.md)
  
[CcServerCertificate renovar](renew-ccservercertificate.md)
  
[CcRootCertificate de exportación](export-ccrootcertificate.md)
  

