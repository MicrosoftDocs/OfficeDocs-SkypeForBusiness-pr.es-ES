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
ms.openlocfilehash: 0c0f65f7026e6c083d9230551d689f0dd19d6b0d
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837640"
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

El acceso de invitado en Teams usa Azure Active Directory (Azure AD) negocio a negocio (B2B) y el modelo de licencia. El acceso de invitado se incluye con todas las suscripciones de Office 365 Empresa Premium, Office 365 Enterprise y Office 365 Educación. No se necesita ninguna otra licencia de Office 365.

Si ve errores de licencia, asegúrese de leer la información [instrucciones de licencias B2B de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) para determinar los requisitos de licencia para satisfacer las necesidades de acceso de invitado en su organización.


- Las licencias de invitado se cuentan contra la organización que invita. Considere esto al calcular el número de licencias que necesita.
- Las licencias se cuentan en contra de su organización, independientemente de si los invitados provienen de otro espacio empresarial de Office 365 o si están utilizando sus direcciones de correo electrónico personales.

## <a name="support-for-b2b-user-types"></a>Soporte técnico para los tipos de usuario B2B
Actualmente, Teams solo admiten los tipos de estado 1 y estado 2 de usuarios invitados [definido por Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).

## <a name="related-topics"></a>Temas relacionados

[Acceso de invitado a Teams](guest-access.md)


