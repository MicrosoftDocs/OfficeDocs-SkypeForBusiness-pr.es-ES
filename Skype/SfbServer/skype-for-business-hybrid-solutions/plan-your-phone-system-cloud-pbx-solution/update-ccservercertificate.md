---
title: Update-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: El Update-CcServerCertificate cmdlet renueva los certificados para Skype Empresarial Cloud Connector Edition cuando están a punto de expirar o ya han expirado.
ms.openlocfilehash: da52efcd3fdf6a0793e085098bf6f72725115e9c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824114"
---
# <a name="update-ccservercertificate"></a>Update-CcServerCertificate
 
El Update-CcServerCertificate cmdlet renueva los certificados para Skype Empresarial Cloud Connector Edition cuando están a punto de expirar o ya han expirado. 
  
```powershell
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se renuevan los certificados para el almacén de administración central, el servidor de mediación y el servidor perimetral cuando los certificados están a punto de expirar o ya han expirado:
  
```powershell
Update-CcServerCertificate
```

### <a name="example-2"></a>Ejemplo 2

En el siguiente ejemplo se renuevan los certificados para el servidor de mediación y el servidor perimetral cuando están a punto de expirar o ya han expirado:
  
```powershell
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

Los certificados internos de Cloud Connector emitidos para el almacén de administración central, el servidor de mediación y el servidor perimetral son válidos durante dos años después de que se emitieron desde un servicio de entidad de certificación. Si los certificados están a punto de expirar o ya han expirado, ejecute el cmdlet Update-CcServerCertificate para renovar los certificados. 
  
Este comando reemplaza el cmdlet Renew-CcServerCertificate en Cloud Connector 2.0 y versiones posteriores.
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Required**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|Roles  <br/> |Opcional  <br/> |System.Array  <br/> | Matriz de roles de servidor de Cloud Connector. <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El Update-CcServerCertificate no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Vea también
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

