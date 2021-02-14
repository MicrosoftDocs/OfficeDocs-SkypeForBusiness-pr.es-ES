---
title: 'Actualizar a Teams desde una implementación local de Skype Empresarial: Microsoft Teams'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Actualización de Skype Empresarial a Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bec5c2b10dc2e09092cd7c26284c04868982e287
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533607"
---
# <a name="implement-your-upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>Implementar la actualización de Skype Empresarial a Teams &mdash; para administradores de TI

En este artículo se describe cómo implementar la actualización. Este artículo es el quinto de varios que describen los conceptos de actualización y la implementación para los administradores de TI.  

- [Información general](upgrade-to-teams-on-prem-overview.md)
- [Métodos de actualización](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Herramientas para administrar la actualización](upgrade-to-teams-on-prem-tools.md)
- [Consideraciones adicionales para las organizaciones con Skype Empresarial local](upgrade-to-teams-on-prem-considerations.md)
- **Implementar la actualización** (en este artículo)
- [Consideraciones de la red telefónica conmutada (RTC)](upgrade-to-teams-on-prem-pstn-considerations.md)

Además, en los artículos siguientes se describen conceptos importantes de actualización y comportamientos de coexistencia:

- [Coexistencia de Teams y Skype Empresarial](upgrade-to-teams-on-prem-coexistence.md)
- [Modos de coexistencia - Referencia](migration-interop-guidance-for-teams-with-skype.md)
- [Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a>Opciones de actualización

En esta sección se describe cómo implementar la actualización mediante una de las siguientes opciones de actualización:

- [Actualización de funciones superpuestas (con el modo Islas)](#overlapping-capabilities-upgrade-using-islands-mode)
- [Una actualización de funcionalidades específicas para una organización que aún no ha empezado a usar Teams](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [Actualización de capacidades de selección para una organización que ya usa Teams en modo Islas](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

Si necesita más información sobre las opciones, asegúrese de que ya ha leído los métodos [de actualización.](upgrade-to-teams-on-prem-upgrade-methods.md)

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>Actualización de funciones superpuestas (con el modo Islas)

Para la opción de actualización de funcionalidades superpuestas:

- Considere esta opción si puede realizar una actualización rápida para toda la organización.  Puesto que existe un riesgo potencial de confusión para los usuarios finales que ejecutan ambos clientes, es mejor que pueda minimizar el período de tiempo durante el cual los usuarios deben ejecutar ambos clientes. Debe asegurarse de que los usuarios sepan ejecutar ambos clientes.

- Esta opción es el modelo de configuración rápida y no requiere una acción del administrador para empezar a usar Teams, excepto para asignar la licencia de Microsoft 365 u Office 365. Si sus usuarios ya tienen Skype Empresarial Online, es posible que ya esté en este modelo.

- Puede ser difícil salir del modo de funcionalidad superpuesta y pasar a TeamsOnly. Como los usuarios actualizados solo se comunican a través de Teams, cualquier otro usuario de la organización que se comunique con ese usuario debe usar Teams.  Si tiene usuarios que no han empezado a usar Teams, se exponen a mensajes que faltan. Además, no verán los usuarios de TeamsOnly en línea en Skype Empresarial. Algunas organizaciones eligen realizar una actualización para todo el inquilino mediante la directiva global de inquilinos para evitar esto, sin embargo, eso requiere una planificación inicial, así como esperar hasta que todos los usuarios estén listos para la actualización.


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>Actualización de funcionalidades específicas para una organización que aún no ha empezado a usar Teams

Si su organización aún no tiene ningún usuario activo en Teams, el primer paso es establecer la directiva predeterminada para todo el espacio empresarial para TeamsUpgradePolicy en uno de los modos de Skype Empresarial, por ejemplo, SfbWithTeamsCollab.  Los usuarios que aún no han empezado a usar Teams no observarán ninguna diferencia en el comportamiento. Sin embargo, al establecer esta directiva en el nivel de inquilino, es posible iniciar la actualización de los usuarios al modo TeamsOnly, y garantiza que los usuarios actualizados puedan comunicarse con usuarios no actualizados.  Una vez que haya identificado los usuarios piloto, puede actualizarlos a TeamsOnly.  Si son locales, use Move-CsUser. Si están en línea, simplemente asígneles el modo TeamsOnly mediante Grant-CsTeamsUpgradePolicy. De forma predeterminada, todas las reuniones de Skype Empresarial programadas por estos usuarios se migrarán a Teams.

Estos son los comandos de clave:

1. Establezca el valor predeterminado para todo el espacio empresarial en el modo SfbWithTeamsCollab como se muestra a continuación:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. Actualice los usuarios piloto a TeamsOnly de la siguiente manera:

   - Para un usuario que está conectado:

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - Para un usuario local:

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

Notas
 
- En lugar de establecer la directiva de todo el espacio empresarial en SfbWithTeamsCollab, puede establecerla en SfbWithTeamsCollabAndMeetings. Esto hace que todos los usuarios programe todas las reuniones nuevas en Teams.
- `Move-CsUser` es un cmdlet en las herramientas locales. El `MoveToTeams` cambio requiere Skype Empresarial Server 2019 o Skype Empresarial Server 2015 con CU8 o posterior. Si usa una versión anterior, primero puede mover el usuario a Skype Empresarial Online y, a continuación, otorgar el modo TeamsOnly a ese usuario.
- De forma predeterminada, las reuniones de Skype Empresarial se migran a Teams al actualizar al modo TeamsOnly o al asignar el modo SfbWithTeamsCollabAndMeetings.  

El siguiente diagrama muestra las fases conceptuales de actualización de capacidades de selección para una organización sin uso previo de Teams. El alto de las barras representa el número de usuarios. Durante cualquier fase de la actualización, todos los usuarios pueden comunicarse entre sí.  Los usuarios de Skype Empresarial se comunican con los usuarios de TeamsOnly mediante interoperabilidad y viceversa. Los usuarios en el modo de islas deben asegurarse de ejecutar ambos clientes.

![Diagrama que muestra la actualización de funcionalidades específicas sin uso previo de Teams](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>Actualización de capacidades de selección para una organización que ya usa Teams en modo Islas

Si algunos usuarios de su organización usan activamente Teams en modo islas, es probable que no desee quitar la funcionalidad de los usuarios existentes. Por lo tanto, es necesario realizar un paso adicional antes de cambiar la directiva de todo el espacio empresarial. La solución es "amplio" para estos usuarios activos de Teams existentes en el modo islas, antes de establecer la directiva de todo el espacio empresarial en SfbWithTeamsCollab.  Una vez que haya hecho esto, puede continuar con la implementación como se ha mencionado anteriormente, sin embargo, tendrá dos grupos de usuarios que se trasladarán a TeamsOnly: los usuarios que estaban activos en Teams estarán en modo Islas y los usuarios restantes estarán en modo SfbWithTeamsCollab. Puede mover progresivamente estos usuarios al modo TeamsOnly.

1. Busque usuarios que estén activos en Teams de la siguiente manera:

   1. En el Centro de administración de Microsoft 365, en el panel de navegación izquierdo, vaya a Informes y, a continuación, Uso. 
   2. En el menú desplegable "Seleccionar un informe", elija Microsoft Teams y, después, Actividad del usuario. Esto proporcionará una tabla exportable de usuarios que han estado activos en Teams. 
   3. Haga clic en Exportar, abra Excel y filtre para mostrar solo los usuarios que están activos en Teams.

2. Para cada usuario activo de Teams que se encontró en el paso 1, asígneles el modo Islas en powerShell remoto. Esto le permite ir al siguiente paso y garantiza que no cambie la experiencia del usuario.  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. Establezca la directiva de todo el espacio empresarial en SfbWithTeamsCollab:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. Actualice los usuarios seleccionados al modo TeamsOnly. Puede elegir actualizar los usuarios en modo Islas o en modo SfbWithTeamsCollab, aunque es posible que desee priorizar la actualización de los usuarios en modo islas en primer lugar para minimizar el potencial de confusión que puede surgir cuando los usuarios están en modo Islas.   

   Para usuarios que están en Skype Empresarial Online:  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   Para usuarios que se aloban en Skype Empresarial Server local:  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

El siguiente diagrama muestra las fases conceptuales de una transición de capacidades selectas en la que hay usuarios activos de las Islas al principio. El alto de las barras representa el número de usuarios. Durante cualquier fase de la actualización, todos los usuarios pueden comunicarse entre sí.  Los usuarios de Skype Empresarial se comunican con los usuarios de TeamsOnly mediante interoperabilidad y viceversa. 


![Diagrama que muestra la actualización de capacidades de selección con usuarios activos en el modo Islas](media/teams-upgrade-2.png)

   



## <a name="related-links"></a>Vínculos relacionados

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 u Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover usuarios entre la implementación local y la nube](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configurar su coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usar el servicio de migración de reuniones (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

