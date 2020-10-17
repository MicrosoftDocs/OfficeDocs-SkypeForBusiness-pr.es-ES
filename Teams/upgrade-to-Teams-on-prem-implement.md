---
title: Actualizar a teams desde una implementación local de Skype empresarial-Microsoft Teams
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
# <a name="implement-your-upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>Implementar la actualización de Skype empresarial a teams &mdash; para administradores de ti

En este artículo se describe cómo implementar la actualización. Este artículo es el quinto de varios que describen los conceptos de actualización y la implementación para administradores de ti.  

- [Información general](upgrade-to-teams-on-prem-overview.md)
- [Métodos de actualización](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Herramientas para administrar la actualización](upgrade-to-teams-on-prem-tools.md)
- [Consideraciones adicionales para las organizaciones con Skype empresarial local](upgrade-to-teams-on-prem-considerations.md)
- **Implementar la actualización** (este artículo)
- [Consideraciones sobre la red telefónica pública conmutada (RTC)](upgrade-to-teams-on-prem-pstn-considerations.md)

Además, los artículos siguientes describen los conceptos de actualización importantes y los comportamientos de coexistencia:

- [Coexistencia de Teams y Skype empresarial](upgrade-to-teams-on-prem-coexistence.md)
- [Modos de coexistencia: referencia](migration-interop-guidance-for-teams-with-skype.md)
- [Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a>Opciones de actualización

En esta sección se describe cómo implementar la actualización mediante una de las siguientes opciones de actualización:

- [Actualización de capacidades superpuestas (con el modo Islas)](#overlapping-capabilities-upgrade-using-islands-mode)
- [Una actualización de las funciones seleccionadas para una organización que aún no ha empezado a usar Teams](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [Una actualización de las funciones seleccionadas para una organización que ya usa equipos en el modo islas](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

Si necesita más información sobre las opciones, asegúrese de que ya ha leído [los métodos de actualización](upgrade-to-teams-on-prem-upgrade-methods.md).

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>Actualización de capacidades superpuestas (con el modo Islas)

Para la opción de actualización capacidades superpuestas:

- Considere esta opción si puede realizar una actualización rápida para su organización general.  Puesto que hay riesgo potencial de confusión para los usuarios finales que ejecutan ambos clientes, es mejor si puede minimizar el período de tiempo durante el cual los usuarios deben ejecutar ambos clientes. Debe asegurarse de que los usuarios sepan ejecutar ambos clientes.

- Esta opción es el modelo que no está en el equipo y no requiere ninguna acción de administrador para comenzar a usar Teams excepto para asignar la licencia de Microsoft 365 o de Office 365. Si los usuarios ya tienen Skype empresarial online, es posible que ya esté en este modelo.

- Puede resultar difícil sacar provecho del modo de funciones superpuestas y pasar a TeamsOnly. Como los usuarios actualizados solo se comunican a través de Teams, cualquier otro usuario de la organización que se comunique con ese usuario debe estar usando Teams.  Si tiene usuarios que no han empezado a usar Teams, se mostrarán a los mensajes que faltan. Además, no verán los usuarios de TeamsOnly en línea en Skype empresarial. Algunas organizaciones eligen realizar una actualización para todos los inquilinos con la directiva global de inquilino para evitar esto, sin embargo, requieren una planeación inicial, así como la espera hasta que todos los usuarios estén listos para su actualización.


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>Una actualización de las funciones seleccionadas para una organización que aún no ha empezado a usar Teams

Si su organización aún no tiene ningún usuario activo en Teams, el primer paso es establecer la directiva predeterminada para el inquilino para TeamsUpgradePolicy en uno de los modos de Skype empresarial, por ejemplo, SfbWithTeamsCollab.  Los usuarios que aún no hayan comenzado a usar Teams no apreciarán ninguna diferencia en el comportamiento. Sin embargo, la configuración de esta directiva en el nivel de espacio empresarial permite empezar a actualizar usuarios al modo TeamsOnly y garantiza que los usuarios actualizados puedan seguir comunicándose con usuarios no actualizados.  Una vez que hayas identificado a los usuarios de la prueba piloto, puedes actualizarlos a TeamsOnly.  Si son locales, usa Move-CsUser. Si están conectados, simplemente asígnelos a TeamsOnly Mode con Grant-CsTeamsUpgradePolicy. De forma predeterminada, cualquier reunión de Skype empresarial programada por estos usuarios se migrará a teams.

A continuación se muestran los comandos clave:

1. Establezca el valor predeterminado para el inquilino en modo SfbWithTeamsCollab de la siguiente manera:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. Actualice los usuarios de la prueba piloto para que TeamsOnly de la siguiente manera:

   - Para un usuario que está conectado:

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - Para un usuario que sea local:

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

Notas
 
- En lugar de establecer la Directiva de todo el inquilino en SfbWithTeamsCollab, puede establecerla en SfbWithTeamsCollabAndMeetings. Esto hace que todos los usuarios programen todas las reuniones nuevas en Teams.
- `Move-CsUser` es un cmdlet en las herramientas locales. El `MoveToTeams` conmutador requiere Skype empresarial server 2019 o Skype empresarial server 2015 con CU8 o posterior. Si está usando una versión anterior, puede mover primero el usuario a Skype empresarial online y, a continuación, conceder el modo TeamsOnly a ese usuario.
- De forma predeterminada, las reuniones de Skype empresarial se migran a teams al actualizar al modo TeamsOnly o al asignar el modo SfbWithTeamsCollabAndMeetings.  

El diagrama siguiente muestra las fases conceptuales de actualización de las funciones seleccionadas para una organización sin un uso previo de Teams. El alto de las barras representa el número de usuarios. Durante cualquier fase de la actualización, todos los usuarios pueden comunicarse entre sí.  Los usuarios de Skype empresarial se comunican con usuarios de TeamsOnly usando interoperabilidad y viceversa. Los usuarios en modo islas deben asegurarse de ejecutar ambos clientes.

![Diagrama que muestra la selección de funciones de selección sin un uso previo de Teams](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>Una actualización de las funciones seleccionadas para una organización que ya usa equipos en el modo islas

Si algunos usuarios de su organización usan activamente equipos en modo islas, es probable que no desee quitar la funcionalidad de los usuarios existentes. Por lo tanto, es necesario un paso adicional antes de cambiar la Directiva de todo el inquilino. La solución es "abuelo", es decir, los usuarios existentes de equipos activos en modo islas, antes de establecer la política de todos los inquilinos en SfbWithTeamsCollab.  Una vez que lo haya hecho, puede proceder con la implementación como se indica anteriormente, pero tendrá dos grupos de usuarios que se están moviendo a TeamsOnly: los usuarios que estuvieron activos en Teams estarán en modo islas y el resto de usuarios estarán en el modo SfbWithTeamsCollab. Puede mover estos usuarios progresivamente al modo TeamsOnly.

1. Busque usuarios que estén activos en Teams de la siguiente manera:

   1. En el centro de administración de Microsoft 365, en la barra de navegación de la izquierda, vaya a informes y, después, uso. 
   2. En la lista desplegable "seleccionar un informe", elija Microsoft Teams y, a continuación, actividad del usuario. Esto proporcionará una tabla exportable de usuarios que han estado activos en Teams. 
   3. Haga clic en exportar, abrir Excel y filtro para mostrar solo los usuarios que están activos en Teams.

2. Para cada usuario de equipos activos que se encuentra en el paso 1, asigne el modo islas en el PowerShell remoto. Esto le permite ir al paso siguiente y se asegura de que no cambie la experiencia del usuario.  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. Establezca la Directiva de todo el inquilino en SfbWithTeamsCollab:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. Actualice los usuarios seleccionados al modo TeamsOnly. Puede optar por actualizar los usuarios en el modo islas o SfbWithTeamsCollab, aunque es posible que desee dar prioridad a la actualización de los usuarios en el modo islas en primer lugar para minimizar la posibilidad de confusión que puede producirse cuando los usuarios están en modo islas.   

   Para usuarios alojados en Skype empresarial online:  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   Para los usuarios alojados en Skype empresarial Server local:  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

El diagrama siguiente muestra las fases conceptuales de una transición de selección de funciones en la que hay usuarios de islas activas al principio. El alto de las barras representa el número de usuarios. Durante cualquier fase de la actualización, todos los usuarios pueden comunicarse entre sí.  Los usuarios de Skype empresarial se comunican con usuarios de TeamsOnly usando interoperabilidad y viceversa. 


![Diagrama que muestra las funciones de selección actualizar con usuarios activos en modo islas](media/teams-upgrade-2.png)

   



## <a name="related-links"></a>Vínculos relacionados

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar la conectividad híbrida entre Skype empresarial Server y Microsoft 365 u Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover usuarios entre la implementación local y la nube](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configurar su coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usar el servicio de migración de reuniones (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

