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
ms.localizationpriority: medium
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: El cmdlet Restore Cc-Credentials restaura todas las credenciales de la implementación Skype for Business Edición de conector de nube actual.
ms.openlocfilehash: 050c4265bff7673a7db620ff41a56a2735d6b4a7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588442"
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
  

