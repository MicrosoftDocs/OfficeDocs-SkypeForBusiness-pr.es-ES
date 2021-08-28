---
title: Renew-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: El cmdlet Renew-CcServerCertificate renueva los certificados para Skype for Business Edición de conector de nube cuando están cerca de expirar o ya expiraron. Este comando se cambió a Update-CcServerCertificate cloud connector 2.0 y versiones posteriores.
ms.openlocfilehash: 564f947462248bb65c8514c9699f2f867312c365
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589944"
---
# <a name="renew-ccservercertificate"></a>Renew-CcServerCertificate
 
El cmdlet Renew-CcServerCertificate renueva los certificados para Skype for Business Edición de conector de nube cuando están cerca de expirar o ya expiraron. Este comando se cambió a Update-CcServerCertificate cloud connector 2.0 y versiones posteriores. 
  
```powershell
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se renuevan los certificados para el Almacén de administración central, el servidor de mediación y el servidor perimetral cuando los certificados están a punto de expirar o ya han expirado:
  
```powershell
Renew-CcServerCertificate
```

### <a name="example-2"></a>Ejemplo 2

En el siguiente ejemplo se renuevan los certificados para el servidor de mediación y el servidor perimetral cuando están cerca de expirar o ya expiraron:
  
```powershell
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

Los certificados internos de Cloud Connector emitidos en el Almacén de administración central, el servidor de mediación y el servidor perimetral son válidos durante dos años después de que se emitieron desde un servicio de entidad de certificación. Si los certificados están cerca de expirar o ya han expirado, ejecute el cmdlet Renew-CcServerCertificate para renovar los certificados. 
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Required**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|Funciones  <br/> |Opcional  <br/> |System.Array  <br/> | Matriz de roles de servidor de Cloud Connector. <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Renew-CcServerCertificate no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

