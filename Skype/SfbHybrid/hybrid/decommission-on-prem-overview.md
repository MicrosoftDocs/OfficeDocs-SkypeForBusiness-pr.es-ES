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
description: Instrucciones sobre cómo retirar el entorno local de Skype Empresarial.
ms.openlocfilehash: 7f5109661fc7d29d83172489dd987b96cb7e87fd
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593903"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a>Retirar el entorno local de Skype Empresarial

Si su organización usa Teams o Skype Empresarial Online con una implementación local de Skype Empresarial Server, puede migrar estos entornos completamente a la nube y, a continuación, retirar la implementación local de Skype Empresarial Server. 

> [!NOTE]
> Antes de retirar el entorno local, debe configurar la conectividad híbrida [entre](configure-hybrid-connectivity.md) la implementación local y Microsoft 365. Después de configurar la conectividad híbrida, puede migrar usuarios a la nube, mientras migra sus reuniones desde locales y migra cualquier contacto de Skype Empresarial Server a Teams. Configurar la conectividad híbrida es un paso necesario para migrar usuarios de local a la nube y para garantizar la funcionalidad completa de Teams.

Para completar el traslado de local a la nube y retirar el entorno local de Skype Empresarial Server, debe completar los siguientes pasos en el siguiente orden:

- **Paso 1.** [Mueva todos los usuarios y extremos de aplicación necesarios de local a en línea.](decommission-move-on-prem-users.md)

- **Paso 2.** [Deshabilite la configuración híbrida](cloud-consolidation-disabling-hybrid.md).

- **Paso 3.** [Quite la implementación local de Skype Empresarial](decommission-remove-on-prem.md).

