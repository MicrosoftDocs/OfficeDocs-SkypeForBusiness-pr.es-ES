---
title: CcAppliance desinstalar
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
ms.openlocfilehash: 325e21d28ef87f9d27e87721452bc3d67d197169
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="uninstall-ccappliance"></a>CcAppliance desinstalar
 
El cmdlet Uninstall-CcAppliance desinstala el dispositivo en ejecución de Skype Empresarial Cloud Connector Edition desde el servidor host.  
  
```
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el ejemplo siguiente se agota y desinstala el dispositivo conector de nube desde el servidor host:
  
```
Uninstall-CcAppliance
```

### <a name="example-2"></a>Ejemplo 2

En el ejemplo siguiente se purga y forzosamente desinstala el dispositivo conector de nube ejecutando en el servidor host, incluso si ha fallado el proceso de drenaje:
  
```
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a>Ejemplo 3

En el ejemplo siguiente se desinstala una versión de copia de seguridad de nube conector sin pedir confirmación del usuario:
  
```
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

Si está desinstalando la versión actual de ejecución del conector de la nube, servicios de drenaje primero se ejecutan en el servidor de mediación y un servidor perimetral para permitir las llamadas simultáneas a finalizar antes de desinstalar las máquinas virtuales. Si va a desinstalar una versión de copia de seguridad, la depuración no se lleva a cabo.
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Requerida.**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
| Version <br/> | Opcional <br/> |System.String  <br/> | La versión del conector de nube que se van a desinstalar desde el servidor host. Si no se especifica, desinstale la versión en ejecución actual. <br/> |
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

[Instalar CcAppliance](install-ccappliance.md)
  
[CcAppliance publicar](publish-ccappliance.md)
  
[Registro CcAppliance](register-ccappliance.md)
  
[Anular el registro de CcAppliance](unregister-ccappliance.md)
  

