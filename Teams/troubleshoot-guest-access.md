---
title: Solución de problemas con el acceso de invitado en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
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
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 52d3922bc68e942ad1cd58e40861fa8820ee6614
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778406"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>Solución de problemas con el acceso de invitado en Microsoft Teams
======================================================

> [!IMPORTANT]
> Es posible que tenga que esperar hasta 24 horas para que sus cambios surtan efecto. 


- Para comprobar si hay problemas de soporte técnico actuales relacionados con el acceso de invitados en Teams, vaya a [Solución de problemas de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).
- Para comprobar si conocemos su problema, consulte [Problemas conocidos de Microsoft Teams](Known-issues.md).
- Los invitados son usuarios de fuera de su organización. Si alguien se encuentra en su organización (incluidos los empleados, los contratistas in situ o los agentes in situ), no se pueden agregar como invitados. Esto mismo se aplica a las filiales.
- Obtenga más información sobre las próximas características de acceso de invitados nuevas o actualizadas en la [Hoja de ruta de Teams](https://aka.ms/teamsroadmap).
- Díganos lo que quiere en [Teams UserVoice](https://aka.ms/TeamsUserVoice).

## <a name="if-your-guests-are-seeing-license-errors"></a>Si los invitados ven errores de licencia

El acceso de invitado en Teams usa Azure Active Directory (Azure AD) negocio a negocio (B2B) y el modelo de licencia. El acceso de invitados se incluye en todas las suscripciones de Microsoft 365 Business Standard, Office 365 Enterprise y Office 365 Education. No se necesita ninguna otra licencia de Office 365.

> [!NOTE]
> Los equipos deben estar habilitados en el inquilino principal de un invitado para que los invitados puedan iniciar sesión y usar Teams como invitado en otro inquilino (recurso).

Si ve errores de licencias, asegúrese de leer las instrucciones de licencias [B2B de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) para determinar los requisitos de licencia para satisfacer sus necesidades de acceso de invitados en su organización.


- Las licencias de invitado se cuentan contra la organización que invita. Considere esto al calcular el número de licencias que necesita.
- Las licencias se cuentan en relación con su organización si los invitados invitados provienen de otra organización de Office 365 o si usan sus direcciones de correo electrónico personales.

## <a name="support-for-b2b-user-types"></a>Soporte técnico para los tipos de usuario B2B
Actualmente, Teams solo admiten los tipos de estado 1 y estado 2 de usuarios invitados [definido por Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).

## <a name="related-topics"></a>Temas relacionados

[Acceso de invitado a Teams](guest-access.md)


