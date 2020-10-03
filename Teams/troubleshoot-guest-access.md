---
title: Solución de problemas con el acceso de invitado en Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: corbinm
search.appverid: MET150
description: Obtenga ayuda para solucionar problemas y solucionar problemas con el acceso de invitados en Microsoft Teams.
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0ce7744aa18fe8ffe3fc83ca40649672f521bbba
ms.sourcegitcommit: 43e5a4aac11c20dd5a4c35b59695f309e1559e82
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2020
ms.locfileid: "48346361"
---
# <a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>Solución de problemas con el acceso de invitado en Microsoft Teams

- Para saber si conocemos su problema, consulte los [equipos de soporte técnico de su organización](Known-issues.md).
- Para comprobar si hay problemas de soporte técnico actuales relacionados con el acceso de invitados en Teams, vaya a [Solución de problemas de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).
- Los invitados son personas fuera de su organización. Si alguien se encuentra en su organización (incluidos los empleados, los contratistas in situ o los agentes in situ), no se pueden agregar como invitados. Esto mismo se aplica a las filiales.
- Obtenga más información sobre las próximas características de acceso de invitados nuevas o actualizadas en la [Hoja de ruta de Teams](https://aka.ms/teamsroadmap).
- Díganos lo que quiere en [Teams UserVoice](https://aka.ms/TeamsUserVoice).

## <a name="if-your-guests-are-seeing-license-errors"></a>Si los invitados ven errores de licencia

El acceso de invitado en Teams usa Azure Active Directory (Azure AD) negocio a negocio (B2B) y el modelo de licencia. El acceso de invitados está incluido en todas las suscripciones de Microsoft 365 Empresa Estándar, Office 365 Enterprise y Office 365 Education. No se necesita ninguna otra licencia de Microsoft 365 u Office 365.

> [!NOTE]
> Los equipos deben estar habilitados en el inquilino principal de un invitado para que los invitados puedan iniciar sesión y usar Teams como invitado en otro inquilino (recurso).

Si ve errores de licencias, asegúrese de leer el [modelo de facturación de las identidades externas de Azure ad](https://docs.microsoft.com/azure/active-directory/external-identities/external-identities-pricing) para determinar los requisitos de licencias para satisfacer sus necesidades de acceso de invitados en su organización.

- Las licencias de invitado se cuentan contra la organización que invita. Considere esto al calcular el número de licencias que necesita.
- Las licencias se cuentan en relación con su organización si los invitados invitados provienen de otra organización de Microsoft 365 o si usan sus direcciones de correo electrónico personales.

## <a name="support-for-b2b-user-types"></a>Soporte técnico para los tipos de usuario B2B

Actualmente, Teams solo admiten los tipos de estado 1 y estado 2 de usuarios invitados [definido por Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).

## <a name="related-topics"></a>Temas relacionados

[Acceso de invitado a Teams](guest-access.md)

[Solución de problemas de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)