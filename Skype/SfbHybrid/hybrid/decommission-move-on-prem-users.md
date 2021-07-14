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
description: Mueva usuarios antes de retirar un Skype Empresarial entorno local.
ms.openlocfilehash: 992f2dd479e0b8ca8a3f11f069e8ef049259ad9c
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420815"
---
# <a name="move-required-users-before-decommissioning-your-on-premises-environment"></a>Mover usuarios necesarios antes de retirar el entorno local

En este artículo se describe cómo mover los usuarios necesarios a la nube de Microsoft antes de retirar el entorno Skype Empresarial local. Este es el paso 1 de los siguientes pasos para retirar el entorno local:

- **Paso 1. Mueva todos los usuarios necesarios de local a online.** (Este artículo)

- Paso 2. [Deshabilite la configuración híbrida](cloud-consolidation-disabling-hybrid.md).

- Paso 3. [Migre los puntos de conexión de aplicaciones híbridas de local a en línea.](decommission-move-on-prem-endpoints.md) Tenga en cuenta que los puntos de conexión de aplicaciones híbridas existentes no se podrán detectar entre el momento en que realice el paso 2 anterior hasta que complete este paso. Debe planear realizar los pasos 2 y 3 en la misma ventana de mantenimiento.

- Paso 4. [Quite la implementación Skype Empresarial local.](decommission-remove-on-prem.md)


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a>Mover todos los usuarios necesarios de local a la nube

Los usuarios que seguirá usando después de completar la migración deben moverse primero de local a la nube. Los usuarios se mueven mediante las herramientas de administración locales. Para obtener más información, consulte [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).

Aunque es posible que los usuarios con cuentas Skype Empresarial Server locales usen Teams, estos usuarios no tienen la funcionalidad completa de Teams. Estos usuarios no pueden interoperar ni federar con ningún otro usuario que aún use Skype Empresarial (ya sea en línea o local). Estos usuarios tampoco pueden recibir llamadas RTC en su Teams cliente. Por lo tanto, debe mover estos usuarios a línea. Este paso también garantiza que los contactos o reuniones creados en Skype Empresarial Server se migren a Teams.

Para comprobar si hay algún usuario restante en la implementación local, ejecute el siguiente cmdlet en una ventana Skype Empresarial Server PowerShell.

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

Si se devuelve algún usuario, revise el resultado para determinar si se debe mover alguna cuenta a la nube y, para cualquiera de estos usuarios, siga los pasos [aquí](move-users-between-on-premises-and-cloud.md). Para las cuentas de usuario que ya no son necesarias, ejecute el siguiente cmdlet Skype Empresarial Server PowerShell:

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> Al Disable-CsUser se quitarán todos los Skype Empresarial para todos los usuarios que cumplan los criterios de filtro. Antes de continuar, confirme que estas cuentas ya no son necesarias en el futuro.


Ya está listo para deshabilitar [la configuración híbrida](cloud-consolidation-disabling-hybrid.md).

## <a name="see-also"></a>Consulte también

- [Retirar el entorno local de Skype Empresarial](decommission-on-prem-overview.md)

- [Deshabilitar la configuración híbrida](cloud-consolidation-disabling-hybrid.md)

- [Mover puntos de conexión de aplicaciones híbridas de local a online](decommission-move-on-prem-endpoints.md)

- [Eliminar la implementación local de Skype Empresarial](decommission-remove-on-prem.md)




