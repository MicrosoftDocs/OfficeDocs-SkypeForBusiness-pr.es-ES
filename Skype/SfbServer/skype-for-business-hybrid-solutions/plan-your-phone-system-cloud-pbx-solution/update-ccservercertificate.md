---
title: Actualización CcServerCertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: El cmdlet Update-CcServerCertificate renueva los certificados por Skype para conector de nube Business Edition cuando estén cerca de caducidad o ya expiró.
ms.openlocfilehash: 1971f754a7c850d72a3d870e7181738267c99101
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="update-ccservercertificate"></a>Actualización CcServerCertificate
 
El cmdlet Update-CcServerCertificate renueva los certificados por Skype para conector de nube Business Edition cuando estén cerca de caducidad o ya expiró. 
  
```
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se renuevan los certificados del almacén de administración central, el servidor de mediación y el servidor perimetral cuando los certificados están a punto de expirar o ya han expirado:
  
```
Update-CcServerCertificate
```

### <a name="example-2"></a>Ejemplo 2

En el siguiente ejemplo se renuevan los certificados del servidor de mediación y el servidor perimetral cuando están a punto de expirar o ya han expirado:
  
```
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

Conector de nube emiten certificados internos en el almacén de Administración Central, el servidor de mediación y el servidor perimetral son válidas durante dos años después de que se emiten desde un servicio de entidad emisora de certificados. Si los certificados están cerca de caducidad o ya expiró, ejecute el cmdlet Update-CcServerCertificate para renovar los certificados. 
  
Este comando reemplaza el cmdlet renovar CcServerCertificate en nube conector 2.0 y versiones posteriores.
  
## <a name="parameters"></a>Parámetros
<a name="DetailedDescription"> </a>

|**Parámetro**|**Requerida.**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|:-----|
|Roles  <br/> |Opcional   <br/> |System.Array  <br/> | Matriz de roles de servidor de Cloud Connector. <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Update-CcServerCertificate no acepta entrada canalizada.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Restablecer CcCACertificate](reset-cccacertificate.md)
  
[CcServerCertificate renovar](renew-ccservercertificate.md)
  
[CcRootCertificate de exportación](export-ccrootcertificate.md)
  

