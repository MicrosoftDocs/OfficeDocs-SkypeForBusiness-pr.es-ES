---
title: ¿Cuáles son las restricciones de caracteres especiales en las directivas de los equipos?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- me.teamsadmincenter.policies.naming.error
description: Vea ¿qué problemas hay con caracteres especiales en los nombres de las directivas y qué puede hacer para solucionarlo.
ms.openlocfilehash: 43e2daba187bb3a381fe617e088518129d918d09
ms.sourcegitcommit: 2b15226723c299fe94f1a012aa21222173fe3af8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2018
ms.locfileid: "20192167"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>¿Cuáles son las restricciones de caracteres especiales en las directivas de los equipos?

**Aunque se pueden usar caracteres especiales en los nombres de las directivas que creó en los equipos, se recomienda encarecidamente que no lo hace.**

Nombres de directiva que se crean para las reuniones, chat y prescense y otras cosas en los equipos pueden tener caracteres especiales, como @, #, $. Sin embargo, si desea realizar cambios en el nombre en el Microsoft Teams y Skype para el centro de administración de negocio, no podrá a. Debe usar Windows PowerShell y el cmdlet de directiva correcta para realizar cambios.

Por ejemplo, si tiene una directiva de reunión con caracteres especiales y desea cambiar el nombre o quite los caracteres especiales del nombre, necesitará usar el cmdlet Set-CsMeetingPolicy. 

Aquí tiene una lista de los cmdlets de directiva que necesita hacer esto:
1. Set-CsMeetingPolicy
2. Set-CsAppPolicy
3. Set-*


