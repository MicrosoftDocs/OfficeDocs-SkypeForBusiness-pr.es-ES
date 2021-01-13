---
title: Actualización básica de PowerShell| Microsoft Teams| Directiva de interoperabilidad de actualización
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Obtenga información sobre un punto y final para actualizar a Microsoft Teams si el Centro de administración no ha encendido su inquilino.
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
ms.openlocfilehash: adb9a0854268df25ebb8dc0337db22f792834b36
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809100"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Actualizar los usuarios de Skype Empresarial Online a Microsoft Teams

> [!Note]
> Los comandos descritos en este artículo están diseñados para usarse como parte de la lista de comprobación [de Actualización básica.](https://aka.ms/UpgradeBasic)

Los aspectos de la migración técnica de la actualización implican una notificación a los usuarios de que Skype Empresarial va a actualizar a Teams y, a continuación, moverlos a **un modo solo de Teams.** Estos pasos pueden realizarse a través de una sesión de administración remota Windows PowerShell Skype Empresarial o a través del Centro de administración de Microsoft Teams.

Estamos implementando activamente herramientas de actualización en el Centro de administración de [Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md)y debería estar disponible próximamente en su inquilino. En cuanto esté disponible, encontrará información sobre la migración de los usuarios en Configuración de la configuración de [coexistencia y actualización.](https://aka.ms/SkypeToTeams-SetCoexistence)

Si está listo para actualizar hoy, puede usar los comandos [de PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) que aparecen en la tabla siguiente.

| Paso básico de actualización # | Modo | Comando de PowerShell |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Islas + Notificar al usuario de Skype Empresarial<br>(Use este comando si los usuarios están actualmente **en modo de** islas (predeterminado)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(por ejemplo, $SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | Skype Empresarial Solo + Notificar al usuario de Skype Empresarial <br>(Use este comando si los usuarios están actualmente en **modo solo para Skype** Empresarial) | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Solo equipos | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |
