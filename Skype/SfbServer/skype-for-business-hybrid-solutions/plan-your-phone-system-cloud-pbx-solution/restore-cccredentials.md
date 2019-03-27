---
title: Restore-CcCredentials
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: El cmdlet Restore Cc-credenciales restaura todas las credenciales de la actual Skype para la implementación de Business Edition de conector en la nube.
ms.openlocfilehash: 0b790b9f2edab9fade2738c3c95348be864f9017
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891471"
---
# <a name="restore-cccredentials"></a>Restore-CcCredentials
 
El cmdlet Restore Cc-credenciales restaura todas las credenciales de la actual Skype para la implementación de Business Edition de conector en la nube. 
  
Este cmdlet se aplica a Skype para conector Edition 2.1 de negocio en la nube.
  
```
Restore-CcCredentials 
```

## <a name="detailed-description"></a>Descripción detallada

El cmdlet Restore-CcCredentials limpia todas las credenciales y le pregunta si desea volver a escribir todas las credenciales usadas para el actual Skype para la implementación de nube de Business Connector.
  
## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="input-types"></a>Tipos de entrada

Ninguno. El cmdlet Restore-CcCredentials no acepta entradas transferidas.
  
## <a name="return-types"></a>Tipos de valores devueltos

Ninguno.
  
## <a name="example"></a>Ejemplo

En el ejemplo siguiente se restaura todas las credenciales de la implementación actual de conector en la nube:
  
```
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a>Consulte también

[Get-CcCredential](get-cccredential.md)
  
[Set-CcCredential](set-cccredential.md)
  

