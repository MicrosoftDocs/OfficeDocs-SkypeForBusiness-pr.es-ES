---
title: Conmutador CcVersion
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: El cmdlet CcVersion de Switch desconecta el dispositivo ejecutando y cambia a un dispositivo recién implementado o copia de seguridad.
ms.openlocfilehash: 651dad80ef5c9907eb6c182527b646da7aa5acc8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="switch-ccversion"></a>Conmutador CcVersion
 
El cmdlet CcVersion de Switch desconecta el dispositivo ejecutando y cambia a un dispositivo recién implementado o copia de seguridad. 
  
```
Switch-CcVersion [-Force]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el ejemplo siguiente se agota los servicios del equipo de ejecución actual y, a continuación, cambia a un dispositivo recién implementado o copia de seguridad:
  
```
Switch-CcVersion
```

### <a name="example-2"></a>Ejemplo 2

En el ejemplo siguiente se purgan los servicios del equipo de ejecución actual y detiene los servicios forzosamente si no purga los servicios. A continuación, cambia el comando a un dispositivo recién implementado o copia de seguridad:
  
```
Switch-CcVersion -Force
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

El cmdlet CcVersion de conmutador purga los servicios de nube de conector en el servidor de mediación y servidor perimetral. Todas las llamadas de ejecución se completará, pero el dispositivo rechazará todas las llamadas nuevas. Tras el drenaje, el cmdlet desconecta el dispositivo ejecución de corporativa y redes de Internet, desactiva todas las máquinas virtuales que pertenecen al dispositivo y, a continuación, conecta el dispositivo de copia de seguridad a la empresa y las redes de Internet.
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Requerida.**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
| Force <br/> | Opcional <br/> |System.Management.Automation.SwitchParameter  <br/> | Detiene los servicios forzosamente si purga los servicios se produce un error. <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

Ninguno
  

