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
description: El cmdlet Uninstall-CcAppliance desinstala el dispositivo de Skype Empresarial Cloud Connector Edition en ejecución del servidor host.
ms.openlocfilehash: c92ad5c31e2e254e4f10511835b6cc9f60c7c43c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824144"
---
# <a name="uninstall-ccappliance"></a>Uninstall-CcAppliance
 
El cmdlet Uninstall-CcAppliance desinstala el dispositivo de Skype Empresarial Cloud Connector Edition en ejecución del servidor host. 
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se purga y desinstala el dispositivo de Cloud Connector del servidor host:
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a>Ejemplo 2

En el siguiente ejemplo se purga y se desinstala por la fuerza el dispositivo de Cloud Connector en ejecución en el servidor host, incluso si se ha fallado en el proceso de purga:
  
```powershell
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a>Ejemplo 3

En el siguiente ejemplo se desinstala una versión de copia de seguridad de Cloud Connector sin la confirmación del usuario:
  
```powershell
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

Si va a desinstalar la versión en ejecución actual de Cloud Connector, los servicios de purga se ejecutan primero en el servidor de mediación y en el servidor perimetral para permitir que las llamadas simultáneas finalicen antes de desinstalar las máquinas virtuales. Si va a desinstalar una versión de copia de seguridad, no se realizará la purga.
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Required**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
| Versión <br/> | Opcional <br/> |System.String  <br/> | La versión de Cloud Connector que se desinstalará del servidor host. Si no se especifica, desinstale la versión en ejecución actual. <br/> |
|Force  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Si desinstala la versión en ejecución actual, intente purgar los servidores del servidor de mediación y del servidor perimetral antes de desinstalar las máquinas virtuales. Si especifica el modificador "Force", incluso si los servicios de purga fallan, las máquinas virtuales se desinstalarán. Este parámetro solo se usa para desinstalar la versión en ejecución actual.  <br/> |
|Confirmar  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Pida confirmación al usuario para desinstalar las máquinas virtuales. El valor predeterminado es TRUE.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El Uninstall-CcAppliance no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Vea también
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

