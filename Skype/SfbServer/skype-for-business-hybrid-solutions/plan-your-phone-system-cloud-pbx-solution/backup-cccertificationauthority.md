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
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: El cmdlet Backup-CcCertificationAuthority copia de seguridad del servicio de entidad de certificación de Skype Empresarial Cloud Connector Edition en un archivo y lo guarda en la carpeta ca en el directorio del recurso compartido de sitios.
ms.openlocfilehash: 4e12b2349f5834866fc69442fb2947425416fe23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803810"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority
 
El cmdlet Backup-CcCertificationAuthority copia de seguridad del servicio de entidad de certificación de Skype Empresarial Cloud Connector Edition en un archivo y lo guarda en la carpeta ca en el directorio del recurso compartido de sitios.
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se hace una copia de seguridad del servicio de entidad de certificación en un archivo y se guarda en la carpeta ca del directorio de recurso compartido de sitios:
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

La copia de seguridad de la entidad de certificación puede ser útil si tiene previsto volver a implementar un dispositivo de Cloud Connector con el mismo certificado en caso de desastre o si desea mover el dispositivo a un nuevo hardware. El comando guarda la copia del servicio de entidad de certificación de Cloud Connector del servidor de AD en \< "SiteRootDirectory \> \CA\SfB CCE Root.p12".
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El Backup-CcCertificationAuthority no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Vea también
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  

