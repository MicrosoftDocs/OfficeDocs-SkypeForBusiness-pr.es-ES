---
title: Set-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: El cmdlet Set-CcApplianceDirectory establece el directorio de trabajo en el Skype for Business Edición de conector de nube host. Todos los archivos de implementación se almacenan en este directorio.
ms.openlocfilehash: 8ca6b8b8e175058e5f19c86a9dd1c6e0cf8a43ab6ef7a439eee4e09b5430f6a2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306601"
---
# <a name="set-ccappliancedirectory"></a>Set-CcApplianceDirectory
 
El cmdlet Set-CcApplianceDirectory establece el directorio de trabajo en el Skype for Business Edición de conector de nube host. Todos los archivos de implementación se almacenan en este directorio.
  
```powershell
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el ejemplo siguiente se establece el directorio de trabajo en el servidor host en c:\cloudconnector\applianceroot:
  
```powershell
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a>Parámetros
<a name="Examples"> </a>

|**Parámetro**|**Required**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
| Path <br/> | Obligatorio <br/> |System.String  <br/> | Especifica la ruta de acceso donde se almacenan todos los archivos de implementación. <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Set-CcApplianceDirectory no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

Ninguno
  

