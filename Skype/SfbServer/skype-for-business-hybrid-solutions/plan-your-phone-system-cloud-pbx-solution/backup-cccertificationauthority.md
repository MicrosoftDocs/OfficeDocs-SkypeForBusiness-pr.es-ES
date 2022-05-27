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
description: El cmdlet Backup-CcCertificationAuthority realiza una copia de seguridad del servicio de entidad de certificación Skype for Business Edición de conector de nube en un archivo y lo guarda en la carpeta ca en el directorio del recurso compartido de sitio.
ms.openlocfilehash: 4dc67fa9e1b4a9a52b3e447b09d91a74704be690
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675462"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority

El cmdlet Backup-CcCertificationAuthority hace una copia de seguridad del servicio de entidad de certificación de Skype for Business Edición de conector de nube en un archivo. El cmdlet también lo guarda en la carpeta ca en el directorio del recurso compartido de sitio.

```powershell
Backup-CcCertificationAuthority
```

## <a name="parameters"></a>Parámetros

Ninguno

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el ejemplo siguiente se realiza una copia de seguridad del servicio de entidad de certificación en un archivo y se guarda en la carpeta ca en el directorio del recurso compartido de sitio:

```powershell
Backup-CcCertificationAuthority
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

La copia de seguridad de la entidad de certificación puede ser útil si planea volver a implementar un dispositivo de Cloud Connector con el mismo certificado. Por ejemplo:

- Recuperación ante desastres.
- Mueva el dispositivo al nuevo hardware.

El comando guarda la copia del servicio de entidad de certificación de Cloud Connector desde el servidor de AD a `"<SiteRootDirectory>\CA\SfB CCE Root.p12"`.

## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Backup-CcCertificationAuthority no acepta entradas canalizadas.

## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno

## <a name="see-also"></a>Vea también
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  