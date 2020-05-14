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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: El cmdlet Set-CcCredential establece las credenciales de la implementación actual de Skype empresarial Cloud Connector Edition.
ms.openlocfilehash: 3717eb0dcaa46bb6708f40ecb7f94869f24774a2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221574"
---
# <a name="set-cccredential"></a>Set-CcCredential
 
El cmdlet Set-CcCredential establece las credenciales de la implementación actual de Skype empresarial Cloud Connector Edition. 
  
Con Cloud Connector versión 2,0 y versiones posteriores, este cmdlet también puede establecer la información de la cuenta para el administrador de la máquina virtual y para el administrador de dominio.
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo, se especifica el nombre de cuenta y la contraseña para el administrador de inquilinos:
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

El cmdlet Set-CcCredential establece el nombre y la contraseña de la cuenta para el administrador de inquilinos. Para las versiones anteriores a 2,0, este administrador debe ser un administrador global. Cloud Connector usa esta cuenta para obtener información de configuración, establecer los parámetros de configuración y actualizar el estado de los dispositivos a la configuración de la organización de Microsoft 365 u Office 365. Con la versión 2,0 y posteriores, también puede usar este cmdlet para actualizar las contraseñas para las cuentas de VmAdmin y de superusuario.
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Required**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> | Obligatorio <br/> |System.String  <br/> | El valor del parámetro debe ser "TenantAdmin", "VmAdmin" o "". <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguna. El cmdlet Set-CcCredential no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Vea también
<a name="ReturnTypes"> </a>

[Get-CcCredential](get-cccredential.md)
  

