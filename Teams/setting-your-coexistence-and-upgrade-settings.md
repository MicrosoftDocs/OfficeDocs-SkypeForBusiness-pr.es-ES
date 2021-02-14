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
description: Obtenga información sobre cómo establecer la configuración de coexistencia y actualización para todos los usuarios de la organización a la vez, o para un único o conjunto de usuarios de la organización.
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


Cuando actualiza sus usuarios de Skype Empresarial para que usen Teams, tiene varias opciones para ayudarle a que sea un proceso sin problemas para sus usuarios. Tiene la opción de establecer la coexistencia y la actualización de todos los usuarios de la organización a la vez, o puede realizar cambios de configuración para un solo usuario o conjunto de usuarios de la organización. Tenga en cuenta que es posible que las versiones anteriores de clientes de Skype Empresarial no respetan esta configuración. Para obtener más información sobre las versiones de los clientes de Skype Empresarial, vaya a la página de actualizaciones y [descargas de Skype Empresarial.](https://docs.microsoft.com/skypeforbusiness/software-updates) 

Puede comprender mejor los modos de coexistencia e interoperabilidad o coexistencia de [Microsoft Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) y Skype Empresarial con [Skype Empresarial.](coexistence-chat-calls-presence.md)  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>Establecer opciones de actualización para todos los usuarios de la organización

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**

1. En el [Centro de administración de Microsoft Teams,](https://admin.teams.microsoft.com/)en el panel de navegación izquierdo, vaya a **la** actualización de Teams para  >  **toda la organización.** 

2. En la parte superior de la **página de actualización de Teams,** modifique las siguientes opciones como desee.
    - Establezca el modo **de coexistencia.**
        - **Islas:** use esta opción si desea que los usuarios puedan usar Skype Empresarial y Teams simultáneamente.
        - **Skype Empresarial solo:** use esta configuración si desea que los usuarios solo usen Skype Empresarial.
        - **Skype Empresarial con colaboración de Teams:** use esta configuración si quiere que los usuarios usen Skype Empresarial, además de usar Teams para la colaboración en grupo (canales).
        - **Skype Empresarial con** colaboración y reuniones de Teams: use esta opción si quiere que los usuarios usen Skype Empresarial, además de Teams para colaborar en grupo (canales) y reuniones de Teams.
        - **Solo teams:** use esta configuración si quiere que los usuarios solo usen Teams. Tenga en cuenta que, incluso con esta configuración, los usuarios aún pueden unirse a reuniones hospedadas en Skype Empresarial.
        
    - Establezca **Notificar a los usuarios de Skype Empresarial que Teams está disponible para la actualización.** Si activa esta opción, se le dirá a los usuarios de Skype Empresarial que pronto se actualizarán a la aplicación Teams.
    - Establezca la **aplicación preferida para que los usuarios se unan a reuniones de Skype Empresarial.** Esta configuración determina qué aplicación se usa para unirse a reuniones de Skype Empresarial y se respeta independientemente del valor del modo de coexistencia.
      - **Aplicación Reuniones de Skype**
      - **Skype Empresarial con características limitadas**
    - Configure si desea **descargar la aplicación Teams en segundo plano para los usuarios de Skype Empresarial.**  Esta configuración descarga de forma silenciosa la aplicación Teams para los usuarios que ejecutan Skype Empresarial en Windows. Solo se respeta si el modo de coexistencia del usuario es Solo Teams o si las notificaciones de actualización pendiente están habilitadas en Skype Empresarial.
3. Haga **clic en** Guardar después de realizar los cambios.

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>Establecer opciones de actualización para un único usuario de la organización

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**

1. En el panel de navegación izquierdo, vaya **a Usuarios** y, a continuación, seleccione el usuario de la lista. 
2. En la **pestaña Cuenta** del usuario, en La actualización **de Teams,** haga clic en **Editar.**
3. Puede establecer el modo **de coexistencia.** Elija una de las siguientes opciones:
     - **Usar la configuración para toda** la organización: use esta opción si quiere que el usuario use la configuración de toda **la** organización. 
     - **Islas:** use esta configuración si desea que el usuario pueda usar Skype Empresarial y Teams. 
     - **Skype Empresarial solo:** use esta configuración si desea que el usuario use Skype Empresarial.
     - **Skype Empresarial con colaboración de Teams:** use esta opción si quiere que el usuario use Skype Empresarial, además de teams para la colaboración en grupo (canales).
      - **Skype Empresarial con** colaboración y reuniones de Teams: use esta opción si quiere que el usuario use Skype Empresarial, además de Teams para colaborar en grupo (canales) y reuniones de Teams.
     - **Solo teams:** use esta configuración si quiere que el usuario use solo Teams. El usuario aún podrá unirse a reuniones de Skype Empresarial.
4. Si selecciona  un modo de coexistencia que no sea Usar la configuración para toda la **organización,** tiene la opción de habilitar las notificaciones en la aplicación Skype Empresarial del usuario que actualicen a Teams estará disponible próximamente. Puede habilitar esta notificación para el usuario activando la opción Notificar a **los usuarios de Skype** Empresarial.
5. Haga **clic en** Guardar después de realizar los cambios.

### <a name="related-topics"></a>Temas relacionados
[Actualizar de Skype Empresarial a Teams para administradores de TI](upgrade-to-teams-on-prem-overview.md)

[Planear el viaje](upgrade-plan-journey.md)

[Comprender el viaje de coexistencia y actualización de Skype Empresarial y Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md)
