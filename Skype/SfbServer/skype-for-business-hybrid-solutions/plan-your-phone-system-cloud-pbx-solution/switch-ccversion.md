---
title: Switch-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: El cmdlet de modificador CcVersion desconecta el dispositivo que se está ejecutando y cambia a un dispositivo recién implementado o copia de seguridad.
ms.openlocfilehash: 73ae9b4f93a2488dea29f3271565ac3d25759fd1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30872862"
---
# <a name="switch-ccversion"></a>Switch-CcVersion
 
El cmdlet de modificador CcVersion desconecta el dispositivo que se está ejecutando y cambia a un dispositivo recién implementado o copia de seguridad. 
  
```
Switch-CcVersion [-Force]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se purga los servicios de la aplicación actual que se está ejecutando y, a continuación, se pasa a un dispositivo recién implementado o copia de seguridad:
  
```
Switch-CcVersion
```

### <a name="example-2"></a>Ejemplo 2

En el ejemplo siguiente se purga los servicios de la aplicación actual que se está ejecutando y detiene los servicios forzosamente si purga de los servicios se produce un error. A continuación, cambia el comando a un dispositivo recién implementado o copia de seguridad:
  
```
Switch-CcVersion -Force
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

El cmdlet de modificador CcVersion purga los servicios del conector de nube en el servidor de mediación y el servidor perimetral. Se completará todas las llamadas que se está ejecutando, pero el dispositivo rechazará las llamadas nuevo. Después de purga, el cmdlet desconecta el dispositivo que se está ejecutando desde la corporativa y las redes de Internet, desactiva todas las máquinas virtuales que pertenecen al dispositivo y, a continuación, conecta el dispositivo de copia de seguridad a la empresa y las redes de Internet.
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Requerida.**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
| Force <br/> | Opcional <br/> |System.Management.Automation.SwitchParameter  <br/> | Detiene los servicios forzosamente si purga de los servicios se produce un error. <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno 
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

Ninguno
  

