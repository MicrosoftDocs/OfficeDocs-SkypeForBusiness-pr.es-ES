---
title: Exit-CcUpdate
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
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: El Exit-CcUpdate cmdlet sale del modo de mantenimiento de actualización en el servidor host de Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: 315d6b7dccb6708901128bf8faa29a60f712e833
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801770"
---
# <a name="exit-ccupdate"></a>Exit-CcUpdate
 
El Exit-CcUpdate cmdlet sale del modo de mantenimiento de actualización en el servidor host de Skype Empresarial Cloud Connector Edition. 
  
Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2. 
  
```powershell
Exit-CcUpdate
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

El siguiente comando coloca el dispositivo en el que se ejecuta de nuevo en modo de producción: 
  
```powershell
Exit-CcUpdate
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

Si tiene dispositivos que ha puesto en modo de mantenimiento especificando el cmdlet Enter-CcUpdate, el cmdlet Exit-CcUpdate los volverá a poner en modo de producción. 
  
Para obtener más información acerca de cómo poner dispositivos en modo de mantenimiento, vea Enter-CcUpdate.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El Exit-CcUpdate no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno 
  
## <a name="see-also"></a>Vea también
<a name="ReturnTypes"> </a>

[Enter-CcUpdate](enter-ccupdate.md)
  

