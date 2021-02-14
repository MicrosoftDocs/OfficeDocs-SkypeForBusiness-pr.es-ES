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
description: El Update-CcCACertificate cmdlet renueva el certificado de CA raíz de Skype Empresarial Cloud Connector Edition que está a punto de expirar o que ya ha expirado.
ms.openlocfilehash: 9a99e80e166b7c8624867594fa02243d9d70537e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824124"
---
# <a name="update-cccacertificate"></a>Update-CcCACertificate
 
El Update-CcCACertificate cmdlet renueva el certificado de CA raíz de Skype Empresarial Cloud Connector Edition que está a punto de expirar o que ya ha expirado. 
  
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

El certificado de entidad de certificación raíz de Cloud Connector es válido durante cinco años a partir de la fecha en que se instala el servicio de entidad de certificación.
  
Si el certificado raíz está a punto de expirar o ya ha expirado, ejecute el cmdlet Update-CcCACertificate para renovar el certificado. Una vez renovado el certificado raíz, el servidor de AD, el Almacén de administración central y el servidor perimetral recibirán nuevos certificados automáticamente.
  
Si hay varios dispositivos en el mismo sitio RTC, ejecute el cmdlet Update-CcCACertificate en todos los dispositivos del mismo sitio RTC.
  
Como último paso, ejecute Export-CcRootCertificate para exportar el certificado raíz a un archivo local en el primer dispositivo y, a continuación, copie e instale el certificado exportado en las puertas de enlace RTC.
  
Este comando reemplaza el cmdlet Renew-CcCACertificate en Cloud Connector 2.0 y versiones posteriores.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El Update-CcCACertificate no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno. 
  
## <a name="see-also"></a>Vea también
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

