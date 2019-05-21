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
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: El cmdlet Backup-CcCertificationAuthority crea una copia de seguridad del servicio de la entidad de certificación de Skype Empresarial Cloud Connector Edition en un archivo y lo guarda en la carpeta de la entidad de certificación en el directorio de recursos compartidos del sitio.
ms.openlocfilehash: 463aab2516deec5b47e549aec67bcba6a0a80bc0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294421"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority
 
El cmdlet Backup-CcCertificationAuthority crea una copia de seguridad del servicio de la entidad de certificación de Skype Empresarial Cloud Connector Edition en un archivo y lo guarda en la carpeta de la entidad de certificación en el directorio de recursos compartidos del sitio.
  
```
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se crea una copia de seguridad del servicio de la entidad de certificación en un archivo y se guarda en la carpeta de la entidad de certificación en el directorio de recursos compartidos del sitio:
  
```
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

La copia de seguridad de la entidad emisora de certificados puede ser útil si tiene previsto volver a implementar un dispositivo de conector de nube con el mismo certificado en caso de que se produzca un desastre o si desea mover el dispositivo a nuevo hardware. El comando guarda la copia del servicio de autoridad de certificación del conector de nube desde el servidor\<de\>ad en "SiteRootDirectory \CA\SfB CCE root. p12".
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Backup-CcCertificationAuthority no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  

