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
description: Obtenga información sobre cómo establecer la coexistencia y la actualización de la configuración para todos los usuarios de la organización a la vez, o para un único o conjunto de usuarios de su organización.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8062c4a9b12c067091fcc95f192ac519f680937d
ms.sourcegitcommit: 480046a53dfb6e6cf867e1920f8fb43dda9d3774
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2022
ms.locfileid: "64846539"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a>Establecer configuración de actualización y coexistencia


Al actualizar su Skype Empresarial usuarios para que usen Teams, tiene varias opciones para ayudarle a que sea un proceso perfecto para sus usuarios. Tiene la opción de realizar configuraciones de coexistencia y actualización para todos los usuarios de la organización a la vez, o puede realizar cambios en la configuración para un único o conjunto de usuarios de su organización. Tenga en cuenta que es posible que las versiones anteriores de Skype Empresarial clientes no respeten esta configuración. Para obtener más información sobre Skype Empresarial versiones del cliente, ve a la [página Skype Empresarial descargas y actualizaciones](/skypeforbusiness/software-updates). 

Puede comprender mejor los modos disponibles leyendo [Comprender Microsoft Teams y Skype Empresarial coexistencia e interoperabilidad](teams-and-skypeforbusiness-coexistence-and-interoperability.md) o [Coexistencia con Skype Empresarial](coexistence-chat-calls-presence.md).  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>Establecer opciones de actualización para todos los usuarios de la organización

 **Usar el Centro de administración de Microsoft Teams**

1. En el [centro de administración de Microsoft Teams](https://admin.teams.microsoft.com/), en el panel de navegación izquierdo, vaya a **Teams** >  **Teams configuración de actualización**. 

2. En la parte superior de la Teams página **de actualización**, modifique las siguientes opciones como desee.

    - Establecer el modo **de coexistencia** .
        - **Islas**: use esta configuración si quiere que los usuarios puedan usar Skype Empresarial y Teams simultáneamente.
        - **solo Skype Empresarial**: use esta opción si quiere que los usuarios solo usen Skype Empresarial.
        - **Skype Empresarial con la colaboración Teams**: use esta opción si desea que los usuarios usen Skype Empresarial además de usar Teams para la colaboración en grupo (canales).
        - **Skype Empresarial con Teams colaboración y reuniones**: use esta configuración si desea que los usuarios usen Skype Empresarial, además de usar Teams para la colaboración en grupo (canales) y reuniones Teams.
        - **solo Teams**: use esta opción si quiere que los usuarios solo usen Teams. Tenga en cuenta que, incluso con esta configuración, los usuarios pueden unirse a reuniones hospedadas en Skype Empresarial.

          > [!IMPORTANT]
          > Solo puede asignar el modo TeamsOnly a todo el inquilino después de completar los dos pasos siguientes:
          >  - Todos los usuarios locales se han movido a Teams Solo con Move-CsUser en el conjunto de herramientas local Skype Empresarial Server.
          >  - Ha actualizado los registros DNS de Skype Empresarial para que apunten a Microsoft 365. 
          >
          > Para obtener más información, vea [Deshabilitar la configuración híbrida para completar la migración a solo Teams](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).
        
    - Establezca **Notificar Skype Empresarial a los usuarios que Teams está disponible para la actualización**. Si activa esta opción, se indicará a los usuarios de Skype Empresarial que pronto se actualizarán a la aplicación Teams.

    - Establezca la **aplicación Preferida para que los usuarios se unan a Skype Empresarial reuniones**. Esta configuración determina qué aplicación se usa para unirse a Skype Empresarial reuniones y se respeta independientemente del valor del modo de coexistencia.
      - **aplicación Reuniones de Skype**
      - **Skype Empresarial con características limitadas**

    - Establezca si desea **Descargar la aplicación Teams en segundo plano para Skype Empresarial usuarios**. Esta configuración descarga de forma silenciosa la aplicación Teams para los usuarios que ejecutan Skype Empresarial en Windows. Solo se respeta si el modo de coexistencia para el usuario se Teams solo o si las notificaciones de la actualización pendiente están habilitadas en Skype Empresarial.

3. Haga clic en **Guardar** después de realizar los cambios.

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>Establecer las opciones de actualización para un único usuario de la organización

 **Usar el Centro de administración de Microsoft Teams**

1. En el panel de navegación izquierdo, vaya a **UsuariosAdministrar** >  usuarios y, después, seleccione el usuario en la lista. 
2. En la pestaña **Cuenta** del usuario, en **Teams actualización**, haga clic en **Editar**.
3. Puede establecer el **modo de coexistencia**. Los modos que no sean Teams Solo se pueden aplicar a los usuarios alojados en Skype Empresarial Server local y, por el contrario, solo los usuarios alojados en la nube pueden tener el modo TeamsOnly.  Elija una de las siguientes opciones:
     - **Usar la configuración de toda** la organización: use esta opción si desea que el usuario use la configuración **de toda la** organización. 
     - **Islas**: use esta configuración si desea que el usuario pueda usar Skype Empresarial y Teams. 
     - **solo Skype Empresarial**: use esta opción si desea que el usuario use Skype Empresarial.
     - **Skype Empresarial con la colaboración Teams**: use esta configuración si desea que el usuario use Skype Empresarial además de usar Teams para la colaboración en grupo (canales).
      - **Skype Empresarial con Teams colaboración y reuniones**: use esta configuración si desea que el usuario use Skype Empresarial, además de usar Teams para la colaboración en grupo (canales) y Teams reuniones.
     - **solo Teams**: use esta opción si desea que el usuario use solo Teams. El usuario aún podrá unirse a Skype Empresarial reuniones.
4. Si selecciona cualquier **modo de coexistencia** que no sea **Usar la configuración de toda** la organización, tiene la opción de habilitar las notificaciones en la aplicación Skype Empresarial del usuario que se actualicen a Teams estará disponible próximamente. Puede habilitar esta notificación para el usuario activando la opción **Notificar al usuario Skype Empresarial**.
5. Haga clic en **Guardar** después de realizar los cambios.

### <a name="related-topics"></a>Temas relacionados
[Planear el viaje](upgrade-plan-journey.md)

[Comprender la coexistencia y el viaje de actualización para Skype Empresarial y Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md)

[Retirar el entorno Skype Empresarial local](/skypeforbusiness/hybrid/decommission-on-prem-overview)
