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
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: El cmdlet restore CC-Credentials restaura todas las credenciales de la implementación actual de Skype empresarial Cloud Connector Edition.
ms.openlocfilehash: adac3f0b9ca6cf392b537a9c5d0f2095021c7120
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003250"
---
# <a name="restore-cccredentials"></a>Restore-CcCredentials
 
El cmdlet restore CC-Credentials restaura todas las credenciales de la implementación actual de Skype empresarial Cloud Connector Edition. 
  
Este cmdlet se aplica a Skype empresarial Cloud Connector Edition 2,1.
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a>Descripción detallada

El cmdlet restore-CcCredentials limpia todas las credenciales y le pide que vuelva a escribir todas las credenciales utilizadas para la implementación actual de Skype empresarial Connector.
  
## <a name="parameters"></a>Parámetros

Ninguna
  
## <a name="input-types"></a>Tipos de entrada

Ninguno. El cmdlet restore-CcCredentials no acepta la entrada canalizada.
  
## <a name="return-types"></a>Tipos de valores devueltos

Ninguno.
  
## <a name="example"></a>Ejemplo

En el siguiente ejemplo se restauran todas las credenciales de la implementación del conector de nube actual:
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a>Consulte también

[Get-CcCredential](get-cccredential.md)
  
[Set-CcCredential](set-cccredential.md)
  

