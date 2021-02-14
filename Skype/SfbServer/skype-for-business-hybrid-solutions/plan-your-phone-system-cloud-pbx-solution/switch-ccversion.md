---
title: Switch-CcVersion
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
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: El cmdlet Switch-CcVersion desconecta el dispositivo en ejecución y cambia a un dispositivo recién implementado o de copia de seguridad.
ms.openlocfilehash: 31dbb841caae51de0accedf081fa576ec378044b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824154"
---
# <a name="switch-ccversion"></a>Switch-CcVersion
 
El cmdlet Switch-CcVersion desconecta el dispositivo en ejecución y cambia a un dispositivo recién implementado o de copia de seguridad. 
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se purgan los servicios del dispositivo en ejecución actual y, a continuación, se cambia a un dispositivo recién implementado o de copia de seguridad:
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a>Ejemplo 2

En el siguiente ejemplo se purgan los servicios del dispositivo en ejecución actual y se detienen los servicios por la fuerza si se produce un error al purgar los servicios. A continuación, el comando cambia a un dispositivo recién implementado o de copia de seguridad:
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

El cmdlet Switch-CcVersion purga los servicios de Cloud Connector en el servidor de mediación y el servidor perimetral. Todas las llamadas en ejecución se completarán, pero el dispositivo rechazará las llamadas nuevas. Después de purgar, el cmdlet desconecta el dispositivo en ejecución de las redes corporativas e Internet, desactiva todas las máquinas virtuales que pertenecen al dispositivo y, a continuación, conecta el dispositivo de copia de seguridad a las redes corporativas e Internet.
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Required**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
| Force <br/> | Opcional <br/> |System.Management.Automation.SwitchParameter  <br/> | Detiene los servicios por la fuerza si se produce un error al purgar los servicios. <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Vea también
<a name="ReturnTypes"> </a>

Ninguno
  

