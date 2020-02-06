---
title: Uninstall-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: 'El cmdlet Uninstall-CcAppliance desinstala el dispositivo en ejecución de Skype Empresarial Cloud Connector Edition desde el servidor host. '
ms.openlocfilehash: c92ad5c31e2e254e4f10511835b6cc9f60c7c43c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824144"
---
# <a name="uninstall-ccappliance"></a>Uninstall-CcAppliance
 
El cmdlet Uninstall-CcAppliance desinstala el dispositivo en ejecución de Skype Empresarial Cloud Connector Edition desde el servidor host.  
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el ejemplo siguiente se purgan y desinstalan el dispositivo de conector de nube desde el servidor host:
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a>Ejemplo 2

El siguiente ejemplo purga y fuerza la desinstalación del dispositivo conector de nube en ejecución en el servidor host, incluso si se produjo un error en el proceso de drenaje:
  
```powershell
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a>Ejemplo 3

En el siguiente ejemplo se desinstala la versión de copia de seguridad de un conector de nube sin la confirmación del usuario:
  
```powershell
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

Si está desinstalando la versión de ejecución actual del conector en la nube, los servicios de drenaje se ejecutan primero en el servidor de mediación y en el servidor perimetral para permitir que las llamadas simultáneas finalicen antes de desinstalar las máquinas virtuales. Si va a desinstalar una versión de copia de seguridad, la depuración no se lleva a cabo.
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Requerida.**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
| Version <br/> | Opcional <br/> |System.String  <br/> | La versión del conector de nube que se desinstalará del servidor host. Si no se especifica, desinstale la versión en ejecución actual. <br/> |
|Force  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Si se va a desinstalar la versión en ejecución actual, se intenta depurar los servidores del servidor de mediación y del servidor perimetral antes de desinstalar las máquinas virtuales. Si especifica el conmutador "Force", incluso en caso de error de los servicios de depuración, las máquinas virtuales se desinstalarán. Este parámetro solo se usa para desinstalar la versión en ejecución actual.  <br/> |
|Confirm  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Pida a la confirmación del usuario que desinstale las máquinas virtuales. El valor predeterminado es TRUE.  <br/> |
   
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
  

