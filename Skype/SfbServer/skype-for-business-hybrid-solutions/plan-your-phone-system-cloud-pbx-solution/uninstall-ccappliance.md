---
title: Uninstall-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: 'El cmdlet Uninstall-CcAppliance desinstala el dispositivo en ejecución de Skype Empresarial Cloud Connector Edition desde el servidor host. '
ms.openlocfilehash: 7b2def71eee17c81b6f178a18d4c248557a0f022
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885651"
---
# <a name="uninstall-ccappliance"></a>Uninstall-CcAppliance
 
El cmdlet Uninstall-CcAppliance desinstala el dispositivo en ejecución de Skype Empresarial Cloud Connector Edition desde el servidor host.  
  
```
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

El siguiente ejemplo se purga y desinstala el dispositivo conector en la nube desde el servidor de host:
  
```
Uninstall-CcAppliance
```

### <a name="example-2"></a>Ejemplo 2

En el ejemplo siguiente se agota y desinstala forzosamente el dispositivo de conector en la nube que se está ejecutando en el servidor de host, incluso si el proceso de vaciado no pudo:
  
```
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a>Ejemplo 3

En el ejemplo siguiente se desinstala una versión de copia de seguridad de conector en la nube sin pedir confirmación del usuario:
  
```
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

Si va a desinstalar la versión actual que se está ejecutando del conector en la nube, servicios de vaciado en primer lugar se ejecutan en el servidor de mediación y el servidor perimetral para permitir que las llamadas simultáneas a fin antes de desinstalar las máquinas virtuales. Si va a desinstalar una versión de copia de seguridad, la depuración no se lleva a cabo.
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Requerida.**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
| Version <br/> | Opcional <br/> |System.String  <br/> | La versión del conector en la nube que se van a desinstalar desde el servidor host. Si no se especifica, desinstale la versión en ejecución actual. <br/> |
|Force  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Si se va a desinstalar la versión en ejecución actual, se intenta depurar los servidores del servidor de mediación y del servidor perimetral antes de desinstalar las máquinas virtuales. Si especifica el conmutador "Force", incluso en caso de error de los servicios de depuración, las máquinas virtuales se desinstalarán. Este parámetro solo se usa para desinstalar la versión en ejecución actual.  <br/> |
|Confirm  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Pedir confirmación del usuario para desinstalar las máquinas virtuales. El valor predeterminado es TRUE.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Uninstall-CcAppliance no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

