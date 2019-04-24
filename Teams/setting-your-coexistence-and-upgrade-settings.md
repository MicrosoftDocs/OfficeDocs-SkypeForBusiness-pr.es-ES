---
title: Configurar su coexistencia y la configuración de actualización
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: En este artículo le ayudará a elegir el modo de coexistencia y establecer otras opciones de configuración de coexistencia.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 55ed1396cd9c16b96e7d230429ccf25c1802473e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32204639"
---
# <a name="setting-your-coexistence-and-upgrade-settings"></a>Configurar su coexistencia y la configuración de actualización

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Cuando se actualiza su Skype para usar los equipos de los usuarios de negocios, dispone de varias opciones que le ayudarán a realizar un proceso transparente para los usuarios. Tiene la opción para realizar la coexistencia y actualizar la configuración para todos los usuarios de la organización a la vez, o puede realizar cambios en la configuración de un único o un conjunto de usuarios de su organización. Tenga en cuenta que las versiones anteriores de Skype para los clientes empresariales pueden no respetan estas opciones de configuración. Para obtener más información acerca de Skype para versiones de cliente de negocio, vaya a [descargas de Skype para la empresa y actualiza la página](https://docs.microsoft.com/en-us/skypeforbusiness/software-updates). 

Puede obtener una mejor comprensión de los tipos de modos que están disponibles para usted, lea la [Descripción de los equipos de Microsoft y Skype para la interoperabilidad y coexistencia de negocio](teams-and-skypeforbusiness-coexistence-and-interoperability.md) o [coexistencia con Skype para la empresa](coexistence-chat-calls-presence.md).  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>Establecer las opciones de actualización para todos los usuarios de la organización

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **desde el centro de administración de equipos de Microsoft**

1. En el panel de navegación izquierdo, vaya a **configuración de toda la organización** > **actualización de los equipos**. 

2. En la parte superior de la página **actualización de los equipos** , realice los siguientes cambios si trabajan para usted.
    - Establezca el modo de **coexistencia** .
        - **Islas** : Utilice esta opción si desea que los usuarios puedan utilizar ambos Skype para profesionales y los equipos de forma simultánea.
        - **Skype para la empresa sólo** - Utilice esta opción si desea que los usuarios sólo para usar Skype para la empresa.
        - **Sólo los equipos** (en la vista previa para algunas organizaciones) - Use esta opción si desea que los usuarios usen únicamente los equipos. Tenga en cuenta que incluso con esta opción, los usuarios todavía pueden unirse a reuniones hospedadas en Skype para la empresa.
    - Establecer **Notificar a Skype para los usuarios empresariales que los equipos está disponible para la actualización**. Si desactiva esta, le indicará el Skype para usuarios profesionales que se va a ser actualizado pronto a la aplicación de los equipos.
    - Establecer la **aplicación preferida para los usuarios participar en Skype para reuniones de negocios**. Esta configuración determina qué aplicación se utiliza para unirse a Skype para reuniones de negocios y se cumplirá independientemente del valor del modo de coexistencia.
      - **Aplicación de las reuniones de Skype**
      - **Skype para la empresa con características limitadas**
    - Establece si se van a **Descargar la aplicación de los equipos en el fondo de Skype para los usuarios empresariales**.  Esta opción de configuración en modo silencioso descarga la aplicación de los equipos de los usuarios que ejecutan Skype para la empresa en Windows. Se tiene en cuenta sólo si modo de coexistencia para el usuario sólo está equipos o si se habilitan las notificaciones de actualización pendientes en Skype para la empresa.
3. Después de realizar los cambios, haga clic en **Guardar** .

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>Establecer las opciones de actualización para un único usuario de la organización

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **desde el centro de administración de equipos de Microsoft**

1. En el panel de navegación izquierdo, vaya a **los usuarios**y, a continuación, seleccione el usuario en la lista. 
2. En la ficha de **cuenta** para el usuario, en **los equipos de actualización**, haga clic en **Editar**.
3. Puede establecer el **modo de coexistencia**. Elegir entre las siguientes opciones:
     - **Configuración de toda la organización uso** - Utilice esta opción si desea que el usuario para utilizar la configuración de la configuración de **toda la organización** . 
     - **Islas** : Utilice esta opción si desea que el usuario para poder utilizar ambos Skype para profesionales y los equipos. 
     - **Skype para la empresa sólo** - Utilice esta opción si desea que el usuario pueda utilizar Skype para la empresa. 
     - Sólo los equipos de **los equipos sólo** - Utilice esta opción si desea que el usuario pueda utilizar. El usuario aún podrá unirse a Skype para reuniones de negocios.
4. Si selecciona un **modo de coexistencia** distinto al **uso Org toda la configuración**, tiene la opción de habilitar las notificaciones en Skype del usuario para la aplicación empresarial de actualización a los equipos próximamente. Puede habilitar esta notificación para el usuario al activar la opción **Notificar la Skype para usuarios de empresa** .
5. Después de realizar los cambios, haga clic en **Guardar** .

### <a name="related-topics"></a>Temas relacionados
[Planear el viaje](upgrade-plan-journey.md)

[Comprender la coexistencia y actualizar viaje para Skype para profesionales y los equipos](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md)
