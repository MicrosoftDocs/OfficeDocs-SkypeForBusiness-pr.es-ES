---
title: Administrar aplicaciones de Microsoft Power Platform en el Centro de administración de Microsoft Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
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
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre cómo administrar el acceso a aplicaciones personalizadas creadas con Microsoft Power Platform en el Centro de administración de Teams.
ms.openlocfilehash: bf75d65f9ebc84ec836dd64839b3e6178d828867
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "66240529"
---
# <a name="manage-microsoft-power-platform-apps-in-the-teams-admin-center"></a>Administrar aplicaciones de Microsoft Power Platform en el Centro de administración de Teams

## <a name="microsoft-power-platform-apps-in-teams"></a>Aplicaciones de Microsoft Power Platform en Teams

En este artículo se ofrece información general sobre cómo administrar las aplicaciones de [Microsoft Power Platform](https://powerplatform.microsoft.com/) en el Centro de administración de Microsoft Teams.

> [!NOTE]
> Este artículo se aplica a las aplicaciones personalizadas creadas por desarrolladores de su organización con Power Apps o Power Virtual Agents. Este artículo no se aplica a la aplicación Power Apps ni a la aplicación Power Virtual Agents que se instalan desde la página Aplicaciones o que están ancladas a Teams a través de una directiva de configuración de aplicaciones. Puedes administrar las aplicaciones de la Store mediante [directivas de permisos de aplicaciones](teams-app-permission-policies.md) y [directivas de configuración de aplicaciones](teams-app-setup-policies.md).

[Power Apps](https://powerapps.microsoft.com) es un entorno de desarrollo de aplicaciones sin código o bajo código que los creadores de aplicaciones de su organización pueden usar para crear aplicaciones personalizadas que se conecten a los datos empresariales. [Power Virtual Agents](/power-virtual-agents/fundamentals-what-is-power-virtual-agents) es un entorno de creación de bots sin código para que los creadores de aplicaciones creen potentes bots. Con la integración de las aplicaciones de Microsoft Power Platform en Teams, las organizaciones pueden simplificar los procesos empresariales, responder a necesidades empresariales cambiantes más rápidamente para impulsar una mayor colaboración y crear y compartir soluciones personalizadas para ser más productivos.  

Las aplicaciones de Microsoft Power Platform creadas por desarrolladores de su organización se agregan automáticamente a Teams. Los desarrolladores pueden controlar quién puede acceder a su aplicación mediante la [característica de uso compartido de Power Apps](/powerapps/maker/canvas-apps/share-app) y la [función de uso compartido en Power Virtual Agents](/power-virtual-agents/admin-share-bots).

Cuando se crea o se comparte una aplicación de Microsoft Power Platform, los usuarios pueden verla e instalarla en la página de aplicaciones, yendo a **Creado con Power Platform**. (La aplicación puede tardar unos minutos en crearse o compartirse para que aparezca aquí).

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="Capturas de pantalla de la página aplicaciones, que muestran las aplicaciones de Microsoft Power Platform enumeradas en Compilación con Power Platform":::

Los usuarios finales ven una aplicación **integrada con Power Platform** si cumplen una de las siguientes condiciones.

|Power Apps |Power Virtual Agents  |
|---------|---------|
|<ul><li>El usuario ha creado la aplicación.</li><li>La aplicación se compartió directamente con el usuario.</li><li>El usuario ha usado recientemente la aplicación. </li></ul>| <ul><li>El usuario ha creado el bot.</li><li>El bot es propiedad de un equipo del que es miembro el usuario. </li></ul>        |

Los usuarios instalan las aplicaciones de Microsoft Power Platform de la misma manera que instalan cualquier otra aplicación de Teams. Tenga en cuenta que los usuarios solo pueden instalar aplicaciones en el contexto en el que tienen permisos. Por ejemplo, un equipo del que es propietario un usuario, un chat del que forma parte el usuario o su ámbito personal.

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-teams-admin-center"></a>Administrar el acceso a las aplicaciones de Microsoft Power Platform en el Centro de administración de Teams

Como administrador, puede controlar si las aplicaciones de Microsoft Power Platform se muestran en **Compilación con Power Platform** en la página Aplicaciones de Teams. Puede bloquear o permitir colectivamente todas las aplicaciones creadas en Power Apps o todas las aplicaciones creadas en Agentes de Power Virtual en el nivel de organización en la página [Administrar aplicaciones](manage-apps.md) o para usuarios específicos que usen [directivas de permisos de aplicaciones](teams-app-permission-policies.md).

Las aplicaciones **Power Apps compartidas** y **Agente virtual compartido de Power Virtual** en la tienda de aplicaciones de su organización representan todas las aplicaciones creadas en esa plataforma en particular. Si bloquea una o ambas aplicaciones para toda la organización o para usuarios específicos, los usuarios pueden ver tales aplicaciones como aplicaciones bloqueadas, pero no pueden instalarlas en Teams. Los usuarios pueden [solicitar la aprobación de administrador para desbloquear aplicaciones](manage-apps.md#manage-user-requests-to-unblock-apps).

Tenga en cuenta que puede controlar el acceso a todas las aplicaciones creadas en Power Apps y Power Virtual Agents, pero no puede permitir ni bloquear aplicaciones individuales. El creador de la aplicación decide quién puede acceder a las aplicaciones que crean a través de la característica de uso compartido desde Power Apps y Power Virtual Agents. Si un creador ha compartido con un usuario una aplicación que han creado en Power Virtual Agents y ha bloqueado **las aplicaciones compartidas de agentes virtuales de Power Virtual** para ese usuario, el usuario no podrá ver ni instalar aplicaciones de esa plataforma en Teams.

Si un usuario tiene permiso para acceder a las aplicaciones desde Power Apps o Power Virtual Agents y, a continuación, le bloquea el acceso a las aplicaciones desde una o ambas plataformas, el usuario puede seguir accediendo y usando las aplicaciones de Microsoft Power Platforms que instaló antes de bloquear la aplicación o las aplicaciones. Sin embargo, el usuario ya no puede instalar ninguna aplicación desde esas plataformas en **Built with Power Platform**.

> [!NOTE]
> La configuración **Permitir interacción con aplicaciones personalizadas** para toda la organización en la página [Administrar aplicaciones](manage-apps.md) se aplica a todos los usuarios de la organización y rige si pueden interactuar con aplicaciones personalizadas. La configuración de aplicaciones para toda la organización rige el comportamiento de todos los usuarios e invalida cualquier otra directiva de permisos de aplicación asignada a los usuarios. Si esta opción está desactivada, los usuarios de su organización no podrán instalar ninguna aplicación personalizada, incluidas las aplicaciones de Microsoft Power Platform. Para obtener más información, consulte [Administrar la configuración de aplicaciones para toda la organización](manage-apps.md#manage-org-wide-app-settings).

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>Permitir o bloquear aplicaciones de Microsoft Power Platform para su organización

De forma predeterminada, se permiten las **aplicaciones de Power Apps compartidas** y las **aplicaciones de agente virtual de Power Virtual compartidas** para todos los usuarios de Teams de su organización. Puede bloquearlas o permitirlas en el nivel de organización en la página [Administrar aplicaciones](manage-apps.md) del Centro de administración de Microsoft Teams.  

1. En el panel izquierdo del Centro de administración de Microsoft Teams, vaya a Aplicaciones  > **de Teams****Administrar aplicaciones**. Debe ser administrador global o administrador de servicios de Teams para poder acceder a la página.
2. En la lista de aplicaciones, realiza una de las siguientes acciones.

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="Captura de pantalla de la página Administrar aplicaciones, que muestra las aplicaciones compartidas de Microsoft Power Platform":::

    - Para bloquear las aplicaciones creadas en Power Apps o Power Virtual Agents para todos los usuarios de la organización, busque **Aplicaciones de energía compartidas** o Aplicaciones compartidas de **Agente de Power Virtual**, selecciónelas y, a continuación, haga clic en **Bloquear**.
    - Para permitir aplicaciones creadas en Power Apps o Power Virtual Agents para todos los usuarios de la organización, busque **Aplicaciones de energía compartidas** o Aplicaciones compartidas de **Power Virtual Agent**, selecciónelas y, a continuación, haga clic en **Permitir**.

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a>Permitir o bloquear aplicaciones de Microsoft Power Platform para usuarios específicos

Para permitir o bloquear el acceso de usuarios específicos de su organización a aplicaciones creadas en Power Apps o agentes de Power Virtual, cree y asigne una o más [directivas de permisos de aplicación](teams-app-permission-policies.md) personalizadas.

Por ejemplo, para bloquear el acceso de usuarios específicos a las aplicaciones creadas en Power Apps, cree una directiva de permisos de aplicación personalizada para bloquear **Power Apps compartidas** y, a continuación, asigne la directiva a esos usuarios.

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="Captura de pantalla de la directiva de permisos de aplicación personalizada de ejemplo con power apps compartidas bloqueadas.":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>Usar registros de auditoría para investigar la actividad de instalación de Microsoft Power Platform

Puede usar registros de auditoría para Teams para investigar eventos en los que los usuarios instalaron aplicaciones de Microsoft Power Platform desde la sección **Compilación con Power Platform** de la página Aplicaciones en Teams. Para ello, [busque en el registro de auditoría](./audit-log-events.md) el evento de Teams de la **aplicación instalada** (en la operación **AppInstalled** ) de un usuario o conjunto de usuarios. Para buscar aplicaciones instaladas desde **la compilación con Power Platform**, busque el valor **TemplatedInstance** en la propiedad **AppDistributionMode** en los detalles de un registro determinado.

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="Captura de pantalla del valor TemplatedInstance en la propiedad AppDistributionMode." lightbox="media/manage-power-platform-apps-audit.png":::

> [!NOTE]
> Puede exportar registros de auditoría en formato CSV para facilitar el filtrado.

## <a name="related-topics"></a>Temas relacionados

- [Compartir una aplicación de lienzo en Power Apps](/powerapps/maker/canvas-apps/share-app)
- [Compartir el bot con otros usuarios](/power-virtual-agents/admin-share-bots)
- [Administrar aplicaciones en el Centro de administración de Microsoft Teams](manage-apps.md)
- [Administrar directivas de permisos de aplicación en Teams](teams-app-permission-policies.md)
- [Publicar una aplicación personalizada enviada a través de la API de envío de aplicaciones de Teams](submit-approve-custom-apps.md)
