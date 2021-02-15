---
title: Administrar las aplicaciones de Microsoft Power Platform en el Centro de administración de Microsoft Teams
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
ms.openlocfilehash: b44bd77a6415be9c9c9454fd96028fdbb8c608c4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831300"
---
# <a name="manage-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Administrar las aplicaciones de Microsoft Power Platform en el Centro de administración de Microsoft Teams

## <a name="microsoft-power-platform-apps-in-teams"></a>Aplicaciones de Microsoft Power Platform en Teams

Este artículo le ofrece información general sobre cómo administrar las aplicaciones de [Microsoft Power Platform](https://powerplatform.microsoft.com/) en el Centro de administración de Microsoft Teams.

> [!NOTE]
> Este artículo se aplica a las aplicaciones personalizadas creadas por autores de su organización con Power Apps o Power Virtual Agents. Estas aplicaciones personalizadas se agregan automáticamente a Teams. Este artículo no es aplicable a las aplicaciones Power Apps ni a los agentes virtuales que se instalan desde la página Aplicaciones o que se anclan a Teams a través de una directiva de configuración de aplicaciones. Administra esas aplicaciones como lo haría con [](manage-apps.md) cualquier otra [](teams-app-permission-policies.md)aplicación en la página Administrar aplicaciones, usando directivas de permisos de aplicación y directivas [de configuración de aplicaciones.](teams-app-setup-policies.md)

[Power Apps](https://powerapps.microsoft.com) es un entorno de desarrollo de aplicaciones sin código y sin código que los responsables de su organización pueden usar para crear aplicaciones personalizadas que se conecten a los datos de su empresa. [Power Virtual Agents](https://docs.microsoft.com/power-virtual-agents/fundamentals-what-is-power-virtual-agents) es un entorno de creación de bots sin código para que los responsables creen bots potentes. Con la integración de aplicaciones de microsoft Power Platform en Teams, las organizaciones pueden simplificar los procesos empresariales, responder a las necesidades empresariales cambiantes más rápidamente para impulsar una mayor colaboración y crear y compartir soluciones personalizadas para ser más productivos.  

Las aplicaciones de Microsoft Power Platform creadas por autores de su organización se agregan automáticamente a Teams. Los responsables pueden controlar quién puede acceder a su aplicación mediante la característica de uso compartido de [Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app) y la característica de uso compartido de Power [Virtual Agents.](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)

Cuando se crea o comparte una aplicación de Microsoft Power Platform, los **** usuarios pueden verlo e instalarlo en la página Aplicaciones yendo a Nombre de la organización creado por  >  **tus compañeros.** (La aplicación puede tardar unos minutos en crearse o compartirse para que aparezca aquí).

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="Capturas de pantalla de la página de aplicaciones, que muestra las aplicaciones de La plataforma de Energía de Microsoft enumeradas en Integradas por tus compañeros":::

Un usuario verá una aplicación integrada por **sus compañeros si** la aplicación cumple una de las siguientes condiciones.

|Power Apps |Agentes virtuales de Power  |
|---------|---------|
|<ul><li>El usuario ha creado la aplicación.</li><li>La aplicación se ha compartido directamente con el usuario.</li><li>El usuario ha usado recientemente la aplicación. </li></ul>| <ul><li>El usuario ha creado el bot.</li><li>El bot es propiedad de un equipo al que pertenece el usuario. </li></ul>        |

Los usuarios instalan las aplicaciones de Microsoft Power Platform de la misma manera que instalan cualquier otra aplicación de Teams. Tenga en cuenta que los usuarios solo pueden instalar aplicaciones en el contexto en el que tienen permisos, por ejemplo, un equipo de su propiedad, un chat del que forman parte o su ámbito personal.

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Administrar el acceso a las aplicaciones de Microsoft Power Platform en el Centro de administración de Microsoft Teams

Como administrador, puede controlar si las aplicaciones de la Plataforma de energía de Microsoft se muestran en la lista Integrada por sus **compañeros en** la página Aplicaciones de Teams. Puede bloquear o permitir colectivamente todas las aplicaciones creadas en Power Apps o [](manage-apps.md) todas las aplicaciones creadas en Power Virtual Agents en el nivel de organización en la página Administrar aplicaciones o para usuarios específicos con directivas de permisos [de aplicación.](teams-app-permission-policies.md)

Las **aplicaciones Power Apps compartidas** y Shared Power Virtual Agent **Apps** en la tienda de aplicaciones de tu organización representan todas las aplicaciones creadas en esa plataforma en particular. Si bloquea una o ambas aplicaciones en el nivel de la organización o para usuarios **específicos,** dichos usuarios no podrán ver ninguna aplicación de esas plataformas en Built by your colleagues (Integrado por sus compañeros) y no podrán instalarlas en Teams.  

Tenga en cuenta que puede controlar el acceso a todas las aplicaciones creadas en Power Apps y Power Virtual Agents, pero no puede permitir ni bloquear aplicaciones individuales. Los responsables deciden quién puede acceder a las aplicaciones que crean mediante la característica de uso compartido desde Power Apps y Power Virtual Agents. Si un creador compartió una aplicación que creó en Power Virtual Agents con un usuario y bloqueó las aplicaciones compartidas de **Power Virtual Agents** para ese usuario, el usuario no podrá ver ni instalar ninguna aplicación de esa plataforma en Teams.

Si un usuario tiene permiso para acceder a aplicaciones de Power Apps o Power Virtual Agents y, a continuación, bloquea el acceso del usuario a aplicaciones desde una o ambas plataformas, el usuario seguirá teniendo acceso y utilizando las aplicaciones de Microsoft Power Platforms que instalaron antes de que bloqueara la aplicación o las aplicaciones. Sin embargo, el usuario ya no puede ver ni instalar aplicaciones desde esas **plataformas en Built by your colleagues**.

> [!NOTE]
> La **opción Permitir interacción con** aplicaciones personalizadas para toda la organización en la página Administrar aplicaciones se aplica a todos los usuarios de la organización y rige si pueden interactuar con aplicaciones personalizadas. [](manage-apps.md) La configuración de aplicaciones para toda la organización rige el comportamiento de todos los usuarios e invalida cualquier otra directiva de permisos de aplicación asignada a los usuarios. Esta configuración está activada de forma predeterminada. Si esta configuración está desactivada, los usuarios de su organización no podrán ver ni instalar aplicaciones personalizadas, incluidas las aplicaciones de Microsoft Power Platform. Para obtener más información, consulte [Administrar la configuración de aplicaciones para toda la organización.](manage-apps.md#manage-org-wide-app-settings)

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>Permitir o bloquear aplicaciones de Microsoft Power Platform para tu organización

De forma predeterminada, **las aplicaciones compartidas Power Apps** y Shared Power Virtual Agent **están** permitidas para todos los usuarios de Teams en su organización. Puede bloquearlas o permitirlas en el nivel de la organización en la [página](manage-apps.md) Administrar aplicaciones del Centro de administración de Microsoft Teams.  

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Administrar aplicaciones**  >  **de** Teams. Debe ser administrador global o administrador del servicio de Teams para acceder a la página.
2. En la lista de aplicaciones, realice una de las siguientes acciones.

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="Captura de pantalla de la página Administrar aplicaciones, que muestra las aplicaciones compartidas de Microsoft Power Platform":::

    - Para bloquear las aplicaciones creadas en Power Apps o Power Virtual Agents para todos los usuarios de la organización, busque **Aplicaciones power apps** compartidas o aplicaciones compartidas de Power Virtual **Agent,** selecciónelos y, a continuación, haga clic en **Bloquear.**
    - Para permitir que todas las aplicaciones creadas en Power Apps o Power Virtual Agents se puedan usar para todos los usuarios de la organización, busque Aplicaciones **power apps** compartidas o aplicaciones compartidas de Power **Virtual Agent,** selecciónelos y, a continuación, haga clic en **Permitir.**

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a>Permitir o bloquear aplicaciones de Microsoft Power Platform para usuarios específicos

Para permitir o impedir que determinados usuarios de la organización tengan acceso a aplicaciones creadas en Power Apps o Power Virtual Agents, cree y asigne una o varias directivas de permisos de [aplicación personalizadas.](teams-app-permission-policies.md) 

Por ejemplo, para impedir que determinados usuarios tengan acceso a aplicaciones creadas en Power Apps, cree una directiva de permisos de aplicación personalizada para bloquear **Shared Power Apps** y, a continuación, asigne la directiva a esos usuarios.

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="Captura de pantalla de la directiva de permisos de aplicación personalizada de ejemplo con Power Apps compartidos bloqueado":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>Usar registros de auditoría para investigar la actividad de instalación de Microsoft Power Platform

Puede usar los registros de auditoría de Teams para investigar  los eventos en los que los usuarios instalaron las aplicaciones de Microsoft Power Platform desde la sección Integrado por sus compañeros de la página Aplicaciones en Teams. Para ello, [busque](https://docs.microsoft.com/microsoftteams/audit-log-events) en el registro de auditoría del evento **Teams** de la aplicación instalada (en la operación **AppInstalled)** un usuario o un conjunto de usuarios. Para buscar aplicaciones instaladas a partir de **integradas** por sus compañeros, busque el valor **TemplatedInstance** en la propiedad **AppDistributionMode** en los detalles de un registro determinado. 

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="Captura de pantalla del valor TemplatedInstance en la propiedad AppDistributionMode":::

> [!NOTE]
> Puede exportar registros de auditoría en formato CSV para filtrarlos más fácilmente.

## <a name="related-topics"></a>Temas relacionados

- [Compartir una aplicación de lienzo en Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app)
- [Compartir el bot con otros usuarios](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)
- [Administrar aplicaciones en el Centro de administración de Microsoft Teams](manage-apps.md)
- [Administrar directivas de permisos de aplicación en Teams](teams-app-permission-policies.md)
- [Publicar una aplicación personalizada enviada a través de la API de envío de aplicaciones de Teams](submit-approve-custom-apps.md)
