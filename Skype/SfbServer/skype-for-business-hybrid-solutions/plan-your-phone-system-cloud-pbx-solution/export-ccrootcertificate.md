---
title: Export-CcRootCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: El cmdlet Export-CcRootCertificate exporta el certificado de ca raíz a un archivo local en el Skype for Business Edición de conector de nube host.
ms.openlocfilehash: e00041088af39bf6f11abd5309ff293bd37bf38f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625002"
---
# <a name="export-ccrootcertificate"></a>Export-CcRootCertificate
 
El cmdlet Export-CcRootCertificate exporta el certificado de ca raíz a un archivo local en el Skype for Business Edición de conector de nube host. 
  
```powershell
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el ejemplo siguiente se establece el parámetro Path como una ruta de acceso de directorio, no como una ruta de acceso de archivo. Genera el archivo c:\test\CCERootCertificates.p7b.
  
```powershell
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

El cmdlet Export-CcRootCertificate permite guardar los certificados raíz e intermedios en una ruta de acceso de archivo. Esto puede ser útil en caso de un escenario de recuperación ante desastres. 
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Required**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|Ruta de acceso  <br/> |Obligatorio  <br/> |System.String  <br/> |Ruta de acceso de archivo donde se almacenará el certificado.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Export-CcRootCertificate no acepta entradas canalizadas. 
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

Ninguno
  

