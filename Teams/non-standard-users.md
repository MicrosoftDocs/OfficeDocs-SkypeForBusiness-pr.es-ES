---
title: Comportamiento de las aplicaciones de Teams para usuarios no estándar
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre el comportamiento de las aplicaciones de Microsoft Teams para los usuarios no estándar.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 66754565737929ec9d34125ca421c7e3eed9fe65
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278550"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a>Comportamiento de las aplicaciones de Microsoft Teams para usuarios no estándar

En este artículo se describe cómo se comportan las aplicaciones de Teams cuando los usuarios invitados, externos (federados) y anónimos están presentes en un contexto de Teams.

- Un **usuario invitado** es alguien que no es un empleado, un estudiante o un miembro de su organización. Tampoco tiene una cuenta profesional o educativa con su organización.

- Un **usuario externo (federado) pertenece** a otro dominio y no tiene acceso a los equipos ni a los recursos del equipo de su organización.

>[!Note]
> Para ver una comparación más detallada entre los usuarios invitados y los externos, vea la comunicación [con usuarios de otras organizaciones.](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations)

- Un **usuario anónimo es** un concepto en las reuniones de Teams en las que el usuario se ha unido a la reunión a través de un vínculo. El usuario no ha iniciado sesión con su cuenta de Microsoft o de la organización.

## <a name="guest-user-access"></a>Acceso de usuario invitado

### <a name="install-update-and-delete-for-guest-users"></a>Instalar, actualizar y eliminar para usuarios invitados

Los invitados no pueden instalar, actualizar o eliminar aplicaciones en un contexto compartido, como un chat, un canal o una reunión. Pueden instalar, actualizar o eliminar aplicaciones en su ámbito personal mediante extensiones de mensajes y vínculos directos. Los invitados no tienen acceso a la tienda de aplicaciones de Teams.

### <a name="usage-behavior-and-policy-for-guest-users"></a>Comportamiento y directiva de uso para usuarios invitados

Los invitados pueden usar una aplicación si la aplicación fue instalada por un usuario nativo.

Los bots pueden enviar mensajes de forma proactiva a los usuarios invitados, pero los invitados no pueden interactuar con el bot. Los invitados no pueden enviar un mensaje al bot 1:1, @ mencionar al bot ni interactuar con tarjetas adaptables que se comunican con el bot.

Los invitados se ajustarán a las directivas de permisos globales y de toda la organización establecidas para el inquilino host de cualquier aplicación. Es decir, si se bloquea una aplicación para toda la organización host, los invitados tampoco podrán usar la aplicación.

Las directivas de configuración no se aplican a los usuarios invitados. Esto significa que la aplicación anclada por el administrador de la directiva predeterminada no afecta a los usuarios invitados.

## <a name="external-federated-user-access"></a>Acceso de usuarios externos (federados)

### <a name="install-update-and-delete-for-external-users"></a>Instalar, actualizar y eliminar usuarios externos

Los usuarios externos no pueden instalar, actualizar o eliminar aplicaciones en ningún contexto, como un chat, un canal o una reunión personal. No tienen acceso a la tienda de aplicaciones de Teams.

### <a name="usage-behavior-and-policy-for-external-users"></a>Comportamiento y directiva de uso para usuarios externos

Los usuarios externos no pueden usar ninguna aplicación de Teams y, cuando se agrega un usuario externo a un contexto con los usuarios nativos, todos los usuarios (nativos y externos) ya no pueden usar aplicaciones.

Las directivas de aplicación no afectan a los usuarios externos, ya que no pueden usar las aplicaciones de Teams.

## <a name="anonymous-user-in-meetings-access"></a>Acceso anónimo en reuniones

### <a name="install-update-and-delete-for-anonymous-users"></a>Instalar, actualizar y eliminar para usuarios anónimos

Los usuarios anónimos no pueden instalar, actualizar ni eliminar aplicaciones en reuniones.

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>Comportamiento y directiva de uso para usuarios anónimos

Los usuarios anónimos no pueden usar aplicaciones directamente en las reuniones. Los usuarios nativos pueden seguir usando las aplicaciones de reuniones si hay usuarios anónimos presentes. Si una aplicación envía una tarjeta adaptable en el chat, los usuarios anónimos pueden interactuar con la tarjeta.

Los usuarios anónimos heredarán la directiva de permisos predeterminada global a nivel de usuario. Este control permite a los usuarios anónimos interactuar con aplicaciones en reuniones de Teams si la directiva de permisos a nivel de usuario ha habilitado la aplicación. Los usuarios anónimos solo pueden interactuar con aplicaciones que ya están disponibles en una reunión y que no pueden adquirir ni administrar estas aplicaciones.
