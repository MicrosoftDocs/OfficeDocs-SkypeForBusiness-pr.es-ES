---
title: Funciones del moderador y participante en un evento de Teams en directo
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: Obtenga información sobre las funciones del moderador y participante en un evento de Teams en directo.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 7714442be770420797df1c51a532f769eb0350a4
ms.sourcegitcommit: f9db7effbb1e56484686afe4724cc3b73380166d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "44565863"
---
<a name="presenter-and-participant-capabilities-in-a-teams-live-event"></a>Funciones del moderador y participante en un evento de Teams en directo
======================================================

Los eventos de Microsoft Teams en directo admiten varios tipos de participantes. Los participantes pueden tener acceso a varias características de eventos en directo en función de sus roles dentro o fuera de una organización.

Las características de la reunión disponibles son:

- Chat (incluye fotos y adhesivos)
- Notas de la reunión
- Whiteboard
- Grabación
- Archivos

Este artículo describe las funciones de los participantes y qué acceso tienen para las características de los eventos en directo.

## <a name="presenters-and-organizers"></a>Moderadores y organizadores

Entre los moderadores y los organizadores se incluyen los siguientes:

- Moderadores de mi organización
- Moderadores de otras organizaciones. Los moderadores son designados por el organizador y requieren una invitación personal del organizador.

El moderador y el organizador tienen acceso a todas las características de un evento en directo.

## <a name="participants"></a>Participantes

Existen varios tipos de participantes de eventos en directo:

- [Participante del espacio empresarial](#in-tenant-participant)
- [Participante invitado](#guest-participant)
- [Participante externo (federado)](#external-federated-participant)
- [Participante anónimo](#anonymous-participant)

### <a name="in-tenant-participant"></a>Participante del espacio empresarial

El participante del espacio empresarial pertenece a la organización y tiene credenciales para el espacio empresarial. Más información sobre este participante en [Seguridad y Microsoft Teams](teams-security-guide.md#participant-types).

| Eventos en directo |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
|  **Característica**       | Antes de la reunión | Durante una reunión | Después de la reunión |
| Chat | No aplicable | No aplicable | No aplicable |
| Notas de la reunión | Sí | Sí |Sí |
| Whiteboard | Sí | Sí |Sí |
| Grabación | N/D |Sí | Sí |
| Archivos | Sí | Sí | Sí |
|||||||


### <a name="guest-participant"></a>Participante invitado

Un participante invitado es alguien de otra organización que ha sido invitado a acceder a Teams u otros recursos en el espacio empresarial de su organización, basado en la plataforma B2B de Azure Active Directory. Se puede invitar a usuarios invitados a unirse a reuniones periódicas y reuniones de canal. Más información sobre un participante invitado en [Cómo es la experiencia de invitado](guest-experience.md#comparison-of-team-member-and-guest-capabilities).

| Eventos en directo  | | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **Característica**        | Antes de la reunión | Durante una reunión | Después de la reunión |
| Chat | No aplicable | No aplicable | No aplicable |
| Notas de la reunión | Sí | Sí | Sí |
| Whiteboard | No | No | No |
| Grabación | N/D | No | No |
| Archivos | No | No | No |
|||||||


### <a name="external-federated-participant"></a>Participante externo (federado)

Un participante externo es alguien que usa Teams en otra organización que ha sido invitado a unirse a una reunión, pero que de otra manera no tiene acceso a otros recursos compartidos de su organización. Los participantes que son usuarios externos aparecen en la lista de la reunión con el mismo nombre de identidad que tienen en su propia organización. Lea más sobre un participante externo en [Comunicarse con usuarios de otras organizaciones ](communicate-with-users-from-other-organizations.md#external-access).

| Eventos en directo |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
|  **Característica**         | Antes de la reunión | Durante una reunión | Después de la reunión |
| Chat | No aplicable| No aplicable | No aplicable |
| Notas de la reunión | No | No | No |
| Whiteboard | No| No | No |
| Grabación | N/D | No | No |
| Archivos | Sí | Sí | Sí |
|||||||

### <a name="anonymous-participant"></a>Participante anónimo

El participante anónimo es como un usuario externo, pero su identidad no se proyecta en la reunión. En el momento de unirse, escribe manualmente un alias. Más información sobre un participante anónimo en [Seguridad y Microsoft Teams](teams-security-guide.md#participant-types).

| Eventos en directo|  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **Característica**        | Antes de la reunión | Durante una reunión | Después de la reunión |
| Chat | No aplicable | No aplicable | No aplicable |
| Notas de la reunión | N/D | No | N/D |
| Whiteboard | No aplicable | No aplicable | No aplicable |
| Grabación | N/D | No | N/D |
| Archivos | N/D | No | N/D |
|||||||


## <a name="related-topics"></a>Temas relacionados

[Seguridad y Microsoft Teams](teams-security-guide.md)

[Acceso de invitado a Teams](guest-access.md)

[Planear eventos en directo en Yammer](teams-live-events/plan-for-teams-live-events.md)
