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
ms.openlocfilehash: afa30ad1b264088294f775bd69d52e29c5bb423d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116548"
---
# <a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>Solución de problemas con el acceso de invitado en Microsoft Teams

- Para ver si conocemos el problema, consulte [Equipos de soporte técnico de su organización.](/MicrosoftTeams/troubleshoot/teams-welcome)
- Para comprobar si hay problemas de soporte técnico actuales relacionados con el acceso de invitados en Teams, vaya a [Solución de problemas de Teams](/MicrosoftTeams/troubleshoot/).
- Los invitados son personas de fuera de su organización. Si alguien se encuentra en su organización (incluidos los empleados, los contratistas in situ o los agentes in situ), no se pueden agregar como invitados. Esto mismo se aplica a las filiales.
- Obtenga más información sobre las próximas características de acceso de invitados nuevas o actualizadas en la [Hoja de ruta de Teams](https://aka.ms/teamsroadmap).
- Díganos lo que quiere en [Teams UserVoice](https://aka.ms/TeamsUserVoice).

## <a name="if-your-guests-are-seeing-license-errors"></a>Si los invitados ven errores de licencia

El acceso de invitado en Teams usa Azure Active Directory (Azure AD) negocio a negocio (B2B) y el modelo de licencia. El acceso de invitados está incluido en todas las suscripciones de Microsoft 365 Empresa Estándar, Office 365 Enterprise y Office 365 Education. No se necesita ninguna otra licencia de Microsoft 365 u Office 365.

> [!NOTE]
> Teams debe estar habilitado en el inquilino principal de un invitado para que los invitados puedan iniciar sesión y usar Teams como invitado en otro espacio empresarial (recurso).

Si ve errores de licencia, asegúrese de leer el modelo de facturación de identidades externas de [Azure AD](/azure/active-directory/external-identities/external-identities-pricing) para determinar los requisitos de licencias para satisfacer sus necesidades de acceso de invitado en su organización.

- Las licencias de invitado se cuentan contra la organización que invita. Considere esto al calcular el número de licencias que necesita.
- Las licencias se cuentan en su organización tanto si los invitados invitados proceden de otra organización de Microsoft 365 como si usan sus direcciones de correo electrónico personales.

## <a name="support-for-b2b-user-types"></a>Soporte técnico para los tipos de usuario B2B

Actualmente, Teams solo admiten los tipos de estado 1 y estado 2 de usuarios invitados [definido por Azure B2B](/azure/active-directory/b2b/user-properties).

## <a name="related-topics"></a>Temas relacionados

[Acceso de invitado a Teams](guest-access.md)

[Solución de problemas de Teams](/MicrosoftTeams/troubleshoot/teams)