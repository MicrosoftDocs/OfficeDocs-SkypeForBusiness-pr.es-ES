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
ms.openlocfilehash: efa1bcda9af6abccd2ced0faf1e772e779a4483f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287086"
---
# <a name="restore-cccredentials"></a>Restore-CcCredentials
 
El cmdlet restore CC-Credentials restaura todas las credenciales de la implementación actual de Skype empresarial Cloud Connector Edition. 
  
Este cmdlet se aplica a Skype empresarial Cloud Connector Edition 2,1.
  
```
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
  
```
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a>Consulte también

[Get-CcCredential](get-cccredential.md)
  
[Set-CcCredential](set-cccredential.md)
  

