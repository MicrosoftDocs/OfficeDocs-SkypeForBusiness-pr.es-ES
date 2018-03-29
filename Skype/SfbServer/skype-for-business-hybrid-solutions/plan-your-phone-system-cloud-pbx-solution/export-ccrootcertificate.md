---
title: CcRootCertificate de exportación
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: El cmdlet Export-CcRootCertificate exporta el certificado de la CA raíz en un archivo local del servidor host de Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: 9af3701fd89cf881b4f966c2b00500ad4e55bc9b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="export-ccrootcertificate"></a>CcRootCertificate de exportación
 
El cmdlet Export-CcRootCertificate exporta el certificado de la CA raíz en un archivo local del servidor host de Skype Empresarial Cloud Connector Edition. 
  
```
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

El siguiente ejemplo establece el parámetro Path como una ruta de acceso del directorio, no como una ruta de archivo. Genera el archivo c:\test\CCERootCertificates.p7b.
  
```
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

El cmdlet Export-CcRootCertificate le permite guardar los certificados raíz e intermedio en una ruta de archivo. Esto puede ser útil en situaciones de recuperación ante desastres. 
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Requerida.**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
| Ruta de acceso  <br/> | Obligatorio  <br/> |System.String  <br/> |Ruta de archivo donde se almacenará el certificado.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Export-CcRootCertificate no acepta entradas canalizadas. 
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

Ninguno
  

