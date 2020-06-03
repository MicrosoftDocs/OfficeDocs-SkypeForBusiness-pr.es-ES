---
title: Actualización básica PowerShell | Microsoft Teams | Conceder actualización de directiva de interoperabilidad
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Obtenga más información sobre un descontinuación de la actualización a Microsoft Teams si el centro de administración no se ha iluminado en su inquilino.
localization_priority: Normal
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
ms.openlocfilehash: d51ff3304aae82f49023bdf461e76e4585cda296
ms.sourcegitcommit: 6acede580649588334aeb48130ab2a5d73245723
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2020
ms.locfileid: "44522483"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Actualización de los usuarios de Skype empresarial online a Microsoft Teams

> [!Note]
> Los comandos que se describen en este artículo están diseñados para usarse como parte de la actualización de la lista de comprobación [básica](https://aka.ms/UpgradeBasic) .

Los aspectos técnicos de la migración de su actualización implican notificar a los usuarios que Skype empresarial se va a actualizar a teams y, a continuación, moverlos a un modo de **solo equipos** . Estos pasos se pueden realizar mediante una sesión de Windows PowerShell remota de Skype empresarial o a través del centro de administración de Microsoft Teams.

Estamos implementando de forma activa las herramientas de actualización en el [centro de administración de Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md)y debería estar disponible muy pronto en su espacio empresarial. Tan pronto como esté disponible, puede encontrar información sobre cómo migrar los usuarios con [la configuración de la coexistencia y la actualización](https://aka.ms/SkypeToTeams-SetCoexistence)de la configuración.

Si está listo para actualizar hoy, puede usar los comandos de [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) que se muestran en la tabla siguiente.

| Paso básico de actualización # | Modo | Comando de PowerShell |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Islas + notificar al usuario de Skype empresarial<br>(Use este comando si los usuarios están actualmente en modo **islas** (predeterminado)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(por ejemplo, $SipAddress = ' TestUser@contoso.com ')* |
| [5](upgrade-basic.md#step-5) | Solo para Skype empresarial + notificar al usuario de Skype empresarial <br>(Use este comando si los usuarios se encuentran actualmente en modo de **solo Skype para empresas** ). | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Solo equipos | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |
