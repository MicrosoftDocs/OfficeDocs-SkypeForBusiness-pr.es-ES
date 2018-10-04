---
title: Establecer las opciones de actualización y coexistencia
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: bjwhalen
search.appverid: MET150
description: En este artículo le ayudará a elegir el modo de coexistencia y establecer otras opciones de configuración de coexistencia.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b89d75f07ecfac6e37f33c27a9272187b0794a6
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371509"
---
# <a name="setting-your-coexistence-and-upgrade-settings"></a>Establecer las opciones de actualización y coexistencia

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Al actualizar su Skype para usar los equipos de los usuarios de negocios, dispone de varias opciones que le ayudarán a realizar un proceso transparente para los usuarios. Tiene la opción para realizar la coexistencia y actualizar la configuración para todos los usuarios de la organización a la vez, o puede realizar cambios en la configuración de un único o un conjunto de usuarios de su organización. Tenga en cuenta que las versiones anteriores de Skype para los clientes empresariales pueden no respetan estas opciones de configuración.

Asignada un nivel de usuario de configuración tiene prioridad sobre la configuración aplicada en el nivel de toda la organización. Puede obtener una mejor comprensión de los tipos de modos que están disponibles para usted, lea [comprender la coexistencia y actualización de viaje para Skype para profesionales y los equipos](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="setting-upgrade-options-for-all-users-in-your-organization"></a>Configurar las opciones de actualización para todos los usuarios de la organización

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**

1. En el panel de navegación izquierdo, vaya a **configuración de toda la organización** > **actualización de los equipos**. 

2. En la parte superior de la página de la **página de actualización de los equipos** , realice los siguientes cambios si trabajan para usted.
    - Establezca el modo de **coexistencia** .
        - **Islas** : Utilice esta opción si desea que los usuarios puedan utilizar ambos Skype para profesionales y los equipos de forma simultánea.
        - **Skype para la empresa sólo** - Utilice esta opción si desea que los usuarios sólo para usar Skype para la empresa.
        - Sólo los equipos de **los equipos sólo** - Utilice esta opción si desea que los usuarios usen. Tenga en cuenta que incluso con esta opción, los usuarios todavía pueden unirse a reuniones hospedadas en Skype para la empresa.
    - Establecer **Notificar a Skype para los usuarios empresariales que los equipos está disponible para la actualización**. Si desactiva esta, le indicará el Skype para usuarios profesionales que se va a ser actualizado pronto a la aplicación de los equipos.
    - Establecer la **aplicación preferida para los usuarios participar en Skype para reuniones de negocios**. Esta configuración determina qué aplicación se utiliza para unirse a Skype para reuniones de negocios y se cumplirá independientemente del valor del modo de coexistencia.
      - **Aplicación de las reuniones de Skype**
      - **Skype para la empresa con características limitadas**
    - Establece si se van a **Descargar la aplicación de los equipos en el fondo de Skype para los usuarios empresariales**.  Esta opción de configuración en modo silencioso descarga la aplicación de los equipos de los usuarios que ejecutan Skype para la empresa en Windows. Se tiene en cuenta sólo si el modo de coexistencia para el usuario es sólo de los equipos o si se habilitan las notificaciones de actualización pendientes en Skype para la empresa.
3. Después de realizar los cambios, haga clic en **Guardar** .

## <a name="setting-upgrade-options-for-a-single-user-in-your-organization"></a>Configurar las opciones de actualización para un único usuario de la organización

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**

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

[Guía de interoperabilidad y migración para las organizaciones que utilizan los equipos junto con Skype para la empresa](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)
