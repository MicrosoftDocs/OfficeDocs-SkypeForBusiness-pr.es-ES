---
title: Remove-CcCertificationAuthorityFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: El cmdlet Remove-CcCertificationAuthorityFile elimina el archivo de copia de seguridad del servicio de entidad de certificación en la carpeta ca en el directorio de recurso compartido del sitio para Skype for Business Edición de conector de nube.
ms.openlocfilehash: aaff21023a63e8933235f4c462c1152339381ca0d9571ded57f6b43742679624
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288781"
---
# <a name="remove-cccertificationauthorityfile"></a>Remove-CcCertificationAuthorityFile
 
El cmdlet Remove-CcCertificationAuthorityFile quita el archivo de copia de seguridad del servicio de entidad de certificación " &lt; SiteRootDirectory &gt; \CA\SfB CCE Root.p12" en la carpeta CA en el directorio de recurso compartido del sitio para Skype for Business Edición de conector de nube. 
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se quita el archivo de copia de seguridad del servicio de entidad de certificación " &lt; SiteRootDirectory &gt; \CA\SfB CCE Root.p12" en la carpeta CA en el directorio de recurso compartido de sitios:
  
```powershell
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
  

