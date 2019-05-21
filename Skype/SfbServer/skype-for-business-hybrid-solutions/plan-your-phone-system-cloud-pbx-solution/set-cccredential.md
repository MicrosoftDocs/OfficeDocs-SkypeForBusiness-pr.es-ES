---
title: Set-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: 'El cmdlet Set-CcCredential establece las credenciales de la implementación actual de Skype Empresarial Cloud Connector Edition. '
ms.openlocfilehash: 59c058f8965bbc6fc011806f383c547c1e7b6cd1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286981"
---
# <a name="set-cccredential"></a>Set-CcCredential
 
El cmdlet Set-CcCredential establece las credenciales de la implementación actual de Skype Empresarial Cloud Connector Edition.  
  
Con el conector de la nube versión 2,0 y posteriores, este cmdlet también puede establecer la información de la cuenta para el administrador de la máquina virtual y para el administrador del dominio.
  
```
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se especifica el nombre y la contraseña de la cuenta para el administrador de inquilinos:
  
```
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

El cmdlet Set-CcCredential establece el nombre y la contraseña de la cuenta para el administrador de inquilinos. Para las versiones anteriores a 2.0, este administrador tiene que ser un administrador global de Office 365. El conector para la nube usa esta cuenta para obtener información de configuración, establecer parámetros de configuración y actualizar el estado del dispositivo a la configuración de inquilino de Office 365. Con la versión 2,0 y posteriores, también puede usar este cmdlet para actualizar las contraseñas de las cuentas de VmAdmin y de.
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Requerida.**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> | Requerido <br/> |System.String  <br/> |  El valor del parámetro debe ser "TenantAdmin", "VmAdmin" o "DomainAdmin". <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Set-CcCredential no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Get-CcCredential](get-cccredential.md)
  

