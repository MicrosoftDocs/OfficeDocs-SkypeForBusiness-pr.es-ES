---
title: Establecer configuración de actualización y coexistencia
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: Obtenga más información sobre cómo configurar la coexistencia y la configuración de actualización para todos los usuarios de la organización a la vez, o para un único o un conjunto de usuarios de su organización.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: a20e8c355df4103980dc9da460d003382c721800
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940610"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a>Establecer configuración de actualización y coexistencia


Al actualizar los usuarios de Skype empresarial para que usen Teams, dispone de varias opciones para ayudarle a convertirlo en un proceso sin problemas para sus usuarios. Tiene la opción de hacer la coexistencia y la configuración de actualización de todos los usuarios de la organización a la vez, o puede realizar cambios de configuración para un único o un conjunto de usuarios de su organización. Tenga en cuenta que es posible que las versiones más antiguas de clientes de Skype empresarial no cumplan con esta configuración. Para obtener más información sobre las versiones de cliente de Skype empresarial, vaya a la [Página de descargas y actualizaciones de Skype empresarial](https://docs.microsoft.com/skypeforbusiness/software-updates). 

Puede obtener una mejor comprensión de los modos disponibles para usted leyendo [comprender Microsoft Teams y la coexistencia e interoperabilidad de Skype](teams-and-skypeforbusiness-coexistence-and-interoperability.md) empresarial o [coexistencia con Skype empresarial](coexistence-chat-calls-presence.md).  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>Establecer las opciones de actualización para todos los usuarios de la organización

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**

1. En el [centro de administración de Microsoft Teams](https://admin.teams.microsoft.com/), en el navegación de la izquierda, vaya a la actualización de la configuración de equipos de la **organización**  >  **Teams upgrade**. 

2. En la parte superior de la página de **actualización de Teams** , modifique las siguientes opciones como desee.
    - Establecer el modo de **coexistencia** .
        - **Islas** : Use esta configuración si quiere que los usuarios puedan usar Skype empresarial y Teams de forma simultánea.
        - **Solo para Skype empresarial** : Use esta configuración si desea que los usuarios solo usen Skype empresarial.
        - **Skype empresarial con colaboración de Teams** : Use esta configuración si quiere que los usuarios usen Skype empresarial además de usar Teams para la colaboración en grupo (canales).
        - **Skype empresarial con colaboración y reuniones de Teams** : Use esta opción si quiere que los usuarios usen Skype empresarial además de usar Teams para la colaboración de grupo (canales) y las reuniones de Teams.
        - **Solo equipos** : Use esta configuración si desea que los usuarios solo usen equipos de equipo. Tenga en cuenta que, incluso con esta configuración, los usuarios pueden unirse a reuniones hospedadas en Skype empresarial.
        
    - Establezca **notificar a los usuarios de Skype empresarial que Teams está disponible para su actualización**. Si activa esta opción, se le indicará a los usuarios de Skype empresarial que pronto se actualizarán a la aplicación de Teams.
    - Establezca la **aplicación preferida para que los usuarios se unan a reuniones de Skype empresarial**. Esta opción determina qué aplicación se usa para unirse a reuniones de Skype empresarial y se acepta independientemente del valor del modo de coexistencia.
      - **Aplicación reuniones de Skype**
      - **Skype empresarial con características limitadas**
    - Establezca si desea **descargar la aplicación de Teams en segundo plano para los usuarios de Skype empresarial**.  Esta configuración descarga silenciosamente la aplicación de Teams para los usuarios que ejecutan Skype empresarial en Windows. Solo se admite si el modo de coexistencia para el usuario solo es de equipos o si las notificaciones de actualización pendiente están habilitadas en Skype empresarial.
3. Haga clic en **Guardar** después de realizar los cambios.

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>Establecer las opciones de actualización para un único usuario de su organización

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**

1. En el navegación de la izquierda, vaya a **usuarios**y, a continuación, seleccione el usuario de la lista. 
2. En la pestaña **cuenta** del usuario, en **actualización de Teams**, haga clic en **Editar**.
3. Puede establecer el **modo de coexistencia**. Elija una de las siguientes opciones:
     - **Usar la configuración de toda la organización** : Use esta configuración si desea que el usuario Use la configuración en la configuración de **toda la organización** . 
     - **Islas** : Use esta configuración si quiere que el usuario pueda usar tanto Skype empresarial como Teams. 
     - **Solo para Skype empresarial** : Use esta configuración si desea que el usuario use Skype empresarial.
     - **Skype empresarial con colaboración de Teams** : Use esta configuración si desea que el usuario use Skype empresarial además de usar Teams para la colaboración en grupo (canales).
      - **Skype empresarial con colaboración y reuniones de Teams** : Use esta configuración si desea que el usuario use Skype empresarial además de usar Teams para la colaboración grupal (canales) y las reuniones de Teams.
     - **Solo equipos** : Use esta configuración si desea que el usuario solo use equipos. El usuario seguirá pudiendo unirse a reuniones de Skype empresarial.
4. Si selecciona cualquier **modo de coexistencia** distinto de **usar la configuración de toda la organización**, tendrá la opción de habilitar las notificaciones en la aplicación Skype empresarial del usuario que la actualización a teams estará disponible próximamente. Puede habilitar esta notificación para el usuario activando la opción **notificar al usuario de Skype empresarial** .
5. Haga clic en **Guardar** después de realizar los cambios.

### <a name="related-topics"></a>Temas relacionados
[Actualizar de Skype empresarial a teams: para administradores de ti](upgrade-to-teams-on-prem-overview.md)

[Planear el viaje](upgrade-plan-journey.md)

[Comprender el viaje de coexistencia y actualización de Skype empresarial y Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md)
