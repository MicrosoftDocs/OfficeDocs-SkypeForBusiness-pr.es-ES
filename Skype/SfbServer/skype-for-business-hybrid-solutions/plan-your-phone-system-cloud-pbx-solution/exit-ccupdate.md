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
description: El cmdlet Exit-CcUpdate sale del modo de mantenimiento de actualización en el Skype for Business Edición de conector de nube host.
ms.openlocfilehash: d55004f071caa67492d5368e36007d9c3c307b90aabbc33d79d1feeb4aa37356
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288846"
---
# <a name="exit-ccupdate"></a>Exit-CcUpdate
 
El cmdlet Exit-CcUpdate sale del modo de mantenimiento de actualización en el Skype for Business Edición de conector de nube host. 
  
Este cmdlet se aplica a Skype for Business Edición de conector de nube 1.4.1, 1.4.2. 
  
```powershell
Exit-CcUpdate
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

El siguiente comando coloca el dispositivo en el que vuelve a ejecutarse en modo de producción: 
  
```powershell
Exit-CcUpdate
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

Si tiene dispositivos que ha puesto en modo de mantenimiento especificando el cmdlet Enter-CcUpdate, el cmdlet Exit-CcUpdate los volverá a poner en modo de producción. 
  
Para obtener más información acerca de cómo poner dispositivos en modo de mantenimiento, vea Enter-CcUpdate.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Exit-CcUpdate no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno 
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Enter-CcUpdate](enter-ccupdate.md)
  

