---
title: PowerShell de actualización básica| Microsoft Teams| Grant Upgrade Interop Policy
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Obtenga información sobre un stopgap para actualizar a Microsoft Teams si el Centro de Administración no se ha iluminado en su inquilino.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 02ba32e5b498639e93bc10757c51429871f5683a
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2022
ms.locfileid: "66606039"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Actualizar los usuarios de Skype Empresarial Online a Microsoft Teams

> [!Note]
> Los comandos descritos en este artículo están diseñados para usarse como parte de la lista de comprobación [de Actualización básica](./upgrade-start-here.md) .

Los aspectos técnicos de la migración de la actualización implican notificar a los usuarios que Skype Empresarial actualizar a Teams y, a continuación, moverlos a un modo **solo de Teams**. Estos pasos se pueden llevar a cabo a través de una sesión Windows PowerShell remota Skype Empresarial o a través del Centro de administración de Microsoft Teams.

Estamos implementando activamente herramientas de actualización en el [centro de administración de Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md) y debería estar disponible pronto en su inquilino. Tan pronto como esté disponible, encontrará información sobre la migración de los usuarios en Configuración de la [configuración de coexistencia y actualización](./setting-your-coexistence-and-upgrade-settings.md).

Si está listo para actualizar hoy, puede usar los comandos de [PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) enumerados en la tabla siguiente.

| Paso básico de actualización # | Modo | Comando de PowerShell |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Islas + Notificar al usuario de Skype Empresarial<br>(Use este comando si los usuarios están actualmente en modo **Islas** (predeterminado)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(por ejemplo, $SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | solo Skype Empresarial + Notificar al usuario de Skype Empresarial <br>(Use este comando si los usuarios están actualmente en **modo solo Skype Empresarial**) | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Solo Teams | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |