---
title: Establecer configuración de actualización y coexistencia
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: Obtenga información sobre cómo establecer la configuración de coexistencia y actualización para todos los usuarios de su organización a la vez, o para un único o conjunto de usuarios de su organización.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 52e035f3940237309a1a8bab0211ccaad243b004
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117078"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a>Establecer configuración de actualización y coexistencia


Al actualizar los usuarios de Skype Empresarial para usar Teams, tiene varias opciones para ayudarle a que sea un proceso sin problemas para los usuarios. Tiene la opción de realizar la configuración de coexistencia y actualización para todos los usuarios de su organización a la vez, o puede realizar cambios de configuración para un único o conjunto de usuarios de su organización. Tenga en cuenta que las versiones anteriores de los clientes de Skype Empresarial pueden no respetar esta configuración. Para obtener más información sobre las versiones de cliente de Skype Empresarial, vaya a la página descargas y [actualizaciones de Skype Empresarial.](/skypeforbusiness/software-updates) 

Puede comprender mejor los modos que están disponibles al leer Comprender la coexistencia e interoperabilidad de [Microsoft Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) y Skype Empresarial o La coexistencia con Skype [Empresarial.](coexistence-chat-calls-presence.md)  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>Establecer opciones de actualización para todos los usuarios de su organización

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**

1. En el [Centro de administración de Microsoft Teams,](https://admin.teams.microsoft.com/)en el panel de navegación izquierdo, vaya a Configuración **de** toda la organización Actualización  >  **de Teams.** 

2. En la parte superior de la **página de actualización de Teams,** modifique las opciones siguientes como desee.
    - Establecer el **modo coexistencia.**
        - **Islas:** use esta configuración si desea que los usuarios puedan usar Skype Empresarial y Teams simultáneamente.
        - **Solo Skype Empresarial:** use esta configuración si quiere que los usuarios solo usen Skype Empresarial.
        - **Skype Empresarial con la colaboración de Teams:** use esta configuración si quiere que los usuarios usen Skype Empresarial, además de usar Teams para la colaboración grupal (canales).
        - Skype Empresarial con la colaboración y las reuniones de **Teams:** use esta configuración si quiere que los usuarios usen Skype Empresarial, además de usar Teams para la colaboración de grupo (canales) y reuniones de Teams.
        - **Solo Teams:** use esta configuración si desea que los usuarios solo usen Teams. Tenga en cuenta que, incluso con esta configuración, los usuarios aún pueden unirse a reuniones hospedadas en Skype Empresarial.
        
    - Establezca **Notificar a los usuarios de Skype Empresarial que Teams está disponible para la actualización.** Si activa esta opción, le dirá a los usuarios de Skype Empresarial que pronto se actualizarán a la aplicación Teams.
    - Establezca la **aplicación Preferida para que los usuarios se unan a las reuniones de Skype Empresarial.** Esta configuración determina qué aplicación se usa para unirse a reuniones de Skype Empresarial y se respeta independientemente del valor del modo de coexistencia.
      - **Aplicación Reuniones de Skype**
      - **Skype Empresarial con características limitadas**
    - Establezca si desea descargar la aplicación Teams en segundo plano para **los usuarios de Skype Empresarial.**  Esta configuración descarga de forma silenciosa la aplicación Teams para los usuarios que ejecutan Skype Empresarial en Windows. Solo se respeta si el modo de coexistencia del usuario es Solo Teams o si las notificaciones de actualización pendiente están habilitadas en Skype Empresarial.
3. Haga **clic en Guardar** después de realizar los cambios.

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>Establecer opciones de actualización para un solo usuario de la organización

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**

1. En el panel de navegación izquierdo, vaya **a Usuarios** y, a continuación, seleccione el usuario de la lista. 
2. En la **pestaña Cuenta** del usuario, en Actualización **de Teams,** haga clic en **Editar.**
3. Puede establecer el modo **coexistencia.** Elija una de las siguientes opciones:
     - **Usar la configuración de toda la** organización: use esta configuración si desea que el usuario use la configuración de toda **la** organización. 
     - **Islas:** use esta configuración si quiere que el usuario pueda usar Skype Empresarial y Teams. 
     - **Solo Skype Empresarial:** use esta configuración si quiere que el usuario use Skype Empresarial.
     - **Colaboración de Skype Empresarial con Teams:** use esta configuración si desea que el usuario use Skype Empresarial, además de usar Teams para la colaboración grupal (canales).
      - Skype Empresarial con la colaboración y las reuniones de **Teams:** use esta configuración si quiere que el usuario use Skype Empresarial, además de usar Teams para la colaboración grupal (canales) y las reuniones de Teams.
     - **Solo Teams:** use esta configuración si desea que el usuario use solo Teams. El usuario podrá seguir unirse a las reuniones de Skype Empresarial.
4. Si selecciona  cualquier modo de coexistencia que no sea Usar la configuración de toda la **organización,** tiene la opción de habilitar las notificaciones en la aplicación de Skype Empresarial del usuario que actualicen a Teams próximamente. Puede habilitar esta notificación para el usuario activando la opción Notificar al usuario **de Skype** Empresarial.
5. Haga **clic en Guardar** después de realizar los cambios.

### <a name="related-topics"></a>Temas relacionados
[Planear el viaje](upgrade-plan-journey.md)

[Comprender el viaje de coexistencia y actualización de Skype Empresarial y Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md)