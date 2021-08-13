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
description: El cmdlet Restore Cc-Credentials restaura todas las credenciales de la implementación Skype for Business Edición de conector de nube actual.
ms.openlocfilehash: 95b93e28bb109c26927a940324edef20479bed8c193efea6923c74058995a5bd
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340676"
---
# <a name="restore-cccredentials"></a>Restore-CcCredentials
 
El cmdlet Restore Cc-Credentials restaura todas las credenciales de la implementación Skype for Business Edición de conector de nube actual. 
  
Este cmdlet se aplica a Skype for Business Edición de conector de nube 2.1.
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a>Descripción detallada

El cmdlet Restore-CcCredentials limpia todas las credenciales y le pide que vuelva a escribir todas las credenciales usadas para la implementación Skype Empresarial Cloud Connector actual.
  
## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="input-types"></a>Tipos de entrada

Ninguno. El cmdlet Restore-CcCredentials no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos

Ninguno.
  
## <a name="example"></a>Ejemplo

En el siguiente ejemplo se restauran todas las credenciales de la implementación actual de Cloud Connector:
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a>Consulte también

[Get-CcCredential](get-cccredential.md)
  
[Set-CcCredential](set-cccredential.md)
  

