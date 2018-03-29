---
title: Conjunto de CcCredential
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: 'El cmdlet Set-CcCredential establece las credenciales de la implementación actual de Skype Empresarial Cloud Connector Edition. '
ms.openlocfilehash: 7680f863ccf082ddb8359c7d3fcefc2c058b6a40
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="set-cccredential"></a>Conjunto de CcCredential
 
El cmdlet Set-CcCredential establece las credenciales de la implementación actual de Skype Empresarial Cloud Connector Edition.  
  
Con conector de nube 2.0 y versiones posteriores, este cmdlet también puede establecer la información de cuenta para el Administrador de la máquina virtual y para el administrador del dominio.
  
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

El cmdlet Set-CcCredential establece el nombre y la contraseña de la cuenta para el administrador de inquilinos. Para versiones anteriores a 2.0, el administrador debe ser un administrador Global de Office 365. Conector de nube utiliza esta cuenta para obtener información de configuración, establecer parámetros de configuración y estado de actualización del dispositivo a la configuración de clientes de Office 365. Con la versión 2.0 y posterior, también puede usar este cmdlet para actualizar las contraseñas para las cuentas de administrador de dominio y de VmAdmin.
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Requerida.**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> |  Obligatorio <br/> |System.String  <br/> |  El valor del parámetro debe ser "TenantAdmin", "VmAdmin" o "DomainAdmin". <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Set-CcCredential no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Get-CcCredential](get-cccredential.md)
  

