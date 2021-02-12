---
title: Requisitos previos y dependencias medioambientales para actualizar a Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Use esta guía para obtener información sobre los requisitos previos y las dependencias medioambientales para implementar Teams en su organización
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bcd3de45954ea500a6be0d325370ab0660604a65
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578283"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Requisitos previos y dependencias medioambientales para Teams

![Diagrama de viaje de actualización, que enfatiza la fase de preparación técnica](media/upgrade-banner-tech-readiness.png "Fases del viaje de actualización, con énfasis en la fase De preparación técnica")

Este artículo forma parte de la fase de preparación técnica del viaje de actualización, una actividad que se completa en paralelo con la fase De disponibilidad del usuario. Antes de continuar, confirma que has completado estas actividades desde fases anteriores:

- [Ha incorporado a las partes interesadas del proyecto](upgrade-enlist-stakeholders.md)
- [Ha definido el ámbito del proyecto](https://aka.ms/SkypetoTeams-Scope)
- [Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Ha elegido el viaje de actualización](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

Teams combina varios servicios de Microsoft 365 y Office 365, y, por tanto, depende de la correcta implementación y funcionamiento de estos servicios. Estos servicios incluyen, pero no están limitados a, SharePoint Online, Exchange Online y OneDrive para la Empresa.

Aunque no todos los servicios son necesarios, recomendamos encarecidamente que los implemente todos. Si decide no implementar determinados servicios, afectará a la funcionalidad que Teams puede ofrecer a su organización. Por ejemplo, aunque no tenga que implementar SharePoint Online, Teams sí confía en SharePoint Online para ciertas funciones como el uso compartido de archivos en conversaciones de grupo, por lo que no implementar este servicio reducirá la funcionalidad que se ofrece a través del cliente.

Consulte los artículos siguientes para obtener información sobre los requisitos previos y cómo Teams interactúa con otras tecnologías:

- Si su organización no ha implementado ninguna carga de trabajo de Microsoft 365 u Office 365, vea [Introducción.](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)

- Si su organización no ha agregado o configurado un dominio comprobado para Microsoft 365 u Office 365, consulte Preguntas más frecuentes [sobre dominios.](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)

- Si su organización no ha sincronizado las identidades con Azure Active Directory, consulte Modelos de identidad [y autenticación en Microsoft Teams.](identify-models-authentication.md)

- Si su organización no tiene Exchange Online, consulte [Comprender cómo interactúan Exchange y Microsoft Teams.](Exchange-Teams-interact.md)

- Si su organización no tiene SharePoint Online, consulte Comprender cómo SharePoint Online y OneDrive para la [Empresa interactúan con Microsoft Teams.](SharePoint-OneDrive-interact.md)

- Para obtener información sobre [cómo interactúan los grupos de Microsoft 365 y Microsoft Teams.](Office-365-groups.md)

- Si su organización es una institución educativa y usa un sistema de información de estudiantes, consulte Bienvenido a [Microsoft School Data Sync](https://docs.microsoft.com/schooldatasync) antes de implementar Microsoft Teams.

- Si su organización está pensando en las opciones de llamadas a la red telefónica conmutada (RTC), consulte [Voz:](cloud-voice-landing-page.md)conectividad de sistema telefónico y RTC, qué [plan](calling-plan-landing-page.md)de llamadas es el adecuado para usted y enrutamiento directo de sistema [telefónico.](direct-routing-landing-page.md)

- Para asegurarse de que se han cumplido todos los requisitos de red antes de implementar Teams, vea Preparar la [red de su organización para Microsoft Teams.](prepare-network.md)

Una vez que haya comprobado que su entorno cumple todos los requisitos previos aplicables, [evalúe su entorno actual para Teams.](upgrade-plan-journey-evaluate-environment.md)
