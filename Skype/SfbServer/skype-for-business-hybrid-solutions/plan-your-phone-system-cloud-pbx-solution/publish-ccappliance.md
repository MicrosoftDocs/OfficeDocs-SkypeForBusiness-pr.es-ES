---
title: Publish-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: 'El cmdlet Publish-CcAppliance obtiene información de alta disponibilidad de la configuración de inquilino en línea y la publica en el dispositivo de Skype Empresarial Cloud Connector Edition en el servidor host. '
ms.openlocfilehash: 119b5e816555eedf221d9db06be15e6a778936d4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879808"
---
# <a name="publish-ccappliance"></a>Publish-CcAppliance
 
El cmdlet Publish-CcAppliance obtiene información de alta disponibilidad de la configuración de inquilino en línea y la publica en el dispositivo de Skype Empresarial Cloud Connector Edition en el servidor host.  
  
```
Publish-CcAppliance
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

El siguiente ejemplo obtiene información de alta disponibilidad de la configuración de inquilino en línea y publica en el dispositivo de conector en la nube en el servidor host:
  
```
Publish-CcAppliance
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

La información de alta disponibilidad contiene los FQDN y las direcciones IP del servidor de mediación del sitio RTC. Se agregan nuevos registros A de DNS al servidor de AD para las direcciones IP del servidor de mediación. Se actualizan nuevo elementos de topología en el almacén de administración central para los FQDN y las direcciones IP del servidor de mediación.  
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El cmdlet Publish-CcAppliance no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Consulte también
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

