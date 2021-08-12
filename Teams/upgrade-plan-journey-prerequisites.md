---
title: Requisitos previos y dependencias ambientales para actualizar a Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Use esta guía para obtener información sobre los requisitos previos y las dependencias ambientales para implementar Teams en su organización
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
ms.openlocfilehash: 66a0bdeac2830fc6a3ebe9f5eae2f382187f384538f2d57c9cf27b56fbdd651a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54323752"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Requisitos previos y dependencias ambientales para Teams

![Diagrama de viaje de actualización, haciendo hincapié en la fase de preparación técnica](media/upgrade-banner-tech-readiness.png "Etapas del viaje de actualización, con énfasis en la fase preparación técnica")

Este artículo forma parte de la fase preparación técnica del viaje de actualización, una actividad que se completa en paralelo con la fase de preparación del usuario. Antes de continuar, confirme que ha completado estas actividades de fases anteriores:

- [Ha incorporado a las partes interesadas del proyecto](upgrade-enlist-stakeholders.md)
- [Ha definido el ámbito del proyecto](./upgrade-define-project-scope.md)
- [Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Elegido el viaje de actualización](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

Teams combina varios Microsoft 365 y Office 365 y, por lo tanto, depende de la correcta implementación y funcionamiento de estos servicios. Estos servicios incluyen, entre otros, SharePoint Online, Exchange Online y OneDrive para la Empresa.

Aunque no todos los servicios son necesarios, le recomendamos que los implemente todos. Si decide no implementar determinados servicios, afectará a la funcionalidad que Teams puede ofrecer a su organización. Por ejemplo, aunque no tiene que implementar SharePoint Online, Teams se basa en SharePoint Online para ciertas funciones, como el uso compartido de archivos en conversaciones de grupo, por lo que no implementar este servicio reducirá la funcionalidad ofrecida a través del cliente.

Vea los artículos siguientes para obtener información sobre los requisitos previos y Teams interactúa con otras tecnologías:

- Si su organización no ha implementado ninguna Microsoft 365 o Office 365 de trabajo, vea [Introducción.](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)

- Si su organización no ha agregado o configurado un dominio comprobado para Microsoft 365 o Office 365, vea Preguntas más frecuentes sobre [dominios.](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)

- Si su organización no ha sincronizado identidades para Azure Active Directory, vea Modelos de identidad y [autenticación en Microsoft Teams](identify-models-authentication.md).

- Si su organización no tiene Exchange Online, vea [Interacción entre Exchange y Microsoft Teams](Exchange-Teams-interact.md).

- Si su organización no tiene SharePoint Online, vea [Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams](SharePoint-OneDrive-interact.md).

- Para obtener información [sobre Microsoft 365 grupos y Microsoft Teams interactúan.](Office-365-groups.md)

- Si su organización es una institución educativa y usa un sistema de información para estudiantes, vea Bienvenido a [Microsoft School Data Sync](/schooldatasync) antes de implementar Microsoft Teams.

- Si su organización está pensando en las opciones de llamadas de red telefónica conmutada (RTC), vea Voz [: conectividad de Sistema telefónico](cloud-voice-landing-page.md)y RTC , Qué [plan](calling-plan-landing-page.md)de llamadas es adecuado para usted y Sistema telefónico enrutamiento [directo.](direct-routing-landing-page.md)

- Para asegurarse de que se han cumplido todos los requisitos de red antes de Teams, vea Preparar la red de su organización [para Microsoft Teams](prepare-network.md).

- Si actualmente usa Skype Empresarial Online Connector para administrar sus servicios, tendrá que pasar al módulo de PowerShell de Teams y actualizar los scripts de PowerShell existentes. Vea [Mover de Skype Empresarial Online Connector al módulo Teams PowerShell para](teams-powershell-move-from-sfbo.md) obtener más información.

Después de comprobar que el entorno cumple todos los requisitos previos aplicables, [evalúe el entorno actual para Teams](upgrade-plan-journey-evaluate-environment.md).