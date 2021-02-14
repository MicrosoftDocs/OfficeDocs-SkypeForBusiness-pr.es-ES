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
description: El Stop-CcLogging cmdlet deja de generar el registro de llamadas entrantes y salientes para un dispositivo de Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: 8a012e9b1a94c3698cc61da4326eb0ccbb27bca2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824164"
---
# <a name="stop-cclogging"></a>Stop-CcLogging
 
El Stop-CcLogging cmdlet deja de generar el registro de llamadas entrantes y salientes para un dispositivo de Skype Empresarial Cloud Connector Edition.
  
```powershell
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se detiene la generación del registro de llamadas entrantes y salientes: 
  
```powershell
Stop-CcLogging
```

### <a name="example-2"></a>Ejemplo 2

En el siguiente ejemplo se detiene la generación del registro de llamadas entrantes y salientes y se limpian los archivos de caché:
  
```powershell
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

El Stop-CcLogging cmdlet detiene el registro de llamadas entrantes y salientes en un dispositivo. De forma predeterminada, el registro se detendrá automáticamente después de cuatro horas.
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Required**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
| RemoveCache <br/> | Opcional <br/> | System.Management.Automation.SwitchParameter <br/> |Quita los archivos de caché de registro.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El Stop-CcLogging no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Vea también
<a name="ReturnTypes"> </a>

[Search-CcLog](search-cclog.md)
  
[Start-CcLogging](start-cclogging.md)
  

