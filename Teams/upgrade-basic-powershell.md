---
title: PowerShell actualización básica | Los equipos de Microsoft | Directiva de interoperabilidad de actualización de GRANT
author: dearbeen
ms.author: dearbeen
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Provisional para la actualización a los equipos si todavía no iluminada el centro de administración en el inquilino
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: 753a79bb8138577b5f97666b5b0081520bd386fe
ms.sourcegitcommit: 716d39077784417c3545a91e501ae26ff56ebdf4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2019
ms.locfileid: "29349244"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Actualizar a los usuarios de Skype para empresarial en línea para Microsoft Teams

> [!Note]
> Los comandos que se describen en este artículo están diseñados para usarse como parte de la lista de comprobación [De actualización básica](https://aka.ms/UpgradeBasic) .

Los aspectos técnicos de migración de la actualización implican notificar a los usuarios que se actualización a los equipos y, a continuación, moverlos a un modo de **equipos sólo** Skype para la empresa. Estos pasos pueden realizarse a través de un Skype para la sesión remota de Windows PowerShell de negocio o a través de la & Teams Microsoft Skype para el centro de administración de negocio.

Nos estamos implantar activamente en los [equipos de Microsoft & Skype para el centro de administración de negocio](manage-teams-skypeforbusiness-admin-center.md)de herramientas de actualización y debe estar disponible pronto en el inquilino. Tan pronto como está disponible, puede encontrar información sobre la migración de los usuarios en el [establecimiento de la coexistencia y la configuración de actualizaciones](https://aka.ms/SkypeToTeams-SetCoexistence).

Si está listo para la actualización de hoy en día, puede usar los comandos de [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) enumerados en la siguiente tabla.

| Actualización paso básico # | Modo | Comando de PowerShell |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Islas + notificar la Skype para usuarios de empresa<br>(Utilice este comando si los usuarios están actualmente en modo de **Islas** (valor predeterminado)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(por ejemplo, $SipAddress = 'TestUser@contoso.com')*<br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingDefaultChatDefault -Identity $SipAddress``` |
| [5](upgrade-basic.md#step-5) | Skype para la empresa sólo + notificar la Skype para usuarios de empresa <br>(Utilice este comando si los usuarios están actualmente en modo de **Skype para la empresa sólo** ) | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingSfBChatSfB -Identity $SipAddress``` |
| [7](upgrade-basic.md#step-7) | Sólo los equipos | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingTeamsChatTeams -Identity $SipAddress``` |