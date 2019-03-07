---
title: Requisitos previos de los equipos de Microsoft | Actualización de adopción de dependencias
author: turgayo
ms.author: turgayo
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: turgayo
description: Use esta guía para obtener más información acerca de los requisitos previos y las dependencias del entorno para implementar los equipos de la organización
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 39483e7b3c8e511f2081f907b187d97dbbaf526f
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2019
ms.locfileid: "30462047"
---
![Fases de la actualización viaje, con especial hincapié en la fase de preparación técnica] (media/upgrade-banner-tech-readiness.png "Fases de la actualización viaje, con especial hincapié en la fase de preparación técnica")

En este artículo forma parte de la fase de preparación técnica de su viaje de actualización, una actividad completar en paralelo con la fase de preparación del usuario. Antes de continuar, confirme que ha realizado estas actividades de fases anteriores:

- [Los participantes en el proyecto de alta](upgrade-enlist-stakeholders.md)
- [Define el ámbito del proyecto](https://aka.ms/SkypetoTeams-Scope)
- [Entiende coexistencia e interoperabilidad de Skype para profesionales y los equipos](https://aka.ms/SkypeToTeams-Coexist)
- [Elegido su viaje por la actualización](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Requisitos previos y las dependencias del entorno para los equipos

Los equipos combina varios servicios de Office 365 y, por lo tanto, depende de la correcta implementación y el funcionamiento de estos servicios. Estos servicios incluyen, pero no está limitado a: Exchange Online, SharePoint Online y OneDrive para la empresa.

Aunque no todos los servicios son necesarios, se recomienda encarecidamente implementar todos ellos. Si decide no implementar determinados servicios, afectará a la funcionalidad que los equipos pueden ofrecer a su organización. Por ejemplo, aunque no tiene que implementar SharePoint Online, los equipos se basan en SharePoint Online para determinadas funciones, como compartir archivos de las conversaciones en grupo, por lo que no se implementa este servicio reducirán la funcionalidad que ofrece a través de la cliente.

Vea los siguientes artículos para obtener más información acerca de los requisitos previos y cómo los equipos interactúa con otras tecnologías:

- Si la organización no ha implementado las cargas de trabajo de Office 365, vea [Introducción a Office 365 para la empresa](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).

- Si la organización no ha agregado o se ha configurado un dominio comprobado para Office 365, vea [Verify su dominio de Office 365](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).

- Si su organización no sincronizado las identidades de Azure Active Directory, vea [modelos de identidad y la autenticación en los equipos de Microsoft](identify-models-authentication.md).

- Si su organización doesn¹t tiene Exchange Online, vea [comprender cómo interactúan los equipos de Microsoft y de Exchange](Exchange-Teams-interact.md).

- Si su organización no tiene SharePoint Online, consulte [comprender cómo SharePoint Online y OneDrive para la empresa interactúan con los equipos de Microsoft](SharePoint-OneDrive-interact.md).

- Obtenga información sobre cómo [interactúan los grupos de Office 365 y equipos de Microsoft](Office-365-groups.md).

- Si la organización es una institución de enseñanza y usar un sistema de información de estudiantes, [implementar la sincronización de datos de escuela](https://docs.microsoft.com/schooldatasync) antes de implementar Microsoft Teams.

Una vez que se haya comprobado que su entorno cumple todos los requisitos previos aplicables, [evaluar su entorno actual para los equipos](upgrade-plan-journey-evaluate-environment.md).