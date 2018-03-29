---
title: Salir CcUpdate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: 'El cmdlet Exit-CcUpdate sale del modo de mantenimiento en el servidor host de Skype Empresarial Cloud Connector Edition. '
ms.openlocfilehash: f7b913fd6aaa77a18df66fd86a36d5d4838f69d4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="exit-ccupdate"></a>Salir CcUpdate
 
El cmdlet Exit-CcUpdate sale del modo de mantenimiento en el servidor host de Skype Empresarial Cloud Connector Edition.  
  
Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2. 
  
```
Exit-CcUpdate
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

El siguiente comando vuelve a poner el dispositivo en el que se ejecuta en modo de producción:  
  
```
Exit-CcUpdate
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

Si tiene dispositivos que ha puesto en modo de mantenimiento mediante el cmdlet Enter-CcUpdate, el cmdlet Exit-CcUpdate los volverá a poner en modo de producción.  
  
Para obtener más información sobre cómo poner los dispositivos en modo de mantenimiento, vea Enter-CcUpdate.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Exit-CcUpdate no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno 
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Escriba-CcUpdate](enter-ccupdate.md)
  

