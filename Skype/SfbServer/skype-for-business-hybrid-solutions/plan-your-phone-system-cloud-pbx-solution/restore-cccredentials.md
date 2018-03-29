---
title: Restauración CcCredentials
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: El cmdlet Restore Cc-credenciales restaura todas las credenciales de la actual Skype para la implementación del conector de nube Business Edition.
ms.openlocfilehash: 045d7f651408b1cbdbd508966da3272ac61d7c04
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="restore-cccredentials"></a>Restauración CcCredentials
 
El cmdlet Restore Cc-credenciales restaura todas las credenciales de la actual Skype para la implementación del conector de nube Business Edition. 
  
Este cmdlet se aplica a Skype para negocios nube conector Edition 2.1.
  
```

Restore-CcCredentials 
```

## <a name="detailed-description"></a>Descripción detallada

El cmdlet Restore-CcCredentials limpia todas las credenciales y se le pregunta si desea volver a escribir todas las credenciales usadas para el actual Skype para implementación de nube de Business Connector.
  
## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="input-types"></a>Tipos de entrada

Ninguno. El cmdlet Restore-CcCredentials no acepta entrada canalizada.
  
## <a name="return-types"></a>Tipos de valores devueltos

Ninguno.
  
## <a name="example"></a>Ejemplo

En el ejemplo siguiente se restaura todas las credenciales de la implementación de nube conector actual:
  
```
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a>Vea también

[Get-CcCredential](get-cccredential.md)
  
[Conjunto de CcCredential](set-cccredential.md)
  

