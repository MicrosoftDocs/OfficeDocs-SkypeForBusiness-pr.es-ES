---
title: Backup-CcCertificationAuthority
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: El cmdlet Backup-CcCertificationAuthority copia de seguridad del servicio Skype for Business Edición de conector de nube entidad de certificación en un archivo y lo guarda en la carpeta ca en el directorio de recurso compartido del sitio.
ms.openlocfilehash: f7803a1c773ca3561b13ef5a263002cc4b8e049a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582534"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority
 
El cmdlet Backup-CcCertificationAuthority copia de seguridad del servicio Skype for Business Edición de conector de nube entidad de certificación en un archivo y lo guarda en la carpeta ca en el directorio de recurso compartido del sitio.
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se hace una copia de seguridad del servicio de entidad de certificación en un archivo y se guarda en la carpeta ca en el directorio de recurso compartido del sitio:
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

La copia de seguridad de la entidad de certificación puede ser útil si tiene previsto volver a implementar un dispositivo de Cloud Connector con el mismo certificado en caso de desastre o si desea mover el dispositivo al nuevo hardware. El comando guarda la copia del servicio de entidad de certificación de Cloud Connector del servidor AD en " \<SiteRootDirectory\> \CA\SfB CCE Root.p12".
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Backup-CcCertificationAuthority no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  

