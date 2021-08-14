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
description: El cmdlet Publish-CcAppliance obtiene información de alta disponibilidad de la configuración del espacio empresarial en línea y la publica en el Skype for Business Edición de conector de nube en el servidor host.
ms.openlocfilehash: 83b0a7e3806a271a358085bb0cca2a2ef6a518e67e124f0be97c1ff4616e3dcc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326186"
---
# <a name="publish-ccappliance"></a>Publish-CcAppliance
 
El cmdlet Publish-CcAppliance obtiene información de alta disponibilidad de la configuración del espacio empresarial en línea y la publica en el Skype for Business Edición de conector de nube en el servidor host. 
  
```powershell
Publish-CcAppliance
```

## <a name="parameters"></a>Parámetros

Ninguno
  
## <a name="examples"></a>Ejemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Ejemplo 1

En el ejemplo siguiente se obtiene información de alta disponibilidad de la configuración del espacio empresarial en línea y se publica en el dispositivo de Cloud Connector en el servidor host:
  
```powershell
Publish-CcAppliance
```

## <a name="detailed-description"></a>Descripción detallada
<a name="DetailedDescription"> </a>

La información de alta disponibilidad contiene los FQDN del servidor de mediación y las direcciones IP del sitio RTC. Los nuevos registros DNS A se agregan al servidor AD para direcciones IP del servidor de mediación. Los nuevos elementos de topología se actualizan en el Almacén de administración central para los FQDN del servidor de mediación y las direcciones IP. 
  
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
  

