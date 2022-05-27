---
title: Estrategias de actualización para administradores de TI
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: El artículo es para administradores de TI y describe estrategias para implementar la actualización de Skype Empresarial a Teams.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f403b12ffc8cabbfebe8a30268eb3e6dad468f32
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681741"
---
# <a name="upgrade-strategies-for-it-administrators"></a>Estrategias de actualización para administradores de TI

![Fases del recorrido de la actualización, con énfasis en la fase de implementación e implementación.](media/upgrade-banner-deployment.png "Fases del recorrido de la actualización, con énfasis en la fase de implementación e implementación")

Este artículo es para administradores de TI que quieran implementar la actualización a Teams desde Skype Empresarial.

Antes de implementar la actualización, le recomendamos los siguientes artículos que describen conceptos de actualización importantes y comportamientos de coexistencia:

- [Comprender Microsoft Teams y Skype Empresarial coexistencia e interoperabilidad](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Modos de coexistencia: referencia](migration-interop-guidance-for-teams-with-skype.md)
- [Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a>Opciones de actualización

En esta sección se describe cómo implementar la actualización mediante una de las siguientes opciones de actualización:

- [Actualización de capacidades superpuestas (usando el modo Islas)](#overlapping-capabilities-upgrade-using-islands-mode)
- [Actualización de funcionalidades seleccionadas para una organización que aún no ha empezado a usar Teams](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [Actualización de funcionalidades seleccionadas para una organización que ya está usando Teams en modo Islas](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

Si necesita más información sobre las opciones, asegúrese de que ya ha leído [Elegir el recorrido de la actualización de Skype Empresarial a Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>Actualización de capacidades superpuestas (usando el modo Islas)

Para la opción de actualización de funciones superpuestas:

- Considere esta opción si puede realizar una actualización rápida para toda la organización.  Dado que existe un riesgo potencial de confusión para los usuarios finales con la ejecución de ambos clientes, es mejor que minimice el período de tiempo durante el cual los usuarios deben ejecutar ambos clientes. Debe asegurarse de que los usuarios saben ejecutar ambos clientes.

- Esta opción es el modelo predefinido y no requiere una acción de administrador para empezar a usar Teams excepto asignar la licencia de Microsoft 365 o Office 365. Si los usuarios ya tienen Skype Empresarial Online, es posible que ya esté en este modelo.

- Puede ser difícil salir del modo de capacidades superpuestas y pasar a TeamsOnly. Como los usuarios actualizados solo se comunican a través de Teams, cualquier otro usuario de la organización que se comunique con ese usuario debe estar usando Teams.  Si tiene usuarios que no han empezado a usar Teams, se mostrarán a mensajes que faltan. Además, no verán los usuarios de TeamsOnly en línea en Skype Empresarial. Algunas organizaciones eligen realizar una actualización para todo el inquilino con la directiva global inquilino para evitar esto, pero eso requiere una planificación inicial, así como esperar hasta que todos los usuarios estén listos para actualizarse.

## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>Actualización de funcionalidades seleccionadas para una organización que aún no ha empezado a usar Teams

Si su organización aún no tiene usuarios activos en Teams, el primer paso es establecer la directiva predeterminada para todo el espacio empresarial para TeamsUpgradePolicy en uno de los modos Skype Empresarial, por ejemplo, SfbWithTeamsCollab.  Los usuarios que aún no han empezado a usar Teams no notan ninguna diferencia de comportamiento. Sin embargo, si establece esta directiva en el nivel de inquilino, podrá empezar a actualizar los usuarios al modo TeamsOnly y se asegurará de que los usuarios actualizados puedan comunicarse con los usuarios no actualizados.  Una vez que haya identificado a los usuarios piloto, puede actualizarlos a TeamsOnly.  Si son locales, use Move-CsUser. Si están en línea, simplemente asígneles el modo TeamsOnly mediante Grant-CsTeamsUpgradePolicy. De forma predeterminada, todas las reuniones de Skype Empresarial programadas por estos usuarios se migrarán a Teams.

Estos son los comandos de tecla:

1. Establezca el valor predeterminado para todo el espacio empresarial en modo SfbWithTeamsCollab como se indica a continuación:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. Actualice los usuarios piloto a TeamsOnly como se indica a continuación:

   - Para un usuario en línea:

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username
     ```

   - Para un usuario local:

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
     ```

**Notas**:

- En lugar de establecer la directiva de todo el espacio empresarial en SfbWithTeamsCollab, podría establecerla en SfbWithTeamsCollabAndMeetings. Esto hace que todos los usuarios programen todas las reuniones nuevas en Teams.
- De forma predeterminada, las reuniones de Skype Empresarial se migran a Teams al actualizar al modo TeamsOnly o al asignar el modo SfbWithTeamsCollabAndMeetings.

> [!NOTE]
> En preparación para la próxima retirada de Skype Empresarial Online, Microsoft ha simplificado la forma en que las organizaciones pasa a Teams. Ya no es necesario especificar el `-MoveToTeams` cambio `Move-CsUser` para mover usuarios directamente desde el entorno local a TeamsOnly. Anteriormente, si no se especificaba este modificador, los usuarios pasaron de estar alojados en Skype Empresarial Server local a Skype Empresarial en línea y su modo se mantuvo inalterado. Ahora, al mover un usuario de local a la nube con `Move-CsUser`, se asigna automáticamente a los usuarios el modo TeamsOnly y sus reuniones locales se convierten automáticamente en reuniones Teams, como si el `-MoveToTeams switch had been specified`, independientemente de si el modificador se especifica realmente. Este comportamiento está disponible en todas las versiones de Skype Para Business Server y Lync Server 2013 (para `-MoveToTeams`las que nunca se ha admitido).

El siguiente diagrama muestra las fases conceptuales de la actualización de capacidades de selección para una organización sin uso previo de Teams. El alto de las barras representa el número de usuarios. Durante cualquier fase de la actualización, todos los usuarios pueden comunicarse entre sí.  Skype Empresarial los usuarios se comunican con TeamsUsuarios puntuales con interoperabilidad y viceversa. Los usuarios en modo Islas deben asegurarse de ejecutar ambos clientes.

![Diagrama que muestra la actualización de funcionalidades seleccionadas sin el uso previo de Teams.](media/teams-upgrade-1.png)

## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>Actualización de funcionalidades seleccionadas para una organización que ya está usando Teams en modo Islas

Si algunos usuarios de su organización usan activamente Teams en modo Islas, probablemente no desee quitar la funcionalidad de los usuarios existentes. Por lo tanto, es necesario realizar un paso adicional antes de cambiar la directiva para todos los inquilinos. La solución es "abuelo" estos usuarios activos existentes Teams en el modo Islas, antes de establecer la directiva de todo el inquilino en SfbWithTeamsCollab.  Una vez hecho esto, puede continuar con la implementación como se indica anteriormente, pero tendrá dos grupos de usuarios que se están moviendo a TeamsOnly: los usuarios que estaban activos en Teams estarán en el modo Islas y el resto de los usuarios estarán en el modo SfbWithTeamsCollab. Puede mover progresivamente estos usuarios al modo TeamsOnly.

1. Busque usuarios que estén activos en Teams como se indica a continuación:

   1. En la Centro de administración de Microsoft 365, en el panel de navegación izquierdo, vaya a Informes y, después, a Uso.
   2. En la lista desplegable "Seleccionar un informe", elija Microsoft Teams y, después, Actividad de usuario. Esto proporcionará una tabla exportable de usuarios que han estado activos en Teams.
   3. Haga clic en Exportar, abra Excel y filtre para mostrar solo los usuarios que están activos en Teams.

2. Para cada usuario de Teams activo que se encontró en el paso 1, asígnele el modo Islas en PowerShell remoto. Esto le permite ir al paso siguiente y asegurarse de que no cambia la experiencia del usuario.

   ```PowerShell
   $users=get-content "C:\MyPath\users.txt"
    foreach ($user in $users){
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands}
   ```

3. Establezca la directiva de todo el espacio empresarial en SfbWithTeamsCollab:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab
   ```

4. Actualizar los usuarios seleccionados al modo TeamsOnly. Puede elegir actualizar los usuarios en el modo Islas o el modo SfbWithTeamsCollab, aunque es posible que desee priorizar la actualización de los usuarios en el modo islas para minimizar el potencial de confusión que puede surgir cuando los usuarios están en modo Islas.

   Para los usuarios alojados en Skype Empresarial Online:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams
   ```

   Para los usuarios alojados en Skype Empresarial Server local:

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
   ```

El diagrama siguiente muestra las fases conceptuales de una transición de capacidades seleccionadas en la que hay usuarios activos de las Islas al principio. El alto de las barras representa el número de usuarios. Durante cualquier fase de la actualización, todos los usuarios pueden comunicarse entre sí.  Skype Empresarial los usuarios se comunican con TeamsUsuarios solo con interoperabilidad y viceversa.

![Diagrama que muestra las capacidades de selección que se actualizan con los usuarios activos en el modo islas.](media/teams-upgrade-2.png)

## <a name="related-links"></a>Vínculos relacionados

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md)

[Configurar la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 o Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover usuarios entre la implementación local y la nube](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configurar su coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[Usar el servicio de migración de reuniones (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
