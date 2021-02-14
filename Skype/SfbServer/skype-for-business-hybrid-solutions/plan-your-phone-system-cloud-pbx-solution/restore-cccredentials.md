---
title: Restore-CcCredentials
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: El cmdlet Restore Cc-Credentials restaura todas las credenciales de la implementación actual de Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: b2cd35b284bcd7e49aabbaa3055c397915565d09
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824246"
---
# <a name="restore-cccredentials"></a>Restore-CcCredentials
 
El cmdlet Restore Cc-Credentials restaura todas las credenciales de la implementación actual de Skype Empresarial Cloud Connector Edition. 
  
Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 2.1.
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a>Descripción detallada

El cmdlet Restore-CcCredentials limpia todas las credenciales y le pide que vuelva a escribir todas las credenciales usadas para la implementación actual de Skype Empresarial Cloud Connector.
  
## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="input-types"></a>Tipos de entrada

Ninguno. El Restore-CcCredentials no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos

Ninguno.
  
## <a name="example"></a>Ejemplo

En el siguiente ejemplo se restauran todas las credenciales de la implementación actual de Cloud Connector:
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a>Vea también

[Get-CcCredential](get-cccredential.md)
  
[Set-CcCredential](set-cccredential.md)
  

