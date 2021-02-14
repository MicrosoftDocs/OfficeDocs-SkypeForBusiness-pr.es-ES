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
description: El cmdlet Remove-CcCertificationAuthorityFile quita el archivo de copia de seguridad del servicio de entidad de certificación en la carpeta ca en el directorio de recursos compartidos del sitio para Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: 49a8f0f313b4153288ebdf037a41dc92f30e60d6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824296"
---
# <a name="remove-cccertificationauthorityfile"></a>Remove-CcCertificationAuthorityFile
 
El cmdlet Remove-CcCertificationAuthorityFile quita el archivo de copia de seguridad del servicio de entidad de certificación " &lt; SiteRootDirectory &gt; \CA\SfB CCE Root.p12" en la carpeta ca en el directorio de recursos compartidos del sitio para Skype Empresarial Cloud Connector Edition. 
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se quita el archivo de copia de seguridad del servicio de entidad de certificación " &lt; SiteRootDirectory &gt; \CA\SfB CCE Root.p12" en la carpeta ca en el directorio de recurso compartido de sitios:
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El Remove-CcCertificationAuthorityFile no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Vea también
<a name="ReturnTypes"> </a>

[Backup-CcCertificationAuthority](backup-cccertificationauthority.md)
  

