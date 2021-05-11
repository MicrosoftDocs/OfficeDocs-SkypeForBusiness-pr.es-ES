---
title: Estrategias de actualización para administradores de TI
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: El artículo es para administradores de TI y describe estrategias para implementar su actualización de Skype Empresarial a Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e4bfb5594b64eb06041e7f761eb0d85cec8c3e5
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52306044"
---
# <a name="upgrade-strategies-for-it-administrators"></a>Estrategias de actualización para administradores de TI

![Fases del viaje de actualización, con énfasis en la fase implementación e implementación](media/upgrade-banner-deployment.png "Fases del viaje de actualización, con énfasis en la fase implementación e implementación")

Este artículo es para administradores de TI que desean implementar su actualización para Teams desde Skype Empresarial.

Antes de implementar la actualización, se recomiendan los siguientes artículos que describen conceptos de actualización importantes y comportamientos de coexistencia:

- [Comprender Microsoft Teams y Skype Empresarial coexistencia e interoperabilidad](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Modos de coexistencia: referencia](migration-interop-guidance-for-teams-with-skype.md)
- [Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a>Opciones de actualización

En esta sección se describe cómo implementar la actualización mediante una de las siguientes opciones de actualización:

- [Actualización de capacidades superpuestas (con el modo Islas)](#overlapping-capabilities-upgrade-using-islands-mode)
- [Una actualización de capacidades de selección para una organización que aún no ha empezado a usar Teams](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [Una actualización de capacidades de selección para una organización que ya usa Teams en modo Islas](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

Si necesita más información sobre las opciones, asegúrese de que ya ha leído Elegir el viaje de actualización de Skype Empresarial [a Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>Actualización de capacidades superpuestas (con el modo Islas)

Para la opción de actualización de funcionalidades superpuestas:

- Considere esta opción si puede realizar una actualización rápida para su organización general.  Dado que existe un riesgo potencial de confusión para los usuarios finales al ejecutar ambos clientes, es mejor si puede minimizar el período de tiempo durante el cual los usuarios deben ejecutar ambos clientes. Debe asegurarse de que los usuarios sepan ejecutar ambos clientes.

- Esta opción es el modelo sin usar y no requiere acción de administrador para empezar con Teams excepto para asignar la licencia Microsoft 365 o Office 365. Si los usuarios ya tienen Skype Empresarial online, es posible que ya esté en este modelo.

- Puede ser difícil salir del modo de capacidades superpuestas y pasar a TeamsOnly. Como los usuarios actualizados solo se comunican Teams, cualquier otro usuario de la organización que se comunique con ese usuario debe usar Teams.  Si tiene usuarios que no han empezado a usar Teams, se mostrarán a los mensajes que faltan. Además, no verán los usuarios de TeamsOnly en línea en Skype Empresarial. Algunas organizaciones eligen realizar una actualización para todo el espacio empresarial con la directiva global Inquilino para evitar esto, pero eso requiere una planificación inicial, así como esperar hasta que todos los usuarios estén listos para actualizarse.


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>Una actualización de capacidades de selección para una organización que aún no ha empezado a usar Teams

Si su organización todavía no tiene usuarios activos en Teams, el primer paso es establecer la directiva predeterminada para todo el espacio empresarial para TeamsUpgradePolicy en uno de los modos Skype Empresarial, por ejemplo, SfbWithTeamsCollab.  Los usuarios que aún no han empezado a usar Teams no notan ninguna diferencia en el comportamiento. Sin embargo, establecer esta directiva en el nivel de inquilino permite empezar a actualizar usuarios al modo TeamsOnly y garantiza que los usuarios actualizados puedan comunicarse con usuarios no actualizados.  Una vez que haya identificado los usuarios piloto, puede actualizarlos a TeamsOnly.  Si son locales, use Move-CsUser. Si están en línea, simplemente asígneles el modo TeamsOnly mediante Grant-CsTeamsUpgradePolicy. De forma predeterminada, Skype Empresarial reuniones programadas por estos usuarios se migrarán a Teams.

Estos son los comandos de clave:

1. Establezca el valor predeterminado para todo el espacio empresarial en el modo SfbWithTeamsCollab de la siguiente manera:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. Actualice los usuarios piloto a TeamsOnly de la siguiente manera:

   - Para un usuario que esté en línea:

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - Para un usuario local:

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

Notas
 
- En lugar de establecer la directiva de todo el espacio empresarial en SfbWithTeamsCollab, puede establecerla en SfbWithTeamsCollabAndMeetings. Esto hace que todos los usuarios programe todas las reuniones nuevas en Teams.
- `Move-CsUser` es un cmdlet en las herramientas locales. El `MoveToTeams` modificador requiere Skype Empresarial Server 2019 o Skype Empresarial Server 2015 con CU8 o posterior. Si usa una versión anterior, primero puede mover el usuario a Skype Empresarial Online y, después, conceder el modo TeamsOnly a ese usuario.
- De forma predeterminada, Skype Empresarial reuniones se migran a Teams al actualizar al modo TeamsOnly o al asignar el modo SfbWithTeamsCollabAndMeetings.  

> [!NOTE]
> En preparación para la próxima retirada de Skype Empresarial Online, Microsoft simplificará la forma en que las organizaciones se desplazan a Teams en un futuro próximo. Al mover un usuario de local a Teams, pronto ya no será necesario especificar el cambio para mover usuarios directamente desde local a `-MoveToTeams` `Move-CsUser` TeamsOnly. Actualmente, si no se especifica este modificador, los usuarios pueden pasar de hospedarse en Skype Empresarial Server local Skype Empresarial Online y su modo permanece sin cambios. Después de la retirada, al mover un usuario de local a la nube con , los usuarios se asignarán automáticamente al modo TeamsOnly y sus reuniones desde locales se convertirán automáticamente en reuniones de Teams, igual que si el modificador se especifica `Move-CsUser` `-MoveToTeams switch had been specified` realmente. Esperamos publicar esta funcionalidad antes de la retirada real del 31 de julio de 2021.


En el siguiente diagrama se muestran las fases conceptuales de la actualización de capacidades de selección para una organización sin el uso previo de Teams. El alto de las barras representa el número de usuarios. Durante cualquier fase de la actualización, todos los usuarios pueden comunicarse entre sí.  Skype Empresarial se comunican con los usuarios de TeamsOnly mediante interoperabilidad y viceversa. Los usuarios en modo Islas deben asegurarse de ejecutar ambos clientes.

![Diagrama que muestra la actualización de capacidades de selección sin el uso previo de Teams](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>Una actualización de capacidades de selección para una organización que ya usa Teams en modo Islas

Si algunos usuarios de su organización usan activamente Teams modo Islas, es probable que no quiera quitar la funcionalidad de los usuarios existentes. Por lo tanto, es necesario realizar un paso adicional antes de cambiar la directiva de todo el espacio empresarial. La solución es "abuelito" de estos usuarios activos existentes Teams en modo Islas, antes de establecer la directiva de todo el espacio empresarial en SfbWithTeamsCollab.  Una vez hecho esto, puede continuar con la implementación como se ha indicado anteriormente, pero tendrá dos grupos de usuarios que se mueven a TeamsOnly: los usuarios que estaban activos en Teams estarán en modo Islas y el resto de los usuarios estarán en modo SfbWithTeamsCollab. Puede mover progresivamente estos usuarios al modo TeamsOnly.

1. Busque usuarios que estén activos en Teams como se muestra a continuación:

   1. Desde el Microsoft 365 de administración, en el panel de navegación izquierdo, vaya a Informes y, a continuación, Uso. 
   2. En el menú desplegable "Seleccionar un informe", elija Microsoft Teams y, a continuación, Actividad del usuario. Esto proporcionará una tabla exportable de usuarios que han estado activos en Teams. 
   3. Haga clic en Exportar, abra Excel y filtre para mostrar solo los usuarios que están activos en Teams.

2. Para cada usuario Teams activo que se encuentra en el paso 1, asígneles el modo Islas en PowerShell remoto. Esto le permite ir al paso siguiente y garantiza que no cambie la experiencia del usuario.  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. Establezca la directiva para todo el espacio empresarial en SfbWithTeamsCollab:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. Actualizar usuarios seleccionados al modo TeamsOnly. Puede elegir actualizar los usuarios en modo Islas o en modo SfbWithTeamsCollab, aunque es posible que desee priorizar la actualización de los usuarios en el modo Islas primero para minimizar el potencial de confusión que puede surgir cuando los usuarios están en modo Islas.   

   Para los usuarios que se alo Skype Empresarial Online:  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   Para los usuarios que se alo Skype Empresarial Server local:  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

El siguiente diagrama muestra las fases conceptuales de una transición de capacidades de selección en la que hay usuarios activos de islas al principio. El alto de las barras representa el número de usuarios. Durante cualquier fase de la actualización, todos los usuarios pueden comunicarse entre sí.  Skype Empresarial usuarios se comunican con los usuarios de TeamsOnly mediante la interoperabilidad y viceversa. 


![Diagrama que muestra la actualización de capacidades de selección con usuarios activos en modo Islas](media/teams-upgrade-2.png)

   



## <a name="related-links"></a>Vínculos relacionados

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 o Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover usuarios entre la implementación local y la nube](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configurar su coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usar el servicio de migración de reuniones (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
