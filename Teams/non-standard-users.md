---
title: Comportamiento de las aplicaciones de Teams en función de los tipos de usuarios
author: ashishguptaiitb
ms.author: guptaashish
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.subservice: teams-apps
search.appverid: MET150
description: Obtenga información sobre cómo funcionan las aplicaciones en Microsoft Teams de forma diferente para invitados, usuarios federados y usuarios anónimos.
ms.localizationpriority: high
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e39aac93c7311785c0f740eded8a0021e321c43
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837500"
---
# <a name="behavior-of-microsoft-teams-apps-based-on-types-of-in-meeting-users"></a>Comportamiento de las aplicaciones de Microsoft Teams en función de los tipos de usuarios en reunión

Las aplicaciones de Teams se comportan cuando los usuarios invitados, externos (federados) y anónimos están presentes en un contexto de Teams.

* Un **usuario invitado** es alguien que no es empleado, estudiante ni miembro de la organización. Tampoco tiene una cuenta profesional o educativa con su organización.

* Un **usuario externo (federado)** es de otro dominio y no tiene acceso a los recursos de Teams de su organización.

  > [!Note]
  > Para obtener una comparación más detallada entre los usuarios invitados y externos, vea [Comunicarse con usuarios de otras organizaciones](./communicate-with-users-from-other-organizations.md).

* Un **usuario anónimo** es un usuario que se une a una reunión a través de un vínculo. El usuario no ha iniciado sesión con su cuenta de Microsoft ni con la cuenta de su organización.

## <a name="guests"></a>Invitados

### <a name="install-update-and-delete-for-guests"></a>Instalar, actualizar y eliminar invitados

Los invitados no pueden instalar, actualizar ni eliminar aplicaciones en un contexto compartido, como un chat, un canal o una reunión. Los invitados pueden hacerlo en su ámbito personal mediante extensiones de mensaje y vínculos directos. Los invitados no pueden acceder a la tienda de aplicaciones de Teams desde la aplicación de escritorio de Teams, pero pueden acceder a la tienda con un vínculo directo.

### <a name="usage-behavior-and-policy-for-guests"></a>Comportamiento de uso y directiva para invitados

Los invitados pueden usar una aplicación si la aplicación fue instalada por un usuario nativo.

#### <a name="bots-installed-to-a-channel"></a>Bots instalados en un canal

Los invitados pueden mencionar el bot e interactuar con tarjetas adaptables.

#### <a name="personal-bots-installed-with-policies"></a>Bots personales instalados con directivas

* Para cualquier aplicación, los invitados se adhieren a las directivas de permisos globales y de toda la organización establecidas para la organización host. Si una aplicación está bloqueada para toda la organización host, los invitados tampoco podrán usar la aplicación.
* Cualquier bot incluido en la directiva de configuración predeterminada global de la aplicación también se instalará para los invitados.
* Después de instalar un bot, los bots pueden comunicarse de forma proactiva con los invitados y los invitados pueden comunicarse de nuevo con los bots.
* No puede quitar un invitado de la directiva global de configuración predeterminada de la aplicación.
* Para evitar que un invitado acceda a bots, puede crear más directivas de configuración de aplicaciones, asignarlas a usuarios internos e instalar bots con las directivas personalizadas.

## <a name="federated-users"></a>Usuarios federados

### <a name="install-update-and-delete-for-federated-users"></a>Instalar, actualizar y eliminar usuarios federados

Los usuarios federados no pueden instalar, actualizar ni eliminar aplicaciones en ningún contexto, como un chat personal, un canal o una reunión. No tienen acceso a la tienda de aplicaciones de Teams de la organización anfitriona.

### <a name="usage-behavior-and-policy-for-federated-users"></a>Comportamiento de uso y directiva para usuarios federados

* Personas de otras organizaciones se adhieren a la directiva global (predeterminada para toda la organización) de la organización
* Los usuarios de la organización de hospedaje pueden agregar aplicaciones en chats de reuniones con personas de otras organizaciones. Personas de otras organizaciones no pueden agregar aplicaciones en los chats de reuniones, pero pueden interactuar con bots, pestañas y extensiones de mensajes una vez agregados al chat.
* Después de instalar un bot en un chat de reunión, puede comunicarse de forma proactiva con personas de otras organizaciones en ese chat y dichas personas pueden comunicarse con el bot.
* Se aplican las directivas de datos de la organización de hospedaje.
* Se aplican las prácticas de uso compartido de datos de las aplicaciones de terceros compartidas por la organización de dicho usuario.

## <a name="anonymous-users"></a>Usuarios anónimos

### <a name="install-update-and-delete-for-anonymous-users"></a>Instalar, actualizar y eliminar para usuarios anónimos

Los usuarios anónimos no pueden instalar, actualizar ni eliminar aplicaciones en las reuniones.

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>Comportamiento de uso y directiva para usuarios anónimos

Los usuarios anónimos no pueden usar aplicaciones directamente en reuniones. Si una aplicación envía una tarjeta adaptable en el chat, los usuarios anónimos pueden interactuar con la tarjeta. Estos usuarios pueden interactuar con aplicaciones en reuniones de Teams si la directiva de permisos a nivel de usuario habilita la aplicación. Los usuarios anónimos heredan la directiva de permisos predeterminada global a nivel de usuario.

Los usuarios anónimos solo pueden interactuar con las aplicaciones que ya están disponibles en una reunión, pero no pueden adquirir ni administrar dichas aplicaciones. Los usuarios nativos pueden seguir usando las aplicaciones de reuniones incluso cuando los usuarios anónimos asisten a una reunión.

## <a name="see-also"></a>Vea también

* [Permitir que usuarios anónimos se unan a reuniones](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings).
* [Administre las directivas de configuración de aplicaciones en Microsoft Teams](teams-app-setup-policies.md).
