---
title: Remove-CcCertificationAuthorityFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: El cmdlet Remove-CcCertificationAuthorityFile quita el archivo de copia de seguridad del servicio de entidad de certificación en la carpeta de la entidad emisora de certificados en el directorio de recurso compartido del sitio de Skype para Business Edition de conector en la nube.
ms.openlocfilehash: 52f3dc8642b9f3177b215b9cd102bbd50cd22fea
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899627"
---
# <a name="remove-cccertificationauthorityfile"></a>Remove-CcCertificationAuthorityFile
 
El cmdlet Remove-CcCertificationAuthorityFile quita el archivo de copia de seguridad del servicio de autoridad de certificación "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" en la carpeta de la entidad emisora de certificados en el directorio de recurso compartido del sitio de Skype para la nube de Business Connector Edition. 
  
```
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el ejemplo siguiente se quita el archivo de copia de seguridad del servicio de autoridad de certificación "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" en la carpeta de la entidad emisora de certificados en el directorio de recurso compartido de sitio:
  
```
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Remove-CcCertificationAuthorityFile no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Backup-CcCertificationAuthority](backup-cccertificationauthority.md)
  

