---
title: Actualización básica de PowerShell| Microsoft Teams| Conceder directiva de interoperabilidad de actualización
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Obtenga información sobre un stopgap para actualizar a Microsoft Teams si el Centro de administración no se ha iluminado en el espacio empresarial.
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
ms.openlocfilehash: ef164ee5d93cb5491923ef3b319ae51134924cc2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120550"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Actualizar los usuarios de Skype Empresarial Online a Microsoft Teams

> [!Note]
> Los comandos descritos en este artículo están diseñados para usarse como parte de la lista de comprobación [Actualizar básico.](./upgrade-start-here.md)

Los aspectos de migración técnica de la actualización implican notificar a los usuarios que Skype Empresarial actualizará a Teams y, a continuación, los trasladará a un modo Teams **único.** Estos pasos se pueden realizar a través de Skype Empresarial sesión remota Windows PowerShell o a través del centro Microsoft Teams administración.

Estamos implementando activamente las herramientas de actualización en el centro de administración de [Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md)y debería estar disponible próximamente en su inquilino. Tan pronto como esté disponible, encontrará información sobre cómo migrar los usuarios en Establecer la configuración de [coexistencia y actualización.](./setting-your-coexistence-and-upgrade-settings.md)

Si está listo para actualizar hoy, puede usar los comandos [de PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) enumerados en la tabla siguiente.

| Paso Básico de actualización # | Modo | Comando de PowerShell |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Islas + Notificar al Skype Empresarial usuario<br>(Use este comando si los usuarios están actualmente en **modo Islas** (predeterminado)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(por ejemplo, $SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | Skype Empresarial Solo + Notificar al Skype Empresarial usuario <br>(Use este comando si los usuarios están actualmente en **Skype Empresarial modo único)** | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Teams Solo | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |