---
title: Administrar aplicaciones de plataforma de energía en el centro de administración de Microsoft Teams
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
description: Obtenga información sobre cómo administrar el acceso a las aplicaciones de Power Platform en el centro de administración de Microsoft Teams.
ms.openlocfilehash: 74bfabaff0ec7ed5f27c08ac86b325164d9dad10
ms.sourcegitcommit: af9f96010460f9323db84912fe143aa0750ac798
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171464"
---
# <a name="manage-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Administrar aplicaciones de plataforma de energía en el centro de administración de Microsoft Teams

## <a name="power-platform-apps-in-teams"></a>Aplicaciones de plataforma de energía en Teams

Este artículo le ofrece información general sobre cómo administrar las aplicaciones de [Power Platform](https://powerplatform.microsoft.com/) agregadas a teams en el centro de administración de Microsoft Teams.

[Power apps](https://powerapps.microsoft.com) es un entorno de desarrollo de aplicaciones de bajo código y sin código que los creadores de su organización pueden usar para crear aplicaciones personalizadas que se conecten a los datos empresariales. Los [agentes de Power virtual](https://docs.microsoft.com/power-virtual-agents/fundamentals-what-is-power-virtual-agents) son un bot? de creación de un bot? Con la integración de las aplicaciones de Power Platform en Teams, las organizaciones pueden simplificar los procesos empresariales, responder a las necesidades empresariales cambiantes más rápidamente para impulsar una mayor colaboración, y crear y compartir soluciones personalizadas para ser más productivas.  

Las aplicaciones de plataforma de energía creadas por los responsables de la organización se agregan automáticamente a teams. Los responsables de los encargados pueden controlar quién puede acceder a su aplicación mediante la [característica de uso compartido en Power apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app) y la [característica de uso compartido en Power virtual Agents](https://docs.microsoft.com/power-virtual-agents/admin-share-bots). 

Cuando se crea o se comparte una aplicación de Power Platform, los usuarios pueden verla e instalarla en la página aplicaciones yendo a **creado para *el nombre*de la organización**  >  **creado por sus colegas**. (Puede demorar unos minutos después de crear o compartir una aplicación para que la aplicación aparezca aquí).

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="Capturas de pantalla de la página de aplicaciones, que muestra las aplicaciones de Power Platform mencionadas en sus colegas":::

Un usuario verá una aplicación de Power Platform en la **compilación de sus compañeros** si la aplicación cumple una de las siguientes condiciones.

|Power apps |Agentes de Power virtual  |
|---------|---------|
|<ul><li>El usuario creó la aplicación.</li><li>La aplicación se compartió directamente con el usuario.</li><li>El usuario ha usado recientemente la aplicación. </li></ul>| <ul><li>El usuario creó el bot.</li><li>El bot es propiedad de un equipo del que el usuario es miembro. </li></ul>        |

Los usuarios instalan las aplicaciones de Power Platform de la misma forma en que instalan cualquier otra aplicación de Teams. Tenga en cuenta que los usuarios solo pueden instalar aplicaciones en el contexto para el que tienen permisos, por ejemplo, un equipo de su propiedad, un chat del que forma parte o su ámbito personal.

## <a name="manage-access-to-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Administrar el acceso a las aplicaciones de Power Platform en el centro de administración de Microsoft Teams

Como administrador, puede controlar si las aplicaciones de plataforma de energía aparecen en la lista de **sus compañeros** en la página aplicaciones de Teams. Puede bloquear o permitir colectivamente todas las aplicaciones creadas en Power Apps o todas las aplicaciones creadas en agentes de Power virtual en el nivel de la organización en la página [Administrar aplicaciones](manage-apps.md) o para usuarios específicos que usen [directivas de permisos](teams-app-permission-policies.md)de la aplicación.

Las aplicaciones **compartidas de Power apps** y las aplicaciones de **agente virtual de Power virtual** de la organización en la tienda de aplicaciones representan todas las aplicaciones creadas en esa plataforma en particular. Si bloquea una o ambas aplicaciones en el nivel de la organización o para usuarios específicos, esos usuarios no podrán ver ninguna aplicación de esas plataformas en la **creación de sus colegas** y no podrán instalarlas en Teams.  

Tenga en cuenta que puede controlar el acceso a todas las aplicaciones creadas en Power apps y los agentes virtuales de Power, pero no puede permitir o bloquear aplicaciones individuales. Los responsables deciden quién puede acceder a las aplicaciones que crean a través de la característica de uso compartido de Power apps y los agentes virtuales de Power. Si un creador ha compartido una aplicación que ha creado en agentes de Power virtual con un usuario y ha bloqueado **Aplicaciones compartidas de agentes virtuales de potencia** para ese usuario, el usuario no podrá ver ni instalar ninguna aplicación de esa plataforma en Teams.

Si un usuario tiene permiso para acceder a aplicaciones de Power Apps o de agentes virtuales de Power, y después impide que el usuario tenga acceso a las aplicaciones de una o ambas plataformas, el usuario podrá acceder y usar las aplicaciones de plataformas de Power que haya instalado antes de bloquear la aplicación o las aplicaciones. Sin embargo, el usuario ya no podrá ver ni instalar ninguna aplicación de esas plataformas en **la creación de sus colegas**.

> [!NOTE]
> La configuración **permitir la interacción con aplicaciones personalizadas** de la organización de la organización en la página [Administrar aplicaciones](manage-apps.md) se aplica a todos los usuarios de la organización y rige si pueden interactuar con aplicaciones personalizadas. La configuración de la aplicación en toda la organización rige el comportamiento de todos los usuarios y anula cualquier otra directiva de permisos de aplicación asignada a los usuarios. Esta opción está activada de forma predeterminada. Si esta opción está desactivada, los usuarios de la organización no pueden ver ni instalar aplicaciones personalizadas, incluidas las aplicaciones de Power Platform. Para obtener más información, vea [administrar la configuración de aplicaciones de toda la organización](manage-apps.md#manage-org-wide-app-settings).

### <a name="allow-or-block-power-platform-apps-for-your-organization"></a>Permitir o bloquear las aplicaciones de la plataforma de energía para su organización

De forma predeterminada, las aplicaciones de **energía compartida** y las **aplicaciones del agente virtual de energía compartida** están permitidas para todos los usuarios de su organización. Puede bloquearlos o permitirlos en el nivel de organización en la página [Administrar aplicaciones](manage-apps.md) del centro de administración de Microsoft Teams.  

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **aplicaciones de Teams**  >  **Manage apps**. Debe ser administrador global o administrador de servicios de equipo para poder acceder a la página.
2. En la lista de aplicaciones, realice una de las siguientes acciones:

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="Captura de pantalla de la página Administrar aplicaciones, que muestra las aplicaciones de plataforma compartida de Power":::

    - Para bloquear las aplicaciones creadas en Power Apps o agentes virtuales de Power para todos los usuarios de su organización, busque **aplicaciones de energía compartidas** o **aplicaciones de agente virtual de energía compartido**, selecciónelas y, a continuación, haga clic en **bloquear**.
    - Para permitir que las aplicaciones creadas en Power Apps o agentes virtuales de Power para todos los usuarios de su organización, busque **aplicaciones de energía compartidas** o **aplicaciones de agente virtual de energía compartido**, selecciónelas y, a continuación, haga clic en **permitir**.

### <a name="allow-or-block-power-platform-apps-for-specific-users"></a>Permitir o bloquear aplicaciones de plataforma de energía para usuarios específicos

Para permitir o bloquear a determinados usuarios de su organización el acceso a aplicaciones creadas en Power Apps o agentes virtuales de Power, cree y asigne una o varias [directivas de permisos de aplicaciones](teams-app-permission-policies.md)personalizadas. 

Por ejemplo, para bloquear el acceso de usuarios específicos a aplicaciones creadas en Power Apps, cree una directiva de permisos de aplicaciones personalizada para bloquear las **aplicaciones de energía compartidas**y, a continuación, asigne la Directiva a esos usuarios.

:::image type="content" source="media/manage-power-platform-apps-app-permissions-policy.png" alt-text="Captura de pantalla de la Directiva de permisos de aplicaciones personalizada de ejemplo con Power apps compartida bloqueada":::

## <a name="related-topics"></a>Temas relacionados

- [Compartir una aplicación de lienzo en Power apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app)
- [Compartir el bot con otros usuarios](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)
- [Administrar aplicaciones en el centro de administración de Microsoft Teams](manage-apps.md)
- [Administrar directivas de permisos de aplicación en Teams](teams-app-permission-policies.md)
- [Publicar una aplicación personalizada enviada a través de la API de envío de la aplicación de Teams](submit-approve-custom-apps.md)
