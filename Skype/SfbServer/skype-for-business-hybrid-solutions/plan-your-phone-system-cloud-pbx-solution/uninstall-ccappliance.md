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
ms.localizationpriority: medium
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: El cmdlet Uninstall-CcAppliance desinstala el dispositivo Skype for Business Edición de conector de nube del servidor host.
ms.openlocfilehash: 12a15e7bc338fc503a1fafbd6e3059f73dcd40d4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624952"
---
# <a name="uninstall-ccappliance"></a>Uninstall-CcAppliance
 
El cmdlet Uninstall-CcAppliance desinstala el dispositivo Skype for Business Edición de conector de nube del servidor host. 
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se descarga y desinstala el dispositivo de Cloud Connector del servidor host:
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a>Ejemplo 2

En el siguiente ejemplo se agota y se desinstala por la fuerza el dispositivo de Cloud Connector en ejecución en el servidor host, incluso si se ha fallado el proceso de vaciado:
  
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

Si va a desinstalar la versión en ejecución actual de Cloud Connector, los servicios de vaciado se ejecutan primero en el servidor de mediación y el servidor perimetral para permitir que las llamadas simultáneas finalicen antes de desinstalar las máquinas virtuales. Si desinstala una versión de copia de seguridad, no se realiza el vaciado.
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Required**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
| Versión <br/> | Opcional <br/> |System.String  <br/> | La versión de Cloud Connector que se desinstalará del servidor host. Si no se especifica, desinstale la versión en ejecución actual. <br/> |
|Force  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Si desinstala la versión actual en ejecución, intente vaciar los servidores del servidor de mediación y del servidor perimetral antes de desinstalar las máquinas virtuales. Si especifica el modificador "Forzar", incluso si los servicios de desagüe fallan, las máquinas virtuales se desinstalarán. Este parámetro solo se usa para desinstalar la versión actual en ejecución.  <br/> |
|Confirmar  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Pida a la confirmación del usuario que desinstale las máquinas virtuales. El valor predeterminado es TRUE.  <br/> |
   
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
  

