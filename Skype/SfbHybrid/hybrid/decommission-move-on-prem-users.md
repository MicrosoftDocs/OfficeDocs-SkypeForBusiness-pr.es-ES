---
title: Mover usuarios a la nube
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Mover usuarios antes de retirar un entorno local de Skype Empresarial.
ms.openlocfilehash: f04ebeec51b739faa89f907de6c363f0ef70a78e
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656676"
---
# <a name="move-required-users-before-decommissioning-your-on-premises-environment"></a>Mover usuarios necesarios antes de retirar el entorno local

En este artículo se describe cómo mover los usuarios necesarios a la nube de Microsoft antes de retirar el entorno local de Skype Empresarial. Este es el paso 1 de los siguientes pasos para retirar el entorno local:

- **Paso 1. Mueva todos los usuarios necesarios de local a online.** (Este artículo)

- Paso 2. [Deshabilite la configuración híbrida](cloud-consolidation-disabling-hybrid.md).

- Paso 3. [Mover extremos de aplicación híbrida de local a en línea.](decommission-move-on-prem-endpoints.md)

- Paso 4. [Quite la implementación local de Skype Empresarial](decommission-remove-on-prem.md).


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a>Mover todos los usuarios necesarios de local a la nube

Los usuarios que seguirá usando después de completar la migración deben moverse primero de local a la nube. Los usuarios se mueven mediante las herramientas de administración locales. Para obtener más información, consulte [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).

Aunque es posible que los usuarios con cuentas locales de Skype Empresarial Server usen Teams, estos usuarios no tienen la funcionalidad completa de Teams. Estos usuarios no pueden interoperar ni federar con ningún otro usuario que aún use Skype Empresarial (ya sea en línea o local). Estos usuarios tampoco pueden recibir llamadas RTC en su cliente de Teams. Por lo tanto, debe mover estos usuarios a línea. Este paso también garantiza que los contactos o reuniones creados en Skype Empresarial Server se migren a Teams.

Para comprobar si hay algún usuario restante en la implementación local, ejecute el siguiente cmdlet en una ventana de PowerShell de Skype Empresarial Server.

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

Si se devuelve algún usuario, revise el resultado para determinar si se debe mover alguna cuenta a la nube y, para cualquiera de estos usuarios, siga los pasos [aquí](move-users-between-on-premises-and-cloud.md). Para las cuentas de usuario que ya no son necesarias, ejecute el siguiente cmdlet de PowerShell de Skype Empresarial Server:

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> Al Disable-CsUser se quitarán todos los atributos de Skype Empresarial para todos los usuarios que cumplan los criterios de filtro. Antes de continuar, confirme que estas cuentas ya no son necesarias en el futuro.


Ya está listo para deshabilitar [la configuración híbrida](cloud-consolidation-disabling-hybrid.md).

## <a name="see-also"></a>Recursos adicionales

- [Retirar el entorno local de Skype Empresarial](decommission-on-prem-overview.md)

- [Deshabilitar la configuración híbrida](cloud-consolidation-disabling-hybrid.md)

- [Mover puntos de conexión de aplicaciones híbridas de local a online](decommission-move-on-prem-endpoints.md)

- [Eliminar la implementación local de Skype Empresarial](decommission-remove-on-prem.md)




