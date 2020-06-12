---
title: Funciones del moderador y participante en una reunión de Teams
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
description: Obtenga información sobre las funciones de moderadores y participantes en una reunión de Teams.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: c8433d4caa0defbe83114ac4027c10b6bf61a725
ms.sourcegitcommit: 862ba1d2b3bd4622b1b0baa15096c29c591cc6c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2020
ms.locfileid: "44702695"
---
<a name="presenter-and-participant-capabilities-in-a-teams-meeting"></a>Funciones del moderador y participante en una reunión de Teams
======================================================

Las reuniones de Microsoft Teams admiten varios tipos de participantes. Los participantes pueden tener acceso a varias características de reunión en función de sus roles dentro o fuera de una organización.

Las características de la reunión disponibles son:

- Chat (incluye fotos y adhesivos)
- Notas de la reunión
- Whiteboard
- Grabación
- Archivos
- Programar una reunión (solo para reuniones)

Este artículo describe las funciones de los participantes y qué acceso tienen para las características de las reuniones.

## <a name="presenters-and-organizers"></a>Moderadores y organizadores

Entre los moderadores y los organizadores se incluyen los siguientes:

- Moderadores de mi organización
- Moderadores de otras organizaciones: esto incluye los participantes anónimos y externos. Los moderadores son designados por el organizador y requieren una invitación personal del organizador.

El moderador y el organizador tienen acceso a todas las características de una reunión o evento en directo.

## <a name="participants"></a>Participantes

Existen varios tipos de participantes en una reunión:

- [Participante del espacio empresarial](#in-tenant-participant)
- [Participante invitado](#guest-participant)
- [Participante externo (federado)](#external-federated-participant)
- [Participante anónimo](#anonymous-participant)

### <a name="in-tenant-participant"></a>Participante del espacio empresarial

El participante del espacio empresarial pertenece a la organización y tiene credenciales para el espacio empresarial. Más información sobre este participante en [Seguridad y Microsoft Teams](teams-security-guide.md#participant-types).

|Reunión  |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **Característica**        | Antes de la reunión | Durante una reunión | Después de la reunión |
| Chat | Sí | Sí | Sí |
| Notas de la reunión | Sí | Sí |Sí |
| Whiteboard | Sí | Sí |Sí |
| Grabación | N/D |Sí | Sí |
| Archivos | Sí | Sí | Sí |
| Programar una reunión | Sí | N/D | N/D |
|||||||

### <a name="guest-participant"></a>Participante invitado

Un participante invitado es alguien de otra organización que ha sido invitado a acceder a Teams u otros recursos en el espacio empresarial de su organización, basado en la plataforma B2B de Azure Active Directory. Se puede invitar a usuarios invitados a unirse a reuniones periódicas y reuniones de canal. Más información sobre un participante invitado en [Cómo es la experiencia de invitado](guest-experience.md#comparison-of-team-member-and-guest-capabilities).

| Reunión |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **Característica**        | Antes de la reunión | Durante una reunión | Después de la reunión |
| Chat | Sí | Sí | Sí |
| Notas de la reunión | Sí | Sí | Sí |
| Whiteboard | No | No |No |
| Grabación | N/D |No | No |
| Archivos | Sí | Sí | Sí |
| Programar una reunión | No | N/D | N/D |
|||||||

### <a name="external-federated-participant"></a>Participante externo (federado)

Un participante externo es alguien que usa Teams en otra organización que ha sido invitado a unirse a una reunión, pero que de otra manera no tiene acceso a otros recursos compartidos de su organización. Los participantes que son usuarios externos aparecen en la lista de la reunión con el mismo nombre de identidad que tienen en su propia organización. Lea más sobre un participante externo en [Comunicarse con usuarios de otras organizaciones ](communicate-with-users-from-other-organizations.md#external-access).

| Reunión ||
|-|-|-|
| **Característica** |||
| Chat | Sí |
| Notas de la reunión | N/D |  
| Whiteboard | N/D |
| Grabación | N/D |  
| Archivos | N/D |
| Programar una reunión | N/D |
|||

### <a name="anonymous-participant"></a>Participante anónimo

El participante anónimo es como un usuario externo, pero su identidad no se proyecta en la reunión. En el momento de unirse, escribe manualmente un alias. Más información sobre un participante anónimo en [Seguridad y Microsoft Teams](teams-security-guide.md#participant-types).

| Reunión  | | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **Característica**        | Antes de la reunión | Durante una reunión | Después de la reunión |
| Chat | No aplicable | Sí | No aplicable |
| Notas de la reunión | N/D | No | N/D |
| Whiteboard | N/D | No | N/D |
| Grabación | N/D | No | N/D |
| Archivos | N/D | No | N/D |
| Programar una reunión | N/D | No aplicable | N/D |
|||||||

## <a name="related-topics"></a>Temas relacionados

[Seguridad y Microsoft Teams](teams-security-guide.md)

[Acceso de invitado a Teams](guest-access.md)
