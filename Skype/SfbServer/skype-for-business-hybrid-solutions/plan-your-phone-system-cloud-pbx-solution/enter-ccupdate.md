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
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: El cmdlet Enter-CcUpdate prepara el servidor host de la edición Cloud Connector de Skype empresarial para el proceso de actualización al ponerlo en el modo de mantenimiento. El dispositivo detiene inmediatamente todos los servicios, finaliza cualquier llamada en curso y rechaza cualquier otra llamada.
ms.openlocfilehash: 25d2fbc56bd4de6a08985de18c178d5a8f993492
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802180"
---
# <a name="enter-ccupdate"></a>Enter-CcUpdate

El cmdlet Enter-CcUpdate prepara el servidor host de la edición Cloud Connector de Skype empresarial para el proceso de actualización al ponerlo en el modo de mantenimiento. El dispositivo detiene inmediatamente todos los servicios, finaliza cualquier llamada en curso y rechaza cualquier otra llamada.
  
```powershell
Enter-CcUpdate
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se prepara el dispositivo para el proceso de actualización mediante la entrada en el modo de mantenimiento:
  
```powershell
Enter-CcUpdate 
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

El cmdlet Enter-CcUpdate detendrá inmediatamente todos los servicios que finalizan cualquier llamada en curso y el dispositivo rechazará las llamadas nuevas, que se transfieren a otros dispositivos de producción. Debes asegurarte de que el resto de los dispositivos de producción tengan capacidad suficiente para manejar las llamadas desde el dispositivo que estás preparando para actualizar.
  
El modo de mantenimiento es útil si, por ejemplo, el dispositivo tiene habilitada la actualización automática y Microsoft publica una revisión crítica. El modo de mantenimiento también es útil si decide desactivar las actualizaciones automáticas, pero realiza actualizaciones manuales con frecuencia.
  
Después de instalar las actualizaciones, el dispositivo puede volver al modo de producción ejecutando el cmdlet Exit-CcUpdate.
  
> [!NOTE]
> Si decide actualizar manualmente un dispositivo de conector de nube, tendrá que actualizarlo dentro de 60 días después de que Microsoft publique la versión siguiente. Microsoft admite la versión publicada anteriormente del conector en la nube para 60 días después de que se publique la nueva versión. 
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Enter-CCUpdate no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno 
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Exit-CcUpdate](exit-ccupdate.md)
  

