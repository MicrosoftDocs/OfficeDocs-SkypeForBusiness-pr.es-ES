---
title: Teams de aplicaciones para usuarios no estándar
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo las aplicaciones Microsoft Teams se comportan para los usuarios no estándar.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: d7b79371cdc8ff5109bf67b1c78639106a83a95e
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796654"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a>Microsoft Teams de aplicaciones para usuarios no estándar

En este artículo se describe cómo se comportan las aplicaciones de Teams cuando los usuarios invitados, externos (federados) y anónimos están presentes en Teams contexto.

- Un **usuario invitado** es alguien que no es empleado, estudiante o miembro de su organización. Tampoco tiene una cuenta profesional o educativa con su organización.

- Un **usuario externo (federado)** pertenece a otro dominio y no tiene acceso a los equipos ni a los recursos del equipo de su organización.

  > [!Note]
  > Para obtener una comparación más detallada de los usuarios invitados frente a los externos, vea [Comunicarse con usuarios de otras organizaciones.](./communicate-with-users-from-other-organizations.md)

- Un **usuario anónimo** es un concepto en Teams reuniones en las que el usuario se ha unido a la reunión a través de un vínculo. El usuario no ha iniciado sesión con su cuenta de Microsoft u organización.

## <a name="guest-users"></a>Usuarios invitados

### <a name="install-update-and-delete-for-guest-users"></a>Instalar, actualizar y eliminar para usuarios invitados

Los invitados no pueden instalar, actualizar o eliminar aplicaciones en un contexto compartido, como un chat, un canal o una reunión, pero pueden hacerlo en su ámbito personal mediante extensiones de mensajes y vínculos directos. Los invitados no tienen acceso a la tienda de aplicaciones Teams desde la aplicación de escritorio Teams, pero pueden acceder a ella con un vínculo directo.

### <a name="usage-behavior-and-policy-for-guest-users"></a>Comportamiento y directiva de uso para usuarios invitados 

Los invitados pueden usar una aplicación si la aplicación la instaló un usuario nativo.

#### <a name="bots-installed-to-a-channel"></a>Bots instalados en un canal

Los bots pueden enviar mensajes de forma proactiva a los usuarios invitados, pero los invitados no pueden interactuar con el bot. Los invitados no pueden enviar mensajes al bot uno a uno, mencionar el bot o interactuar con tarjetas adaptables que se comunican con el bot.

#### <a name="personal-bots-installed-with-policies"></a>Bots personales instalados con directivas

- Los invitados se ajustarán a las directivas de permisos globales y de toda la organización establecidas para el inquilino del host para cualquier aplicación. Si una aplicación está bloqueada para toda la organización host, los invitados tampoco pueden usar la aplicación.
- Los bots incluidos en la directiva de configuración predeterminada global de la aplicación también se instalarán para los invitados.
- Una vez instalado un bot, los bots pueden comunicarse proactivamente con los invitados y los invitados pueden comunicarse de nuevo con los bots.
- No puede quitar un invitado de la directiva de configuración de aplicaciones predeterminada global.
- Para evitar que los invitados accedan a bots, puede crear más directivas de configuración de aplicaciones, asignarlas a usuarios internos e instalar bots con las directivas personalizadas.

## <a name="external-federated-users"></a>Usuarios externos (federados)

### <a name="install-update-and-delete-for-external-users"></a>Instalar, actualizar y eliminar para usuarios externos

Los usuarios externos no pueden instalar, actualizar ni eliminar aplicaciones en ningún contexto, como un chat, un canal o una reunión personal. No tienen acceso a la tienda de aplicaciones Teams de la organización de hospedaje.

### <a name="usage-behavior-and-policy-for-external-users"></a>Comportamiento de uso y directiva para usuarios externos

- Las personas de otras organizaciones se adhieren a la directiva global (predeterminada para toda la organización) de la organización de hospedaje
- Los usuarios de la organización de hospedaje pueden agregar aplicaciones en chats de reunión con personas de otras organizaciones. Los usuarios de otras organizaciones no pueden agregar aplicaciones en chats de reunión, pero pueden interactuar con bots, pestañas y extensiones de mensajes una vez agregados al chat.
- Después de instalar un bot en un chat de reunión, puede comunicarse proactivamente con personas de otras organizaciones en ese chat y esas personas pueden comunicarse con el bot.
- Se aplican las directivas de datos de la organización de hospedaje, así como las prácticas de uso compartido de datos de las aplicaciones de terceros compartidas por la organización de ese usuario.

## <a name="anonymous-users"></a>Usuarios anónimos

### <a name="install-update-and-delete-for-anonymous-users"></a>Instalar, actualizar y eliminar para usuarios anónimos

Los usuarios anónimos no pueden instalar, actualizar ni eliminar aplicaciones en reuniones.

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>Comportamiento y directiva de uso para usuarios anónimos

Los usuarios anónimos no pueden usar directamente las aplicaciones en las reuniones. Los usuarios nativos pueden seguir usando las aplicaciones de reuniones si hay usuarios anónimos presentes. Si una aplicación envía una tarjeta adaptable en el chat, los usuarios anónimos pueden interactuar con la tarjeta. Para obtener más información, lea [Permitir que usuarios anónimos se unan a reuniones.](/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings)

Los usuarios anónimos heredarán la directiva de permisos predeterminada global a nivel de usuario. Pueden interactuar con las aplicaciones en Teams reuniones si la directiva de permisos de nivel de usuario ha habilitado la aplicación. Los usuarios anónimos solo pueden interactuar con aplicaciones que ya están disponibles en una reunión y que no pueden adquirir ni administrar estas aplicaciones.
