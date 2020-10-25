---
title: Administrar las aplicaciones de Microsoft Power Platform en el centro de administración de Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: joglocke
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo administrar el acceso a aplicaciones personalizadas integradas en Microsoft Power Platform en el centro de administración de Microsoft Teams.
ms.openlocfilehash: 5675083c3a7b0aaea2fb053609cbf7da800dbe42
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753575"
---
# <a name="manage-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Administrar las aplicaciones de Microsoft Power Platform en el centro de administración de Microsoft Teams

## <a name="microsoft-power-platform-apps-in-teams"></a>Aplicaciones de Microsoft Power Platform en Teams

Este artículo le ofrece información general sobre cómo administrar las aplicaciones de [Microsoft Power Platform](https://powerplatform.microsoft.com/) en el centro de administración de Microsoft Teams.

> [!NOTE]
> Este artículo se aplica a las aplicaciones personalizadas creadas por los responsables de la organización mediante Power Apps o Power virtual Agents. Estas aplicaciones personalizadas se agregan automáticamente a teams. Este artículo no se aplica a la aplicación Power Apps o a la aplicación Power virtual Agents que se instalan desde la página aplicaciones o se anclan a teams mediante una directiva de configuración de aplicación. Estas aplicaciones se administran del mismo modo que lo haría cualquier otra aplicación en la página [Administrar aplicaciones](manage-apps.md) , mediante [directivas de permisos](teams-app-permission-policies.md)de la aplicación y [directivas de configuración](teams-app-setup-policies.md)de la aplicación.

[Power apps](https://powerapps.microsoft.com) es un entorno de desarrollo de aplicaciones de bajo código y sin código que los creadores de su organización pueden usar para crear aplicaciones personalizadas que se conecten a los datos empresariales. Los [agentes de Power virtual](https://docs.microsoft.com/power-virtual-agents/fundamentals-what-is-power-virtual-agents) son un bot? de creación de un bot? Gracias a la integración de las aplicaciones de Microsoft Power Platform en Teams, las organizaciones pueden simplificar los procesos empresariales, responder a las cambiantes necesidades empresariales más rápidamente para impulsar una mayor colaboración, y crear y compartir soluciones personalizadas para ser más productivas.  

Las aplicaciones de Microsoft Power Platform creadas por los responsables de la organización se agregan automáticamente a teams. Los responsables de los encargados pueden controlar quién puede acceder a su aplicación mediante la [característica de uso compartido en Power apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app) y la [característica de uso compartido en Power virtual Agents](https://docs.microsoft.com/power-virtual-agents/admin-share-bots).

Cuando se crea o se comparte una aplicación de Microsoft Power Platform, los usuarios pueden verla e instalarla en la página aplicaciones yendo a **creado para *el nombre*de la organización**  >  **creado por sus colegas**. (Puede demorar unos minutos después de crear o compartir una aplicación para que la aplicación aparezca aquí).

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="Capturas de pantalla de la página de aplicaciones, que muestra las aplicaciones de Microsoft Power Platform enumeradas en las creadas por sus colegas":::

Un usuario verá una aplicación en la **creación de tus colegas** si la aplicación cumple una de las siguientes condiciones.

|Power apps |Agentes de Power virtual  |
|---------|---------|
|<ul><li>El usuario creó la aplicación.</li><li>La aplicación se compartió directamente con el usuario.</li><li>El usuario ha usado recientemente la aplicación. </li></ul>| <ul><li>El usuario creó el bot.</li><li>El bot es propiedad de un equipo del que el usuario es miembro. </li></ul>        |

Los usuarios instalan las aplicaciones de Microsoft Power Platform de la misma forma en que instalan cualquier otra aplicación de Teams. Tenga en cuenta que los usuarios solo pueden instalar aplicaciones en el contexto para el que tienen permisos, por ejemplo, un equipo de su propiedad, un chat del que forma parte o su ámbito personal.

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Administrar el acceso a las aplicaciones de Microsoft Power Platform en el centro de administración de Microsoft Teams

Como administrador, puede controlar si las aplicaciones de Microsoft Power Platform se enumeran en la **creación de sus compañeros** en la página aplicaciones de Teams. Puede bloquear o permitir colectivamente todas las aplicaciones creadas en Power Apps o todas las aplicaciones creadas en agentes de Power virtual en el nivel de la organización en la página [Administrar aplicaciones](manage-apps.md) o para usuarios específicos que usen [directivas de permisos](teams-app-permission-policies.md)de la aplicación.

Las aplicaciones **compartidas de Power apps** y las aplicaciones de **agente virtual de Power virtual** de la organización en la tienda de aplicaciones representan todas las aplicaciones creadas en esa plataforma en particular. Si bloquea una o ambas aplicaciones en el nivel de la organización o para usuarios específicos, esos usuarios no podrán ver ninguna aplicación de esas plataformas en la **creación de sus colegas** y no podrán instalarlas en Teams.  

Tenga en cuenta que puede controlar el acceso a todas las aplicaciones creadas en Power apps y los agentes virtuales de Power, pero no puede permitir o bloquear aplicaciones individuales. Los responsables deciden quién puede acceder a las aplicaciones que crean a través de la característica de uso compartido de Power apps y los agentes virtuales de Power. Si un creador ha compartido una aplicación que ha creado en agentes de Power virtual con un usuario y ha bloqueado **Aplicaciones compartidas de agentes virtuales de potencia** para ese usuario, el usuario no podrá ver ni instalar ninguna aplicación de esa plataforma en Teams.

Si un usuario tiene permiso para acceder a aplicaciones de Power Apps o de agentes virtuales de Power, y después impide que el usuario tenga acceso a las aplicaciones de una o ambas plataformas, el usuario podrá acceder y usar las aplicaciones de Microsoft Power Platforms instaladas antes de bloquear la aplicación o las aplicaciones. Sin embargo, el usuario ya no podrá ver ni instalar ninguna aplicación de esas plataformas en **la creación de sus colegas**.

> [!NOTE]
> La configuración **permitir la interacción con aplicaciones personalizadas** de la organización de la organización en la página [Administrar aplicaciones](manage-apps.md) se aplica a todos los usuarios de la organización y rige si pueden interactuar con aplicaciones personalizadas. La configuración de la aplicación en toda la organización rige el comportamiento de todos los usuarios y anula cualquier otra directiva de permisos de aplicación asignada a los usuarios. Esta opción está activada de forma predeterminada. Si esta opción está desactivada, los usuarios de la organización no pueden ver ni instalar aplicaciones personalizadas, incluidas las aplicaciones de Microsoft Power Platform. Para obtener más información, vea [administrar la configuración de aplicaciones de toda la organización](manage-apps.md#manage-org-wide-app-settings).

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>Permitir o bloquear las aplicaciones de Microsoft Power Platform para su organización

De forma predeterminada, las aplicaciones de **energía compartida** y las **aplicaciones del agente virtual de energía compartida** están permitidas para todos los usuarios de su organización. Puede bloquearlos o permitirlos en el nivel de organización en la página [Administrar aplicaciones](manage-apps.md) del centro de administración de Microsoft Teams.  

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **aplicaciones de Teams**  >  **Manage apps**. Debe ser administrador global o administrador de servicios de equipo para poder acceder a la página.
2. En la lista de aplicaciones, realice una de las siguientes acciones:

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="Captura de pantalla de la página Administrar aplicaciones, que muestra las aplicaciones compartidas de Power Platform de Microsoft":::

    - Para bloquear las aplicaciones creadas en Power Apps o agentes virtuales de Power para todos los usuarios de su organización, busque **aplicaciones de energía compartidas** o **aplicaciones de agente virtual de energía compartido**, selecciónelas y, a continuación, haga clic en **bloquear**.
    - Para permitir que las aplicaciones creadas en Power Apps o agentes virtuales de Power para todos los usuarios de su organización, busque **aplicaciones de energía compartidas** o **aplicaciones de agente virtual de energía compartido**, selecciónelas y, a continuación, haga clic en **permitir**.

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a>Permitir o bloquear las aplicaciones de Microsoft Power Platform para usuarios específicos

Para permitir o bloquear a determinados usuarios de su organización el acceso a aplicaciones creadas en Power Apps o agentes virtuales de Power, cree y asigne una o varias [directivas de permisos de aplicaciones](teams-app-permission-policies.md)personalizadas. 

Por ejemplo, para bloquear el acceso de usuarios específicos a aplicaciones creadas en Power Apps, cree una directiva de permisos de aplicaciones personalizada para bloquear las **aplicaciones de energía compartidas**y, a continuación, asigne la Directiva a esos usuarios.

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="Captura de pantalla de la Directiva de permisos de aplicaciones personalizada de ejemplo con Power apps compartida bloqueada":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>Usar registros de auditoría para investigar la actividad de instalación de Microsoft Power Platform

Puede usar registros de auditoría para los equipos para investigar eventos en los que los usuarios instalaron aplicaciones de Microsoft Power Platform desde la sección **creado por su compañeros** de la página aplicaciones de Teams. Para ello, [Busque en el registro de auditoría](https://docs.microsoft.com/microsoftteams/audit-log-events) el evento de Teams de la **aplicación instalado** (bajo la operación de **AppInstalled** ) de un usuario o un conjunto de usuarios. Para buscar aplicaciones instaladas desde **una compilación de sus compañeros**, busque el valor **TemplatedInstance** en la propiedad **AppDistributionMode** en los detalles de un registro determinado. 

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="Captura de pantalla del valor TemplatedInstance de la propiedad AppDistributionMode":::

> [!NOTE]
> Puede exportar registros de auditoría en formato CSV para facilitar el filtrado.

## <a name="related-topics"></a>Temas relacionados

- [Compartir una aplicación de lienzo en Power apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app)
- [Compartir el bot con otros usuarios](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)
- [Administrar aplicaciones en el centro de administración de Microsoft Teams](manage-apps.md)
- [Administrar directivas de permisos de aplicación en Teams](teams-app-permission-policies.md)
- [Publicar una aplicación personalizada enviada a través de la API de envío de la aplicación de Teams](submit-approve-custom-apps.md)
