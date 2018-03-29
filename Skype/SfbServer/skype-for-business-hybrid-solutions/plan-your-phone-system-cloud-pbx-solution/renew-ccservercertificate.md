---
title: CcServerCertificate renovar
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: El cmdlet Renew-CcServerCertificate renueva los certificados de Skype Empresarial Cloud Connector Edition cuando están a punto de expirar o ya han expirado. Este comando se cambió a CcServerCertificate de actualización en nube conector 2.0 y versiones posteriores.
ms.openlocfilehash: 3d895a24c4cc8b400aa48ce394324435cfbb3979
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="renew-ccservercertificate"></a>CcServerCertificate renovar
 
El cmdlet Renew-CcServerCertificate renueva los certificados de Skype Empresarial Cloud Connector Edition cuando están a punto de expirar o ya han expirado. Este comando se cambió a CcServerCertificate de actualización en nube conector 2.0 y versiones posteriores. 
  
```
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se renuevan los certificados del almacén de administración central, el servidor de mediación y el servidor perimetral cuando los certificados están a punto de expirar o ya han expirado:
  
```
Renew-CcServerCertificate
```

### <a name="example-2"></a>Ejemplo 2

En el siguiente ejemplo se renuevan los certificados del servidor de mediación y el servidor perimetral cuando están a punto de expirar o ya han expirado:
  
```
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

Conector de nube emiten certificados internos en el almacén de Administración Central, el servidor de mediación y el servidor perimetral son válidas durante dos años después de que se emiten desde un servicio de entidad emisora de certificados. Si los certificados están a punto de expirar o ya han expirado, ejecute el cmdlet Renew-CcServerCertificate para renovar los certificados. 
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Requerida.**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|Roles  <br/> |Opcional   <br/> |System.Array  <br/> | Matriz de roles de servidor de Cloud Connector. <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Renew-CcServerCertificate no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Restablecer CcCACertificate](reset-cccacertificate.md)
  
[CcServerCertificate renovar](renew-ccservercertificate.md)
  
[CcRootCertificate de exportación](export-ccrootcertificate.md)
  

