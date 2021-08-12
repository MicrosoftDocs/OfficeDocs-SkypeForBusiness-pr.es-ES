---
title: Stop-CcLogging
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
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: El cmdlet Stop-CcLogging deja de generar el registro de llamadas entrantes y salientes para un Skype for Business Edición de conector de nube dispositivo.
ms.openlocfilehash: 7813acf9867829cadaa26d84a0e8a6c33f825ef45b9fca781840a44f94574930
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347565"
---
# <a name="stop-cclogging"></a>Stop-CcLogging
 
El cmdlet Stop-CcLogging deja de generar el registro de llamadas entrantes y salientes para un Skype for Business Edición de conector de nube dispositivo.
  
```powershell
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se deja de generar el registro de llamadas entrantes y salientes: 
  
```powershell
Stop-CcLogging
```

### <a name="example-2"></a>Ejemplo 2

El siguiente ejemplo deja de generar el registro de llamadas entrantes y salientes y limpia los archivos de caché:
  
```powershell
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

El cmdlet Stop-CcLogging detiene el registro de llamadas entrantes y salientes en un dispositivo. De forma predeterminada, el registro se detendrá automáticamente después de cuatro horas.
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Required**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
| RemoveCache <br/> | Opcional <br/> | System.Management.Automation.SwitchParameter <br/> |Quita los archivos de caché de registro.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Stop-CcLogging no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Search-CcLog](search-cclog.md)
  
[Start-CcLogging](start-cclogging.md)
  

