---
title: Disponibilidad y uso de las aplicaciones de Teams por diferentes tipos de usuarios
author: ashishguptaiitb
ms.author: guptaashish
ms.reviewer: kojika
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
ms.subservice: teams-apps
search.appverid: MET150
description: Obtenga información sobre cómo funcionan las aplicaciones en Microsoft Teams para invitados, usuarios federados y usuarios anónimos.
ms.localizationpriority: high
ms.date: 09/28/2022
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3511dec4f3238babc3356bafbe2bb69e791e7632
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131319"
---
# <a name="use-of-teams-apps-for-external-attendees-or-guest-from-outside-an-organization"></a>Uso de aplicaciones de Teams para asistentes externos o invitados externos a una organización

Las aplicaciones de Teams permiten la colaboración con personas de fuera de su organización. Como administrador, puede controlar quién puede acceder a los chats, las reuniones y el canal de Teams para colaborar con los usuarios de su organización. Para obtener información detallada, vea [cómo permitir la colaboración con asistentes externos](manage-external-access.md) y [qué pueden hacer los invitados en Teams](guest-access.md). Este artículo se centra en el uso de aplicaciones por parte de personas de fuera de la organización.

Los siguientes tipos de usuarios pueden estar presentes en un chat o reunión de Teams y, si lo permite, pueden usar aplicaciones en Teams.

* Un **usuario invitado** es alguien que no es empleado, estudiante ni miembro de la organización. Tampoco tiene una cuenta profesional o educativa con su organización.

* Un **usuario externo (federado)** es de otro dominio y no tiene acceso a los recursos de Teams de su organización.

* Un **usuario anónimo** es un usuario que se une a una reunión a través de un vínculo. El usuario no ha iniciado sesión con su cuenta de Microsoft ni con la cuenta de su organización.

Para obtener una comparación más detallada entre los usuarios invitados y externos, vea [Comunicarse con usuarios de otras organizaciones](communicate-with-users-from-other-organizations.md).

## <a name="guests"></a>Invitados

### <a name="install-update-and-delete-apps-for-guests"></a>Instalar, actualizar y eliminar aplicaciones para invitados

Los invitados no pueden instalar, actualizar ni eliminar aplicaciones en un contexto compartido, como un chat, un canal o una reunión. Los invitados pueden hacerlo en su ámbito personal mediante extensiones de mensaje y vínculos directos. Los invitados no pueden acceder a la tienda de aplicaciones de Teams desde la aplicación de escritorio de Teams, pero pueden acceder a la tienda con un vínculo directo.

### <a name="usage-behavior-and-policy-for-guests"></a>Comportamiento de uso y directiva para invitados

Los invitados pueden usar una aplicación si la aplicación la instaló el usuario de una organización.

#### <a name="bots-installed-to-a-channel"></a>Bots instalados en un canal

Los invitados pueden mencionar el bot e interactuar con tarjetas adaptables.

#### <a name="personal-bots-installed-with-policies"></a>Bots personales instalados con directivas

* Para cualquier aplicación, los invitados se adhieren a las directivas de permisos globales y de toda la organización establecidas para la organización host. Si una aplicación está bloqueada para toda la organización host, los invitados tampoco podrán usar la aplicación.
* Cualquier bot incluido en la directiva de configuración predeterminada global de la aplicación también se instalará para los invitados.
* Después de instalar un bot, los bots e invitados pueden comunicarse de forma proactiva entre sí.
* No puede quitar un invitado de la directiva global de configuración predeterminada de la aplicación.
* Para evitar que un invitado acceda a bots, puede crear más directivas de configuración de aplicaciones, asignarlas a usuarios internos e instalar bots con las directivas personalizadas.

## <a name="federated-users"></a>Usuarios federados

### <a name="install-update-and-delete-apps-for-federated-users"></a>Instalar, actualizar y eliminar aplicaciones para usuarios federados

Los usuarios federados no pueden instalar, actualizar ni eliminar aplicaciones en ningún contexto, como un chat personal, un canal o una reunión. No tienen acceso a la tienda de aplicaciones de Teams de la organización anfitriona.

### <a name="usage-behavior-and-policy-for-federated-users"></a>Comportamiento de uso y directiva para usuarios federados

* Personas de otras organizaciones se adhieren a la directiva global (predeterminada para toda la organización) de la organización
* Los usuarios de la organización de hospedaje pueden agregar aplicaciones en chats de reuniones con personas de otras organizaciones. Personas de otras organizaciones no pueden agregar aplicaciones en los chats de reuniones, pero pueden interactuar con bots, pestañas y extensiones de mensajes una vez agregados al chat.
* Después de instalar un bot en un chat de reunión, puede comunicarse de forma proactiva con personas de otras organizaciones en ese chat y dichas personas pueden comunicarse con el bot.
* Se aplican las directivas de datos de la organización de hospedaje.
* Se aplican las prácticas de uso compartido de datos de las aplicaciones de terceros compartidas por la organización de dicho usuario.

## <a name="anonymous-users"></a>Usuarios anónimos

### <a name="install-update-and-delete-apps-for-anonymous-users"></a>Instalar, actualizar y eliminar aplicaciones para usuarios anónimos

Los usuarios anónimos no pueden instalar, actualizar ni eliminar aplicaciones en las reuniones.

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>Comportamiento de uso y directiva para usuarios anónimos

Los usuarios anónimos no pueden usar aplicaciones directamente en reuniones. Si una aplicación envía una tarjeta adaptable en el chat, los usuarios anónimos pueden interactuar con la tarjeta. Estos usuarios pueden interactuar con aplicaciones en reuniones de Teams si la directiva de permisos a nivel de usuario habilita la aplicación. Los usuarios anónimos heredan la directiva de permisos predeterminada global a nivel de usuario.

Los usuarios anónimos solo pueden interactuar con las aplicaciones que ya están disponibles en una reunión, pero no pueden adquirir ni administrar dichas aplicaciones. Los usuarios nativos pueden seguir usando las aplicaciones de reuniones incluso cuando los usuarios anónimos asisten a una reunión.

### <a name="allow-anonymous-users-to-use-apps-in-meetings"></a>Permitir que usuarios anónimos usen aplicaciones en reuniones

De forma predeterminada, los usuarios anónimos pueden interactuar con las aplicaciones existentes en una reunión. Los usuarios anónimos no pueden agregar nuevas aplicaciones a una reunión. Puede no permitir que usuarios anónimos interactúen con aplicaciones.

1. Inicie sesión en el Centro de administración de Teams y acceda a **[La configuración](https://admin.teams.microsoft.com/meetings/settings)** de **reuniones** > .

1. En **Participantes**, cambie el botón de alternancia de **Los usuarios anónimos pueden interactuar con aplicaciones en reuniones** a **Desactivado**.

1. Seleccione **Guardar**.

## <a name="related-articles"></a>Artículos relacionados

* [Permitir que usuarios anónimos se unan a reuniones](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings).
* [Administre las directivas de configuración de aplicaciones en Microsoft Teams](teams-app-setup-policies.md).
* [Cómo permitir la colaboración con invitados y participantes externos](manage-external-access.md).
* [Qué pueden hacer los invitados en Teams](guest-access.md)
