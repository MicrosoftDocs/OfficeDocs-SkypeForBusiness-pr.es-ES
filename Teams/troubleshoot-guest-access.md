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
description: Obtenga ayuda y solucione problemas con el acceso de invitado en Microsoft Teams.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: e0a3530b7a1f9029d9f671d0a02ef58cbb7907bf
ms.sourcegitcommit: 96d98e145ff300833d827a7d43b4e4b0331b7538
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871736"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>Solución de problemas con el acceso de invitado en Microsoft Teams
======================================================

> [!IMPORTANT]
> Es posible que tenga que esperar hasta 24 horas para que los cambios surtan efecto. 


- Para comprobar si hay problemas de soporte técnico actuales con el acceso de invitado en Teams, vaya a [solución de problemas de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).
- Para ver si conocemos su problema, consulte [problemas conocidos de Microsoft Teams](Known-issues.md).
- Los invitados son usuarios externos a su organización. Si alguien se encuentra dentro de su organización (incluidos los empleados, los contratistas en el sitio o los agentes en el sitio), no se pueden agregar como invitados. Lo mismo se aplica a tus afiliados.
- Descubra futuras características nuevas o actualizadas de acceso de invitado en la [Guía básica de Teams](https://aka.ms/teamsroadmap).
- Díganos lo que quiere en [UserVoice de Teams](https://aka.ms/TeamsUserVoice).

## <a name="if-your-guests-are-seeing-license-errors"></a>Si los invitados experimentan errores de licencia

El acceso de invitados en Teams usa Azure Active Directory (Azure AD) empresarial para empresas (B2B) y su modelo de licencias. El acceso de invitado se incluye con todas las suscripciones de Office 365 Empresa Premium, Office 365 Enterprise y Office 365 Educación. No se necesita ninguna otra licencia de Office 365.

Si ve errores de licencias, asegúrese de leer las instrucciones de licencias [B2B de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) para determinar los requisitos de licencia para satisfacer sus necesidades de acceso de invitados en su organización.


- Las licencias de invitados se cuentan en relación con la organización que invita. Considere esto cuando calcule el número de licencias que necesita.
- Las licencias se cuentan en relación con su organización si los invitados invitados provienen de otro inquilino de Office 365 o si usan sus direcciones de correo electrónico personales.

## <a name="support-for-b2b-user-types"></a>Compatibilidad con tipos de usuario B2B
Actualmente, los equipos solo tienen compatibilidad con los tipos de estado 1 y estado 2 de los usuarios invitados [definidos por Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).

## <a name="related-topics"></a>Temas relacionados

[Acceso de invitado a Teams](guest-access.md)


