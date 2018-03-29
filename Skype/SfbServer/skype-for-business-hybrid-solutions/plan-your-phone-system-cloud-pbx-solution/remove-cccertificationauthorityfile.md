---
title: Quitar CcCertificationAuthorityFile
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: El cmdlet Remove-CcCertificationAuthorityFile quita el archivo de copia de seguridad de servicio de autoridad de certificación en la carpeta de la entidad emisora de certificados en el directorio de recurso compartido del sitio de Skype para conector de nube Business Edition.
ms.openlocfilehash: 0cc2470d6ee9312646feb3d459d6fb7a4c2bb30b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="remove-cccertificationauthorityfile"></a>Quitar CcCertificationAuthorityFile
 
El cmdlet Remove-CcCertificationAuthorityFile quita el archivo de copia de seguridad de servicio de autoridad de certificación "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" en la carpeta de la entidad emisora de certificados en el directorio de recurso compartido del sitio de Skype para Business Connector de nube Edition. 
  
```
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

El ejemplo siguiente quita el archivo de copia de seguridad de servicio de autoridad de certificación "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" en la carpeta de la entidad emisora de certificados en el directorio de recurso compartido del sitio:
  
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

[Copia de seguridad CcCertificationAuthority](backup-cccertificationauthority.md)
  

