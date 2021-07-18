---
title: Establecer configuración de actualización y coexistencia
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: Obtenga información sobre cómo establecer la configuración de coexistencia y actualización para todos los usuarios de su organización a la vez, o para un único o conjunto de usuarios de su organización.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9419e8ba7339db1fb202e3b5add66935caff7486
ms.sourcegitcommit: 1a622397b5c7fe05e687bb47493fcbca63915d97
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "53447978"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a>Establecer configuración de actualización y coexistencia


Al actualizar su Skype Empresarial usuarios para que usen Teams, tiene varias opciones para ayudarle a que sea un proceso sin problemas para los usuarios. Tiene la opción de realizar la configuración de coexistencia y actualización para todos los usuarios de su organización a la vez, o puede realizar cambios de configuración para un único o conjunto de usuarios de su organización. Tenga en cuenta que las versiones anteriores de Skype Empresarial clientes pueden no respetar esta configuración. Para obtener más información sobre Skype Empresarial de cliente, vaya a la [página Skype Empresarial descargas y actualizaciones.](/skypeforbusiness/software-updates) 

Puede comprender mejor los modos disponibles leyendo Comprender [Microsoft Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) y Skype Empresarial coexistencia e interoperabilidad o Coexistencia con [Skype Empresarial](coexistence-chat-calls-presence.md).  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>Establecer opciones de actualización para todos los usuarios de su organización

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**

1. En el [Microsoft Teams de administración](https://admin.teams.microsoft.com/), en el panel de navegación izquierdo, vaya a Configuración **de** toda la organización  >  **Teams actualización.** 

2. En la parte superior de la **Teams de** actualización, modifique las siguientes opciones según lo desee.

    - Establecer el **modo coexistencia.**
        - **Islas:** use esta configuración si desea que los usuarios puedan usar tanto Skype Empresarial como Teams simultáneamente.
        - **Skype Empresarial:** use esta configuración si desea que los usuarios solo usen Skype Empresarial.
        - **Skype Empresarial con Teams** colaboración: use esta configuración si desea que los usuarios usen Skype Empresarial además de usar Teams para la colaboración de grupo (canales).
        - Skype Empresarial con Teams colaboración y reuniones: use esta configuración si desea que los usuarios usen Skype Empresarial además de usar Teams para la colaboración de grupo **(canales)** y Teams reuniones.
        - **Teams:** use esta configuración si desea que los usuarios solo usen Teams. Tenga en cuenta que, incluso con esta configuración, los usuarios aún pueden unirse a reuniones hospedadas en Skype Empresarial.

          > [!IMPORTANT]
          > Solo puede asignar el modo TeamsOnly a todo el espacio empresarial después de completar los dos pasos siguientes:
          >  - Todos los usuarios locales se han movido a Teams solo con Move-CsUser en el conjunto de herramientas Skype Empresarial Server local.
          >  - Ha actualizado todos los Skype Empresarial DNS para que apunten a Microsoft 365. 
          >
          > Para obtener más información, vea [Deshabilitar la configuración híbrida para completar](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)la migración a Teams solo .
        
    - Establezca **Notificar Skype Empresarial usuarios que Teams está disponible para la actualización.** Si activa esta opción, le dirá a Skype Empresarial usuarios que pronto se actualizarán a la Teams aplicación.

    - Establezca la **aplicación Preferida para que los usuarios se unan Skype Empresarial reuniones.** Esta configuración determina qué aplicación se usa para unirse Skype Empresarial reuniones y se respeta independientemente del valor del modo de coexistencia.
      - **Skype Aplicación Reuniones**
      - **Skype Empresarial con características limitadas**

    - Establezca si desea descargar la Teams en segundo plano para **Skype Empresarial usuarios.**  Esta configuración descarga silenciosamente la aplicación Teams para los usuarios que Skype Empresarial en Windows. Solo se respeta si el modo de coexistencia del usuario Teams o si las notificaciones de actualización pendiente están habilitadas en Skype Empresarial.

3. Haga **clic en Guardar** después de realizar los cambios.

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>Establecer opciones de actualización para un solo usuario de la organización

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**

1. En el panel de navegación izquierdo, vaya **a Usuarios** y, a continuación, seleccione el usuario de la lista. 
2. En la **pestaña Cuenta** del usuario, en **Teams,** haga clic en **Editar.**
3. Puede establecer el modo **coexistencia.** Los modos distintos de Teams Solo se pueden aplicar a los usuarios que se aloen en Skype Empresarial Server local y, por el contrario, solo los usuarios que se aloen en la nube pueden tener el modo TeamsOnly.  Elija una de las siguientes opciones:
     - **Usar la configuración de toda la** organización: use esta configuración si desea que el usuario use la configuración de toda **la** organización. 
     - **Islas:** use esta configuración si desea que el usuario pueda usar tanto Skype Empresarial como Teams. 
     - **Skype Empresarial:** use esta configuración si desea que el usuario use Skype Empresarial.
     - **Skype Empresarial con Teams** colaboración: use esta configuración si desea que el usuario use Skype Empresarial además de usar Teams para la colaboración de grupo (canales).
      - Skype Empresarial con Teams colaboración y reuniones: use esta configuración si desea que el usuario use Skype Empresarial además de usar Teams para la colaboración de grupo **(canales)** y Teams reuniones.
     - **Teams:** use esta configuración si desea que el usuario solo use Teams. El usuario podrá seguir unirse a Skype Empresarial reuniones.
4. Si selecciona  cualquier modo de coexistencia que no sea Usar la configuración de toda la **organización,** tiene la opción de habilitar las notificaciones en la aplicación Skype Empresarial del usuario que actualicen a Teams próximamente. Puede habilitar esta notificación para el usuario activando la opción Notificar **al Skype Empresarial** usuario.
5. Haga **clic en Guardar** después de realizar los cambios.

### <a name="related-topics"></a>Temas relacionados
[Planear el viaje](upgrade-plan-journey.md)

[Comprender el viaje de coexistencia y actualización de Skype Empresarial y Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md)

[Retirar el entorno de Skype Empresarial local](/skypeforbusiness/hybrid/decommission-on-prem-overview)
