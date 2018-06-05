---
title: Remove-CcLegacyServerCertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: El cmdlet Remove-CcLegacyServerCertificate quita los certificados de servidores heredados en el almacén de administración central, el servidor de mediación y el servidor perimetral después de ejecutar los cmdlets Renew-CcCACertificate o Renew-CcServerCertificate.
ms.openlocfilehash: dc52351d9c66ff310329da62dbd69da74b19c222
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569843"
---
# <a name="remove-cclegacyservercertificate"></a>Remove-CcLegacyServerCertificate
 
El cmdlet Remove-CcLegacyServerCertificate quita los certificados de servidores heredados en el almacén de administración central, el servidor de mediación y el servidor perimetral después de ejecutar los cmdlets Renew-CcCACertificate o Renew-CcServerCertificate.
  
```
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se quitan los certificados heredados emitidos para el almacén de administración central, el servidor de mediación y el servidor perimetral después de haber renovado los certificados:
  
```
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a>Ejemplo 2

En el siguiente ejemplo se quitan los certificados emitidos para el servidor de mediación y el servidor perimetral después de haber renovado los certificados:  
  
```
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a>Parámetros
<a name="Examples"> </a>

|**Parámetro**|**Requerida.**|**Tipo de**|**Descripción**|
|:-----|:-----|:-----|:-----|
| Roles <br/> |Opcional   <br/> |System.Array  <br/> | Matriz de roles de servidor de Cloud Connector. <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Remove-CcLegacyServerCertificate no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[CcServerCertificate renovar](renew-ccservercertificate.md)
  
[Restablecer CcCACertificate](reset-cccacertificate.md)
  
[CcCACertificate renovar](renew-cccacertificate.md)
  
[Actualización de CcCACertificate](update-cccacertificate.md)
  

