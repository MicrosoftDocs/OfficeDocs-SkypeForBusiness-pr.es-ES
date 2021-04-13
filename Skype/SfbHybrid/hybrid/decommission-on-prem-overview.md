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
ms.openlocfilehash: 46848c6730d37f549a8d5ee16f066fa67c789873
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656686"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a>Retirar el entorno local de Skype Empresarial

Si su organización usa Teams o Skype Empresarial Online con una implementación local de Skype Empresarial Server, puede migrar estos entornos completamente a la nube y, a continuación, retirar la implementación local de Skype Empresarial Server. 

> [!NOTE]
> Antes de retirar el entorno local, debe configurar la conectividad híbrida [entre](configure-hybrid-connectivity.md) la implementación local y Microsoft 365. Después de configurar la conectividad híbrida, puede migrar usuarios a la nube, mientras migra sus reuniones desde locales y migra cualquier contacto de Skype Empresarial Server a Teams. Configurar la conectividad híbrida es un paso necesario para migrar usuarios de local a la nube y para garantizar la funcionalidad completa de Teams.

Para completar el traslado de local a la nube y retirar el entorno local de Skype Empresarial Server, debe completar los siguientes pasos en el siguiente orden:

- **Paso 1.** [Mueva todos los usuarios necesarios de local a en línea.](decommission-move-on-prem-users.md)

- **Paso 2.** [Deshabilite la configuración híbrida](cloud-consolidation-disabling-hybrid.md).

- **Paso 3.** [Mover extremos de aplicación híbrida de local a en línea.](decommission-move-on-prem-endpoints.md)

- **Paso 4.** [Quite la implementación local de Skype Empresarial](decommission-remove-on-prem.md).

