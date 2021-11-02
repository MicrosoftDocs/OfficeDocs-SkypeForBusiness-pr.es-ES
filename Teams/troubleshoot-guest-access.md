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
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: c8d54e236583211c2a8169987bf03ceba756facf
ms.sourcegitcommit: 1957a06d4bae3d42b4e3b6d4bd8ff2752a19d377
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "60641220"
---
# <a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>Solución de problemas con el acceso de invitado en Microsoft Teams

- Para ver si conocemos el problema, consulte Soporte [técnico Teams en su organización.](/MicrosoftTeams/troubleshoot/teams-welcome)
- Para comprobar si hay problemas de soporte técnico actuales relacionados con el acceso de invitados en Teams, vaya a [Solución de problemas de Teams](/MicrosoftTeams/troubleshoot/).
- Los invitados son personas de fuera de su organización. Si alguien se encuentra en su organización (incluidos los empleados, los contratistas in situ o los agentes in situ), no se pueden agregar como invitados. Esto mismo se aplica a las filiales.
- Obtenga más información sobre las próximas características de acceso de invitados nuevas o actualizadas en la [Hoja de ruta de Teams](https://aka.ms/teamsroadmap).
- Díganos lo que quiere en [Teams UserVoice](https://aka.ms/TeamsUserVoice).

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

## <a name="if-your-guests-are-seeing-license-errors"></a>Si los invitados ven errores de licencia

El acceso de invitado en Teams usa Azure Active Directory (Azure AD) negocio a negocio (B2B) y el modelo de licencia. El acceso de invitados está incluido en todas las suscripciones de Microsoft 365 Empresa Estándar, Office 365 Enterprise y Office 365 Education. No se necesita ninguna otra licencia de Microsoft 365 u Office 365.

> [!NOTE]
> Teams estar habilitado en el espacio empresarial de un invitado para que los invitados puedan iniciar sesión y usar Teams como invitado en otro espacio empresarial (recurso).

Si ve errores de licencia, asegúrese [](/azure/active-directory/external-identities/external-identities-pricing) de leer el modelo de facturación para Azure AD Identidades externas para determinar los requisitos de licencia para satisfacer sus necesidades de acceso de invitado en su organización.

- Las licencias de invitado se cuentan contra la organización que invita. Considere esto al calcular el número de licencias que necesita.
- Las licencias se cuentan en su organización tanto si los invitados invitados proceden de otra organización Microsoft 365 como si usan sus direcciones de correo electrónico personales.

## <a name="related-topics"></a>Temas relacionados

[Acceso de invitado a Teams](guest-access.md)

[Solución de problemas de Teams](/MicrosoftTeams/troubleshoot/teams)
