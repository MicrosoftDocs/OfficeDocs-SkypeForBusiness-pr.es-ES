---
title: Enter-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: El cmdlet Enter-CcUpdate prepara el servidor host Skype for Business Edición de conector de nube para el proceso de actualización poniéndolo en modo de mantenimiento. El dispositivo detiene inmediatamente todos los servicios, finalizando las llamadas en curso y rechazando las llamadas nuevas.
ms.openlocfilehash: 26f1874ca6c0b92836716d66031945adc864d0ff
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620766"
---
# <a name="enter-ccupdate"></a>Enter-CcUpdate

El cmdlet Enter-CcUpdate prepara el servidor host Skype for Business Edición de conector de nube para el proceso de actualización poniéndolo en modo de mantenimiento. El dispositivo detiene inmediatamente todos los servicios, finalizando las llamadas en curso y rechazando las llamadas nuevas.
  
```powershell
Enter-CcUpdate
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se prepara el dispositivo para el proceso de actualización entrando en modo de mantenimiento:
  
```powershell
Enter-CcUpdate 
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

El cmdlet Enter-CcUpdate impedirá inmediatamente todos los servicios que terminen las llamadas en curso y el dispositivo rechazará las llamadas nuevas, que se transfieren a otros dispositivos de producción. Debe asegurarse de que los dispositivos de producción restantes tienen suficiente capacidad para controlar las llamadas desde el dispositivo que está preparando para actualizar.
  
El modo de mantenimiento es útil si el dispositivo tiene habilitada la actualización automática, por ejemplo, y Microsoft publica una revisión crítica. El modo de mantenimiento también es útil si decide desactivar las actualizaciones automáticas, pero realiza actualizaciones manuales de forma coherente.
  
Después de instalar las actualizaciones, el dispositivo puede volver al modo de producción ejecutando el cmdlet Exit-CcUpdate.
  
> [!NOTE]
> Si decide actualizar manualmente un dispositivo de Cloud Connector, deberá actualizarlo en un plazo de 60 días después de que Microsoft libere la siguiente versión. Microsoft admite la versión publicada anteriormente de Cloud Connector durante 60 días después de publicar la nueva versión 
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Enter-CCUpdate no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno 
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Exit-CcUpdate](exit-ccupdate.md)
  

