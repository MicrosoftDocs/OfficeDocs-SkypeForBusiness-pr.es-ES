---
title: Requisitos previos de Microsoft Teams | Actualización de adopción de dependencias
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Use esta guía para obtener información sobre los requisitos previos y las dependencias ambientales para implementar equipos de su organización.
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
ms.openlocfilehash: 241c1f2ab0287b6beb2a99386b2f04b1f7cbfb28
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "44666072"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Requisitos previos y dependencias medioambientales de los equipos

![Actualizar el diagrama de viaje, enfatizando la fase de preparación técnica](media/upgrade-banner-tech-readiness.png "Etapas del viaje de actualización, con énfasis en la fase de preparación técnica")

Este artículo forma parte de la fase de preparación técnica de su viaje de actualización, una actividad que ha completado en paralelo con la fase de preparación del usuario. Antes de continuar, confirme que ha completado estas actividades desde fases anteriores:

- [Ha incorporado a las partes interesadas del proyecto](upgrade-enlist-stakeholders.md)
- [Ha definido el ámbito del proyecto](https://aka.ms/SkypetoTeams-Scope)
- [Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Eligió la actualización del viaje](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

Teams combina varios servicios de Microsoft 365 y de Office 365 y, por lo tanto, depende de la implementación y el funcionamiento correctos de estos servicios. Estos servicios incluyen, entre otros, SharePoint Online, Exchange Online y OneDrive para la empresa.

Aunque no se necesitan todos los servicios, se recomienda implementarlos todos. Si decide no implementar determinados servicios, esta afectará a la funcionalidad que los equipos pueden ofrecer a su organización. Por ejemplo, aunque no tiene que implementar SharePoint Online, los equipos dependen de SharePoint Online para ciertas funciones, como el uso compartido de archivos en las conversaciones de grupo, por lo que si no implementa este servicio, disminuirá la funcionalidad que se ofrece a través del cliente.

Consulte los artículos siguientes para obtener información sobre los requisitos previos y cómo Teams interactúa con otras tecnologías:

- Si su organización no ha implementado ninguna carga de trabajo de Microsoft 365 u Office 365 [, consulte Introducción](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).

- Si su organización no ha agregado ni configurado un dominio verificado para Microsoft 365 u Office 365, consulte [preguntas más frecuentes sobre los dominios](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).

- Si su organización no ha sincronizado las identidades con Azure Active Directory, consulte [modelos de identidad y autenticación en Microsoft Teams](identify-models-authentication.md).

- Si su organización no tiene<sup>1</sup>Exchange Online, consulte [comprender cómo interactúan Exchange y Microsoft Teams](Exchange-Teams-interact.md).

- Si su organización no tiene SharePoint Online, consulte [comprender cómo SharePoint Online y OneDrive para la empresa interactúan con Microsoft Teams](SharePoint-OneDrive-interact.md).

- Obtenga información sobre cómo [interactúan microsoft 365 Groups y Microsoft Teams](Office-365-groups.md).

- Si su organización es un centro educativo y usa un sistema de información de estudiante, [implemente School Data Sync](https://docs.microsoft.com/schooldatasync) antes de implementar Microsoft Teams.

Una vez que haya verificado que su entorno cumple con todos los requisitos previos vigentes, [evalúe su entorno actual para Teams](upgrade-plan-journey-evaluate-environment.md).
