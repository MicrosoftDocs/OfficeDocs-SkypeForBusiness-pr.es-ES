---
title: Administrar aplicaciones de Microsoft Power Platform en el centro de administración de Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 09/27/2022
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre cómo administrar el acceso a aplicaciones personalizadas que se han creado con Microsoft Power Platform en el centro de administración de Teams.
ms.openlocfilehash: c4ac0bd3551bb53da06de3301447c6bf4842540c
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912589"
---
# <a name="manage-microsoft-power-platform-apps-in-the-teams-admin-center"></a>Administrar aplicaciones de Microsoft Power Platform en el centro de administración de Teams

Este artículo le ofrece información general sobre cómo administrar las aplicaciones personalizadas creadas con las aplicaciones [de Microsoft Power Platform](https://powerplatform.microsoft.com/) en el Centro de administración de Microsoft Teams. Las aplicaciones personalizadas las crean desarrolladores de la organización para usuarios internos.

> [!NOTE]
> El artículo no se aplica a la aplicación Power Apps ni a la aplicación Power Virtual Agents que se instalan desde la página Aplicaciones o que están ancladas a Teams a través de una directiva de configuración de aplicaciones. Las aplicaciones de Store se pueden administrar mediante [directivas de permisos de aplicaciones](teams-app-permission-policies.md) y [directivas de configuración de aplicaciones](teams-app-setup-policies.md).

[Power Apps](https://powerapps.microsoft.com) es un entorno de desarrollo de aplicaciones sin código o con poco código que los creadores de aplicaciones de su organización pueden usar para crear aplicaciones personalizadas que se conecten a los datos de empresa. [Power Virtual Agents](/power-virtual-agents/fundamentals-what-is-power-virtual-agents) es un entorno sin código de creación de bots para que los desarrolladores de aplicaciones puedan crear bots eficaces. Con la integración de aplicaciones de Microsoft Power Platform en Teams, las organizaciones pueden simplificar los procesos empresariales, responder a las necesidades empresariales cambiantes más rápidamente para impulsar una mayor colaboración y crear y compartir soluciones personalizadas para ser más productivo.  

Las aplicaciones de Microsoft Power Platform que hayan creado los desarrolladores de su organización se agregan automáticamente a Teams. Los desarrolladores pueden controlar quién puede acceder a su aplicación mediante la [característica de uso compartido en Power Apps](/powerapps/maker/canvas-apps/share-app) y la [característica de uso compartido en Power Virtual Agents](/power-virtual-agents/admin-share-bots).

Cuando se crea o se comparte una aplicación de Microsoft Power Platform, los usuarios pueden verla e instalarla en la página de aplicaciones desde **Creado con Power Platform**. (La aplicación puede tardar unos minutos en aparecer aquí después de que se haya creado o compartido).

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="Capturas de pantalla de la página de aplicaciones, que muestran las aplicaciones de Microsoft Power Platform enumeradas en Creado con Power Platform.":::

Los usuarios finales ven una aplicación en **Creado con Power Platform** si la aplicación cumple una de las siguientes condiciones.

|Power Apps |Power Virtual Agents  |
|---------|---------|
|<ul><li>El usuario creó la aplicación.</li><li>La aplicación se compartió directamente con el usuario.</li><li>El usuario usó recientemente la aplicación. </li></ul>| <ul><li>El usuario creó el bot.</li><li>El bot es propiedad de un equipo del que el usuario es miembro. </li></ul>        |

Los usuarios instalan las aplicaciones de Microsoft Power Platform de la misma manera en que se instala cualquier otra aplicación de Microsoft Teams. Tenga en cuenta que los usuarios solo pueden instalar aplicaciones en el contexto en el que tienen permisos. Por ejemplo, un equipo del que es propietario un usuario, un chat del que forma parte el usuario o su ámbito personal.

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-teams-admin-center"></a>Administrar el acceso a las aplicaciones de Microsoft Power Platform en el centro de administración de Teams

Como administrador, puede controlar si las aplicaciones de Microsoft Power Platform se muestran en **Creado con Power Platform** en la página Aplicaciones de Teams. Puede bloquear o permitir de forma colectiva todas las aplicaciones creadas en Power Apps o todas las aplicaciones creadas en Power Virtual Agents en el nivel de organización en la página [Administrar aplicaciones](manage-apps.md) o para usuarios específicos que usen [directivas de permisos de aplicaciones](teams-app-permission-policies.md).

Las aplicaciones **Power Apps compartidas** y **Power Virtual Agent Apps compartidas** de la tienda de aplicaciones de la organización representan todas las aplicaciones creadas en esa plataforma en particular. Si bloquea una o ambas aplicaciones para toda la organización o para usuarios específicos, los usuarios no podrán instalarlas en Teams. Los usuarios no pueden solicitar la aprobación del administrador para permitir las aplicaciones.

Tenga en cuenta que puede controlar el acceso a todas las aplicaciones creadas en Power Apps y Power Virtual Agents, pero no puede permitir ni bloquear aplicaciones individuales. El creador de la aplicación decide quién puede acceder a las aplicaciones que ha creado a través de la característica de uso compartido desde Power Apps y Power Virtual Agents. Si un creador ha compartido una aplicación que ha creado en Power Virtual Agents con un usuario y usted ha bloqueado **aplicaciones Power Virtual Agents compartidas** para ese usuario, el usuario no podrá ver ni instalar aplicaciones de esa plataforma en Teams.

Si un usuario tiene permiso para acceder a las aplicaciones desde Power Apps o Power Virtual Agents y, luego, usted bloquea el acceso a las aplicaciones desde una o ambas plataformas, el usuario podrá seguir accediendo y usando las aplicaciones de Microsoft Power Platforms que el usuario haya instalado antes de que se haya producido el bloqueo. Sin embargo, el usuario ya no podrá instalar ninguna aplicación desde esas plataformas en **Creado con Power Platform**.

> [!NOTE]
> La opción de configuración **Permitir interacción con aplicaciones personalizadas** de toda la organización en la página [Administrar aplicaciones](manage-apps.md) se aplica a todos los usuarios de la organización y rige si dichos usuarios pueden interactuar con aplicaciones personalizadas. La configuración de aplicaciones para toda la organización rige el comportamiento de todos los usuarios e invalida cualquier otra directiva de permisos de aplicación asignada a los usuarios. Si esta opción está desactivada, los usuarios de su organización no podrán instalar ninguna aplicación personalizada, incluidas las aplicaciones de Microsoft Power Platform. Para obtener más información, consulte [Administrar la configuración de aplicaciones de toda la organización](manage-apps.md#manage-org-wide-app-settings).

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>Permitir o bloquear aplicaciones de Microsoft Power Platform para su organización

De forma predeterminada, se permiten las **aplicaciones de Power Apps compartidas** y las **aplicaciones de Power Virtual Agents compartidas** para todos los usuarios de Teams de la organización. Puede bloquearlas o permitirlas en el nivel de organización desde la página [Administrar aplicaciones](manage-apps.md) del centro de administración de Microsoft Teams.  

1. Inicie sesión en el Centro de administración de Teams y acceda a **las aplicaciones** >  de Teams **[Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps)** Debe ser administrador global o administrador de servicios de Teams para acceder a la página.
1. En la lista de aplicaciones, realice una de las siguientes acciones.

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="Captura de pantalla de la página Administrar aplicaciones, que muestra las aplicaciones compartidas de Microsoft Power Platform.":::

    * Para bloquear las aplicaciones creadas en Power Apps o Power Virtual Agents para todos los usuarios de la organización, busque **aplicaciones de Power Apps compartidas** o **aplicaciones de Power Virtual Agents compartidas**, selecciónelas y, luego, seleccione **Bloquear**.
    * Para permitir aplicaciones creadas en Power Apps o Power Virtual Agents para todos los usuarios de la organización, busque **aplicaciones de Power Apps compartidas** o **aplicaciones de Power Virtual Agents compartidas**, selecciónelas y, luego, seleccione **Permitir**.

### <a name="allow-microsoft-power-platform-apps-for-specific-users"></a>Permitir aplicaciones de Microsoft Power Platform para usuarios específicos

Para permitir o bloquear el acceso de usuarios específicos de la organización a aplicaciones creadas en Power Apps o Power Virtual Agents, cree y asigne una o más [directivas de permisos de aplicación](teams-app-permission-policies.md) personalizadas.

Por ejemplo, para bloquear el acceso de usuarios específicos a las aplicaciones creadas en Power Apps, cree una directiva personalizada para que los permisos de las aplicaciones bloqueen **las Power Apps compartidas** y, a continuación, asigne la directiva a esos usuarios.

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="Captura de pantalla de la directiva personalizada de ejemplo para permisos de aplicaciones con Power Apps compartidas bloqueadas.":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>Usar registros de auditoría para investigar la actividad de instalación de Microsoft Power Platform

Puede usar registros de auditoría para Teams e investigar eventos en los que los usuarios instalaron aplicaciones de Microsoft Power Platform desde la sección **Creado con Power Platform** de la página Aplicaciones en Teams. Para ello, [busque en el registro de auditoría](./audit-log-events.md) el evento de Teams de la **aplicación instalada** (en la operación **AppInstalled**) de un usuario o conjunto de usuarios. Para buscar aplicaciones instaladas desde **Creado con Power Platform**, busque el valor **TemplatedInstance** en la propiedad **AppDistributionMode** en los detalles de un registro determinado.

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="Captura de pantalla del valor TemplatedInstance en la propiedad AppDistributionMode." lightbox="media/manage-power-platform-apps-audit.png":::

> [!NOTE]
> Puede exportar registros de auditoría en formato CSV para facilitar el filtrado.

## <a name="related-articles"></a>Artículos relacionados

* [Compartir una aplicación de lienzo en Power Apps](/powerapps/maker/canvas-apps/share-app)
* [Compartir el bot con otros usuarios](/power-virtual-agents/admin-share-bots)
* [Administrar aplicaciones en el centro de administración de Microsoft Teams](manage-apps.md)
* [Administrar directivas de permisos de aplicación en Teams](teams-app-permission-policies.md)
* [Publicar una aplicación personalizada enviada a través de la API de envío de aplicaciones de Teams](submit-approve-custom-apps.md)
