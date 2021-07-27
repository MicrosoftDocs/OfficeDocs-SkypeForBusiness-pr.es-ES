---
title: Retirar el entorno local de Skype Empresarial
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
description: Instrucciones para retirar el entorno Skype Empresarial local.
ms.openlocfilehash: 420ca75e12737ce85c2fd03031f3e1b8fd9ca625
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510801"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a>Retirar el entorno local de Skype Empresarial

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Si su organización usa Teams o Skype Empresarial Online con una implementación local de Skype Empresarial Server, puede migrar estos entornos completamente a la nube y, a continuación, retirar la implementación local de Skype Empresarial Server. 

> [!NOTE]
> Antes de retirar el entorno local, debe configurar la conectividad híbrida [entre](configure-hybrid-connectivity.md) la implementación local y Microsoft 365. Después de configurar la conectividad híbrida, puede migrar usuarios a la nube, mientras migra sus reuniones desde locales y migra cualquier contacto de Skype Empresarial Server a Teams. La configuración de la conectividad híbrida es un paso necesario para migrar usuarios de local a la nube y garantizar la funcionalidad Teams usuario.

Para completar el traslado de local a la nube y retirar el entorno Skype Empresarial Server local, debe completar los siguientes pasos en el siguiente orden:

- **Paso 1.** [Mueva todos los usuarios necesarios de local a en línea.](decommission-move-on-prem-users.md)

- **Paso 2.** [Deshabilite la configuración híbrida](cloud-consolidation-disabling-hybrid.md).

- **Paso 3.** [Mover extremos de aplicación híbrida de local a en línea.](decommission-move-on-prem-endpoints.md)

- **Paso 4.** [Quite la implementación Skype Empresarial local.](decommission-remove-on-prem.md)

