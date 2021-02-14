---
title: Publish-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: El cmdlet Publish-CcAppliance obtiene información de alta disponibilidad de la configuración de inquilino en línea y la publica en el dispositivo de Skype Empresarial Cloud Connector Edition en el servidor host.
ms.openlocfilehash: 159247614733261cac4b3381e35d8dd297cf9a23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824316"
---
# <a name="publish-ccappliance"></a>Publish-CcAppliance
 
El cmdlet Publish-CcAppliance obtiene información de alta disponibilidad de la configuración de inquilino en línea y la publica en el dispositivo de Skype Empresarial Cloud Connector Edition en el servidor host. 
  
```powershell
Publish-CcAppliance
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el siguiente ejemplo se obtiene información de alta disponibilidad de la configuración de inquilino en línea y se publica en el dispositivo de Cloud Connector en el servidor host:
  
```powershell
Publish-CcAppliance
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

La información de alta disponibilidad contiene los FQDN del servidor de mediación y las direcciones IP del sitio RTC. Se agregan nuevos registros A de DNS al servidor de AD para las direcciones IP del servidor de mediación. Los nuevos elementos de topología se actualizan en el Almacén de administración central para los FQDN y las direcciones IP del servidor de mediación. 
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Ninguno. El Publish-CcAppliance no acepta entradas canalizadas.
  
## <a name="return-types"></a>Tipos de valores devueltos
<a name="ReturnTypes"> </a>

Ninguno
  
## <a name="see-also"></a>Vea también
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

