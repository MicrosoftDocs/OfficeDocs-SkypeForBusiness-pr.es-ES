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
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: El cmdlet Export-CcRootCertificate exporta el certificado de ca raíz a un archivo local en el servidor host de Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: 2b252eba4688deb790d85b0c3663b09a9e85e7b9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800920"
---
# <a name="export-ccrootcertificate"></a>Export-CcRootCertificate
 
El cmdlet Export-CcRootCertificate exporta el certificado de ca raíz a un archivo local en el servidor host de Skype Empresarial Cloud Connector Edition. 
  
```powershell
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se establece el parámetro Path como una ruta de acceso de directorio, no una ruta de acceso de archivo. Genera el archivo c:\test\CCERootCertificates.p7b.
  
```powershell
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

El Export-CcRootCertificate cmdlet permite guardar los certificados raíz e intermedios en una ruta de acceso de archivo. Esto puede ser útil en caso de un escenario de recuperación ante desastres. 
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Required**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|Path  <br/> |Obligatorio  <br/> |System.String  <br/> |Ruta de acceso del archivo donde se almacenará el certificado.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El Export-CcRootCertificate no acepta entradas canalizadas. 
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Vea también
<a name="ReturnTypes"> </a>

Ninguno
  

