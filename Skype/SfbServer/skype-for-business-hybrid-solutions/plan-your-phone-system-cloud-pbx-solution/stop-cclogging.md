---
title: Stop-CcLogging
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: El cmdlet Stop-CcLogging detiene la generación del registro de llamadas entrantes y salientes de un dispositivo de Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: eaccde49421cd22e32b23b89d8b5ea42dd073912
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32250635"
---
# <a name="stop-cclogging"></a>Stop-CcLogging
 
El cmdlet Stop-CcLogging detiene la generación del registro de llamadas entrantes y salientes de un dispositivo de Skype Empresarial Cloud Connector Edition.
  
```
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se detiene la generación del registro de llamadas entrantes y salientes:  
  
```
Stop-CcLogging
```

### <a name="example-2"></a>Ejemplo 2

En el siguiente ejemplo se detiene la generación del registro de llamadas entrantes y salientes, y se limpian los archivos caché:
  
```
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

El cmdlet Stop-CcLogging detiene el registro de llamadas entrantes y salientes en un dispositivo. De manera predeterminada, el registro se detendrá automáticamente después de cuatro horas.
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Requerida.**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
| RemoveCache <br/> | Opcional <br/> | System.Management.Automation.SwitchParameter <br/> |Elimina los archivos caché del registro.  <br/> |
   
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
  

