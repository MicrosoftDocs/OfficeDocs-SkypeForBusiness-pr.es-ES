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
description: El cmdlet Set-CcCredential establece la credencial de la implementación Skype for Business Edición de conector de nube actual.
ms.openlocfilehash: 330326790f20add51dcaeb4468b17438c302c353c08076402e15f4d32985c117
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54324140"
---
# <a name="set-cccredential"></a>Set-CcCredential
 
El cmdlet Set-CcCredential establece la credencial de la implementación Skype for Business Edición de conector de nube actual. 
  
Con Cloud Connector versión 2.0 y versiones posteriores, este cmdlet también puede establecer la información de cuenta para el administrador de la máquina virtual y para el administrador de dominio.
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se especifica el nombre de cuenta y la contraseña del administrador de inquilinos:
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

El cmdlet Set-CcCredential establece el nombre de cuenta y la contraseña del administrador de inquilinos. Para las versiones anteriores a la 2.0, este administrador debe ser un administrador global. Cloud Connector usa esta cuenta para obtener información de configuración, establecer parámetros de configuración y actualizar el estado del dispositivo al Microsoft 365 o Office 365 de la organización. Con la versión 2.0 y versiones posteriores, también puede usar este cmdlet para actualizar las contraseñas de las cuentas VmAdmin y DomainAdmin.
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Required**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> | Obligatorio <br/> |System.String  <br/> | El valor del parámetro debe ser "TenantAdmin", "VmAdmin" o "DomainAdmin". <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Set-CcCredential no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Get-CcCredential](get-cccredential.md)
  

