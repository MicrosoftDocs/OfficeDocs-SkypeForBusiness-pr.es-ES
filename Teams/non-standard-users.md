---
title: Teams comportamiento de las aplicaciones en función de los tipos de usuarios
author: guptaashish
ms.author: guptaashish
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo se comportan las aplicaciones de Microsoft Teams para diferentes tipos de usuarios.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: a407564986d5e4c758d39e2684e5c068539bb9dc
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922471"
---
# <a name="microsoft-teams-apps-behavior-based-on-types-of-users"></a>Microsoft Teams el comportamiento de las aplicaciones en función de los tipos de usuarios

Teams aplicaciones se comportan cuando los usuarios invitados, externos (federados) y anónimos están presentes en un contexto Teams.

* Un **usuario invitado** es alguien que no es empleado, estudiante ni miembro de la organización. Tampoco tiene una cuenta profesional o educativa con su organización.

* Un **usuario externo (federado)** pertenece a otro dominio y no tiene acceso a los equipos ni a los recursos del equipo de su organización.

  > [!Note]
  > Para obtener una comparación más detallada de los usuarios invitados y externos, [vea Comunicarse con usuarios de otras organizaciones](./communicate-with-users-from-other-organizations.md).

* Un **usuario anónimo** es un concepto de Teams reuniones en las que el usuario se ha unido a la reunión mediante un vínculo. El usuario no ha iniciado sesión con su cuenta de Microsoft o de la organización.

## <a name="guest-users"></a>Usuarios invitados

### <a name="install-update-and-delete-for-guest-users"></a>Instalar, actualizar y eliminar para usuarios invitados

Los invitados no pueden instalar, actualizar ni eliminar aplicaciones en un contexto compartido, como un chat, un canal o una reunión, pero pueden acceder a su ámbito personal mediante extensiones de mensajes y vínculos directos. Los invitados no tienen acceso a la tienda de aplicaciones Teams desde la aplicación de escritorio Teams, pero pueden acceder a ella con un vínculo directo.

### <a name="usage-behavior-and-policy-for-guest-users"></a>Comportamiento de uso y directiva para usuarios invitados

Los invitados pueden usar una aplicación si la aplicación fue instalada por un usuario nativo.

#### <a name="bots-installed-to-a-channel"></a>Bots instalados en un canal

Los usuarios invitados pueden mencionar el bot e interactuar con tarjetas adaptables.

#### <a name="personal-bots-installed-with-policies"></a>Bots personales instalados con directivas

* Los invitados se adhieren a las directivas de permisos globales y de toda la organización establecidas para el inquilino host para cualquier aplicación. Si una aplicación está bloqueada para toda la organización host, los invitados tampoco podrán usar la aplicación.
* Cualquier bot incluido en la directiva de configuración predeterminada global de la aplicación también se instalará para los invitados.
* Después de instalar un bot, los bots pueden comunicarse de forma proactiva con los invitados y los invitados pueden comunicarse de nuevo con los bots.
* No puede quitar un invitado de la directiva global de configuración predeterminada de la aplicación.
* Para evitar que un invitado acceda a bots, puede crear más directivas de configuración de aplicaciones, asignarlas a usuarios internos e instalar bots con las directivas personalizadas.

## <a name="external-federated-users"></a>Usuarios externos (federados)

### <a name="install-update-and-delete-for-external-users"></a>Instalar, actualizar y eliminar usuarios externos

Los usuarios externos no pueden instalar, actualizar ni eliminar aplicaciones en ningún contexto, como un personal, chat, canal o reunión. No tienen acceso a la tienda de aplicaciones Teams de la organización de hospedaje.

### <a name="usage-behavior-and-policy-for-external-users"></a>Comportamiento de uso y directiva para usuarios externos

* Los usuarios de otras organizaciones se adhieren a la directiva global (predeterminada para toda la organización) de la organización
* Los usuarios de la organización de hospedaje pueden agregar aplicaciones en chats de reuniones con personas de otras organizaciones. Los usuarios de otras organizaciones no pueden agregar aplicaciones en los chats de reuniones, pero pueden interactuar con bots, pestañas y extensiones de mensajes una vez agregados al chat.
* Después de instalar un bot en un chat de reunión, puede comunicarse de forma proactiva con personas de otras organizaciones en ese chat y dichas personas pueden comunicarse con el bot.
* Se aplican las directivas de datos de la organización de hospedaje, así como las prácticas de uso compartido de datos de cualquier aplicación de terceros compartida por la organización de ese usuario.

## <a name="anonymous-users"></a>Usuarios anónimos

### <a name="install-update-and-delete-for-anonymous-users"></a>Instalar, actualizar y eliminar para usuarios anónimos

Los usuarios anónimos no pueden instalar, actualizar ni eliminar aplicaciones en las reuniones.

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>Comportamiento de uso y directiva para usuarios anónimos

Los usuarios anónimos no pueden usar aplicaciones directamente en reuniones. Los usuarios anónimos heredan la directiva de permisos predeterminada global a nivel de usuario. Si una aplicación envía una tarjeta adaptable en el chat, los usuarios anónimos pueden interactuar con la tarjeta. Estos usuarios pueden interactuar con aplicaciones en Teams reuniones si la directiva de permisos a nivel de usuario habilita la aplicación.

Los usuarios anónimos solo pueden interactuar con las aplicaciones que ya están disponibles en una reunión y no pueden adquirir ni administrar dichas aplicaciones. Los usuarios nativos pueden seguir usando las aplicaciones de reuniones incluso cuando los usuarios anónimos asisten a una reunión.

## <a name="see-also"></a>Vea también

* [Permitir que usuarios anónimos se unan a reuniones](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings).
* [Administrar directivas de configuración de aplicaciones en Microsoft Teams](teams-app-setup-policies.md).
