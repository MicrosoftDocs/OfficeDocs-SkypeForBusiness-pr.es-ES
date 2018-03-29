---
title: Quitar CcLegacyServerCertificate
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
ms.openlocfilehash: f23a753df1a5c9f81b81bc0f1d7d33c01020b489
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="remove-cclegacyservercertificate"></a>Quitar CcLegacyServerCertificate
 
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

|**Parámetro**|**Requerida.**|**Tipo**|**Descripción**|
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
  
[Actualización CcCACertificate](update-cccacertificate.md)
  

