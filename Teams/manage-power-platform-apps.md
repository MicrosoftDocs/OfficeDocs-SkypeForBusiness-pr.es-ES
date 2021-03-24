---
title: Administrar aplicaciones de Microsoft Power Platform en el Centro de administración de Microsoft Teams
author: cichur
ms.author: v-cichur
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
description: Obtenga información sobre cómo administrar el acceso a aplicaciones personalizadas integradas en Microsoft Power Platform en el Centro de administración de Microsoft Teams.
ms.openlocfilehash: 03940d402bd2259287e1e69f844e6560424f15e2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096164"
---
# <a name="manage-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Administrar aplicaciones de Microsoft Power Platform en el Centro de administración de Microsoft Teams

## <a name="microsoft-power-platform-apps-in-teams"></a>Aplicaciones de Microsoft Power Platform en Teams

En este artículo se ofrece información general sobre cómo administrar las aplicaciones de [Microsoft Power Platform](https://powerplatform.microsoft.com/) en el Centro de administración de Microsoft Teams.

> [!NOTE]
> Este artículo se aplica a las aplicaciones personalizadas creadas por creadores de su organización con Power Apps o Power Virtual Agents. Estas aplicaciones personalizadas se agregan automáticamente a Teams. Este artículo no se aplica a la aplicación Power Apps o a la aplicación Power Virtual Agents que están instaladas desde la página Aplicaciones o ancladas a Teams a través de una directiva de configuración de aplicaciones. Administra esas aplicaciones como lo haría con [](manage-apps.md) cualquier otra [](teams-app-permission-policies.md)aplicación en la página Administrar aplicaciones, con directivas de permisos de aplicación y directivas [de configuración de aplicaciones.](teams-app-setup-policies.md)

[Power Apps](https://powerapps.microsoft.com) es un entorno de desarrollo de aplicaciones sin código que los creadores de su organización pueden usar para crear aplicaciones personalizadas que se conecten a los datos empresariales. [Power Virtual Agents es](/power-virtual-agents/fundamentals-what-is-power-virtual-agents) un entorno de creación de bots sin código para que los creadores creen bots eficaces. Con la integración de las aplicaciones de Microsoft Power Platform en Teams, las organizaciones pueden simplificar los procesos empresariales, responder a las necesidades empresariales cambiantes más rápidamente para impulsar una mayor colaboración y crear y compartir soluciones personalizadas para ser más productivos.  

Las aplicaciones de Microsoft Power Platform creadas por creadores de su organización se agregan automáticamente a Teams. Los creadores pueden controlar quién puede acceder a su aplicación mediante la característica de uso compartido en [Power Apps](/powerapps/maker/canvas-apps/share-app) y la característica de uso compartido en Power [Virtual Agents.](/power-virtual-agents/admin-share-bots)

Cuando se crea o comparte una aplicación de Microsoft Power Platform, los usuarios pueden verlo e instalarlo en la página Aplicaciones yendo a Creado para su ***nombre*** de organización creado por  >  **sus compañeros.** (Puede tardar unos minutos después de crear o compartir una aplicación para que la aplicación aparezca aquí).

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="Capturas de pantalla de la página Aplicaciones, que muestra las aplicaciones de Microsoft Power Platform enumeradas en Integrado por sus compañeros":::

Un usuario verá una aplicación integrada por sus compañeros **si** la aplicación cumple una de las siguientes condiciones.

|Power Apps |Power Virtual Agents  |
|---------|---------|
|<ul><li>El usuario creó la aplicación.</li><li>La aplicación se compartió directamente con el usuario.</li><li>El usuario ha usado recientemente la aplicación. </li></ul>| <ul><li>El usuario creó el bot.</li><li>El bot es propiedad de un equipo del que es miembro el usuario. </li></ul>        |

Los usuarios instalan las aplicaciones de Microsoft Power Platform de la misma manera que instalan cualquier otra aplicación de Teams. Tenga en cuenta que los usuarios solo pueden instalar aplicaciones en el contexto en el que tienen permisos, por ejemplo, un equipo de su propiedad, un chat del que forman parte o su ámbito personal.

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Administrar el acceso a las aplicaciones de Microsoft Power Platform en el Centro de administración de Microsoft Teams

Como administrador, puede controlar si las aplicaciones de Microsoft Power Platform se muestran en **Integrado por** sus compañeros en la página Aplicaciones de Teams. Puede bloquear o permitir colectivamente todas las aplicaciones creadas en Power Apps o [](manage-apps.md) todas las aplicaciones creadas en Power Virtual Agents en el nivel de la organización en la página Administrar aplicaciones o para usuarios específicos que usan directivas de permisos de [aplicación.](teams-app-permission-policies.md)

Las **aplicaciones Compartidas de Power Apps** y Shared Power Virtual Agent **en** la tienda de aplicaciones de su organización representan todas las aplicaciones creadas en esa plataforma en particular. Si bloquea una o ambas aplicaciones en el nivel de la organización o para usuarios específicos, esos usuarios no podrán ver ninguna aplicación de esas **plataformas** en Integrado por sus compañeros y no podrán instalarlas en Teams.  

Tenga en cuenta que puede controlar el acceso a todas las aplicaciones creadas en Power Apps y Power Virtual Agents, pero no puede permitir ni bloquear aplicaciones individuales. Los creadores deciden quién puede acceder a las aplicaciones que crean a través de la característica de uso compartido desde Power Apps y Power Virtual Agents. Si un creador compartió una aplicación que creó en Power Virtual Agents con un usuario y bloqueó aplicaciones de agentes virtuales de **Power Compartido** para ese usuario, el usuario no podrá ver ni instalar ninguna aplicación de esa plataforma en Teams.

Si un usuario tiene permiso para acceder a aplicaciones de Power Apps o Power Virtual Agents y, a continuación, bloquea el acceso a las aplicaciones desde una o ambas plataformas, el usuario podrá seguir accediendo y usar las aplicaciones de Microsoft Power Platforms que instalaron antes de bloquear la aplicación o las aplicaciones. Sin embargo, el usuario ya no puede ver ni instalar ninguna aplicación de esas plataformas en **Integrado por sus compañeros.**

> [!NOTE]
> La **configuración Permitir interacción con** aplicaciones personalizadas para toda la organización en la página Administrar aplicaciones se aplica a todos los usuarios de su organización y rige si pueden interactuar con aplicaciones personalizadas. [](manage-apps.md) La configuración de aplicaciones para toda la organización rige el comportamiento de todos los usuarios e invalida cualquier otra directiva de permisos de aplicación asignada a los usuarios. Esta configuración está activada de forma predeterminada. Si esta configuración está desactivada, los usuarios de su organización no pueden ver ni instalar ninguna aplicación personalizada, incluidas las aplicaciones de Microsoft Power Platform. Para obtener más información, vea [Administrar la configuración de aplicaciones para toda la organización.](manage-apps.md#manage-org-wide-app-settings)

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>Permitir o bloquear aplicaciones de Microsoft Power Platform para su organización

De forma predeterminada, **las aplicaciones power apps compartidas** y las aplicaciones de agente virtual de Power **Virtual** compartidas están permitidas para todos los usuarios de Teams de su organización. Puede bloquearlas o permitirlas en el nivel de la organización en la página Administrar [aplicaciones](manage-apps.md) del Centro de administración de Microsoft Teams.  

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Aplicaciones de Teams** > **Administrar aplicaciones**. Debe ser administrador global o administrador del servicio de Teams para obtener acceso a la página.
2. En la lista de aplicaciones, realice una de las siguientes acciones.

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="Captura de pantalla de la página Administrar aplicaciones, que muestra las aplicaciones compartidas de Microsoft Power Platform":::

    - Para bloquear las aplicaciones creadas en Power Apps o Power Virtual Agents para todos los usuarios de su organización, busque Aplicaciones de **Power Apps** compartidas o Aplicaciones compartidas de Power **Virtual Agent,** selecciónelo y, a continuación, haga clic en **Bloquear.**
    - Para permitir aplicaciones creadas en Power Apps o Power Virtual Agents para todos los usuarios de su organización, busque Aplicaciones **de Power Apps** compartidas o Aplicaciones compartidas de Power Virtual **Agent,** selecciónelo y, a continuación, haga clic en **Permitir.**

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a>Permitir o bloquear aplicaciones de Microsoft Power Platform para usuarios específicos

Para permitir o bloquear el acceso de usuarios específicos de su organización a aplicaciones creadas en Power Apps o Power Virtual Agents, cree y asigne una o más directivas de permisos de aplicaciones [personalizadas.](teams-app-permission-policies.md) 

Por ejemplo, para impedir que usuarios específicos accedan a aplicaciones creadas en Power Apps, cree una directiva de permisos de aplicación personalizada para bloquear **Aplicaciones compartidas de Power Apps** y, después, asigne la directiva a esos usuarios.

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="Captura de pantalla de una directiva de permisos de aplicación personalizada de ejemplo con Power Apps compartido bloqueado":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>Usar registros de auditoría para investigar la actividad de instalación de Microsoft Power Platform

Puede usar registros de auditoría para Teams para investigar eventos en los que los usuarios instalaron aplicaciones de Microsoft Power Platform desde la sección Integrado **por** sus compañeros de la página Aplicaciones de Teams. Para ello, busque en el  registro de [auditoría](./audit-log-events.md) el evento Teams de la aplicación instalada (en la operación **AppInstalled)** para un usuario o conjunto de usuarios. Para buscar aplicaciones instaladas desde **Integrado por** sus compañeros, busque el valor **TemplatedInstance** en la **propiedad AppDistributionMode** en los detalles de un registro determinado. 

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="Captura de pantalla del valor TemplatedInstance en la propiedad AppDistributionMode":::

> [!NOTE]
> Puede exportar registros de auditoría en formato CSV para facilitar el filtrado.

## <a name="related-topics"></a>Temas relacionados

- [Compartir una aplicación de lienzo en Power Apps](/powerapps/maker/canvas-apps/share-app)
- [Compartir el bot con otros usuarios](/power-virtual-agents/admin-share-bots)
- [Administrar aplicaciones en el Centro de administración de Microsoft Teams](manage-apps.md)
- [Administrar directivas de permisos de aplicación en Teams](teams-app-permission-policies.md)
- [Publicar una aplicación personalizada enviada a través de la API de envío de aplicaciones de Teams](submit-approve-custom-apps.md)