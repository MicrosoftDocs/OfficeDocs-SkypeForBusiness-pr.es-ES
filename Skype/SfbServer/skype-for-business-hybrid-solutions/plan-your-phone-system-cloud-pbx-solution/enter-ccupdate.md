---
title: Escriba-CcUpdate
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: El cmdlet Enter-CcUpdate prepara el servidor host de Skype Empresarial Cloud Connector Edition para el proceso de actualización poniéndolo en modo de mantenimiento. El dispositivo isdrained, es decir, todas las llamadas existentes se completarán, pero las nuevas llamadas se rechazan.
ms.openlocfilehash: f9b789bbd76bd3405617dc170af0695f9cbe94ed
ms.sourcegitcommit: baa4ecf69bdcf499b5b724246f3e9f45c6ca3b7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2018
ms.locfileid: "25450514"
---
# <a name="enter-ccupdate"></a>Escriba-CcUpdate
 
El cmdlet Enter-CcUpdate prepara el servidor host de Skype Empresarial Cloud Connector Edition para el proceso de actualización poniéndolo en modo de mantenimiento. El dispositivo se "vacía", es decir, todas las llamadas existentes se completarán, pero las nuevas llamadas se rechazan. 
  
```
Enter-CcUpdate
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se prepara el dispositivo para el proceso de actualización mediante la entrada en el modo de mantenimiento:
  
```
Enter-CcUpdate 
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

El cmdlet ENTRAR CcUpdate detendrá inmediatamente todos los servicios que terminan las llamadas en curso y el dispositivo rechazará las llamadas nuevo, que se transfieren a otros dispositivos de producción. Deberá asegurarse de que los dispositivos de producción restantes tengan la suficiente capacidad para gestionar las llamadas del dispositivo en el que está preparando la actualización.
  
El modo de mantenimiento es útil si, por ejemplo, el dispositivo tiene habilitada la actualización automática y Microsoft publica una revisión crítica. El modo de mantenimiento también es útil si decide desactivar las actualizaciones automáticas, pero realiza actualizaciones manuales con frecuencia.
  
Después de instalar las actualizaciones, el dispositivo puede regresar al modo de producción con el cmdlet Exit-CcUpdate.
  
> [!NOTE]
> Si decide actualizar manualmente un dispositivo de conector en la nube, debe actualizar dentro de 60 días después de que Microsoft lance la siguiente versión. Microsoft admite la versión publicada anteriormente del conector en la nube para 60 días después de que se publique la nueva versión 
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Enter-CCUpdate no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno 
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Salir CcUpdate](exit-ccupdate.md)
  

