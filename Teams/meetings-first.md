---
title: 'Reuniones en primer lugar: Microsoft Teams'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: lsomi
description: Obtenga más información sobre reuniones en primer lugar, donde los usuarios pueden crear sus reuniones en Teams, mientras continúan usando Skype Empresarial para chat, llamadas y presencia.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 88be8ef1e43cc9d17fb541f6c56186959aeeb8a4
ms.sourcegitcommit: 401cee68d4f6f9470d614dda12b9cb023f382ff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2022
ms.locfileid: "67999345"
---
# <a name="meetings-first"></a>Reuniones primero

"Reuniones en primer lugar" está dirigido y optimizado para Skype Empresarial Server organizaciones con Telefonía IP empresarial locales que desean empezar a usar las reuniones de Teams lo más rápido posible. Para estas organizaciones, Meetings First es una alternativa al modo **Islas** que prioriza la experiencia de reuniones de Teams.

## <a name="what-is-meetings-first"></a>¿Qué es Reuniones en primer lugar?

Meetings First se basa en el modo de coexistencia **SfBWithTeamsCollabAndMeetings** . Reuniones En primer lugar no es un producto o una característica, es una configuración que usa las capacidades y características de Teams y Skype Empresarial para proporcionar una experiencia de coexistencia única a la medida.

En Reuniones en primer lugar, los usuarios crean su reunión en Teams, mientras siguen usando Skype Empresarial para chat, llamadas y presencia. No hay superposición de modalidades entre Teams y Skype Empresarial. El chat, las llamadas y la presencia están activados en Skype Empresarial y desactivados en Teams. Esta configuración permite escenarios únicos "mejores juntos" entre Skype Empresarial y Teams que mejoran la experiencia del usuario durante la coexistencia, así como escenarios de interoperabilidad con los usuarios **de Teams solo**.

![Captura de pantalla del escenario mejor juntos con Teams y Skype Empresarial.](media/meetings-first-meeting-in-meeting.png)

> [!Important]
> Reuniones en primer lugar es una mejor coincidencia para las organizaciones que no tienen o pocos usuarios activos de chat de Teams. Los usuarios de chat de Active Teams no deben cambiar al modo Reuniones en primer lugar, ya que perderían la capacidad de chatear en Teams y de acceder a su historial de chats. En su lugar, estos usuarios deben estar en modo **Islas** y reuniones solo se conceden a los usuarios que aún no están activos en el chat en Teams.

## <a name="who-should-consider-meetings-first"></a>¿Quién debe considerar Primero las reuniones?

Reuniones en primer lugar es para las organizaciones que usan Skype Empresarial Server con Telefonía IP empresarial que quieren acelerar su cambio a las reuniones de Teams. Reuniones en primer lugar es especialmente para las organizaciones con una disciplina de TI fuerte que quieren una ruta de actualización administrada a Teams.

En el caso de organizaciones complejas o de gran tamaño, las migraciones de voz se realizan normalmente de sitio en sitio en sitio y pueden tardar mucho tiempo, potencialmente varios años, lo que da lugar a escenarios de coexistencia ampliada. Si esa coexistencia está en modo **Islas**, los usuarios siempre tendrán la opción de dos soluciones de reunión (Skype Empresarial y Teams), lo que puede resultar en situaciones confusas o poco adecuadas. A diferencia de las migraciones de voz, las migraciones de reuniones pueden completarse generalmente en toda la compañía en un breve período de tiempo. Las organizaciones que quieran cambiar por completo a las reuniones de Teams lo más rápido posible (y sin esperar a que se complete la migración de voz) deben considerar Reuniones primero.

Reuniones En primer lugar, puede que no sea útil para las organizaciones que no tienen usuarios Telefonía IP empresarial. Estas organizaciones deberían poder actualizar a **Teams solo** en cuanto puedan adoptar las reuniones de Teams. Considere la posibilidad de omitir reuniones en primer lugar.

Además, Reuniones en primer lugar es útil para las organizaciones cuyo ámbito es una solución de reunión de juego puro, por ejemplo, cuando se emite una RFP de "solo reuniones".

## <a name="capabilities-in-meetings-first"></a>Funcionalidades en reuniones en primer lugar

Meeting First reúne las siguientes capacidades:

- [Aprovisione un usuario Skype Empresarial Server (local)](./tutorial-audio-conferencing.yml?tutorial-step=3) con [audioconferencia de Teams](tutorial-audio-conferencing.yml).
- [Servicio de migración](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms) de reuniones: las reuniones organizadas por el usuario se migrarán a la nube y se convertirán en reuniones de Teams a medida que se promueva al usuario a Reuniones primero (requiere Exchange Online).
- Experiencia de usuario simplificada en Teams, centrada en reuniones y equipos y canales de Teams (que se pueden ocultar mediante la [directiva de permisos](teams-app-permission-policies.md) de aplicaciones). [El chat privado, las llamadas y la presencia propia de Teams](teams-client-experience-and-conformance-to-coexistence-modes.md) no se exponen en Reuniones en primer lugar, lo que permite que el esfuerzo de implementación y adopción se centre en las reuniones.
- Experiencia de [reunión de Teams](tutorial-meetings-in-teams.yml) superior.
- "Mejor juntos" entre Teams y Skype Empresarial: 
  - Suspensión automática: cuando se encuentre en una reunión en Teams, al recibir una llamada en Skype Empresarial se pondrá la reunión de Teams en espera y viceversa. Esto evita que los usuarios puedan escuchar sus llamadas privadas por parte de los participantes de la reunión.
    ![Captura de pantalla del escenario mejor juntos con Teams y Skype Empresarial.](media/meetings-first-better-together-hold.png)
  - Conciliación de presencia: la actividad en Teams se refleja en la presencia del usuario, que es la presencia Skype Empresarial ya que el chat y las llamadas están en Skype Empresarial. En concreto, cuando los primeros usuarios de Reuniones se encuentran en una reunión de Teams, su presencia se actualizará para reflejarlo. Cuando presente su pantalla, su presencia se actualizará para mostrar No molestar (en función de la configuración de Skype Empresarial).
  - Conciliación de controles HID del dispositivo USB (también disponible en Mac): Teams respeta los controles HID durante las reuniones de Teams y Skype Empresarial en todas las demás circunstancias.
  - A menos que se indique lo contrario, las capacidades Better Together requieren clientes de escritorio de Windows recientes en este momento.

## <a name="prerequisites-for-meetings-first"></a>Requisitos previos para las reuniones primero

Los únicos requisitos difíciles para Reuniones en primer lugar son los mismos que los requisitos para Teams con Active Directory local y una implementación local Skype Empresarial:

- [Requisitos previos generales para Teams, incluidos](upgrade-plan-journey-prerequisites.md)
- [Identidad y autenticación en Teams](identify-models-authentication.md) y
- [Configure Azure Active Directory para Teams y Skype Empresarial](/skypeforbusiness/hybrid/configure-azure-ad-connect).

No [es necesaria una topología Skype Empresarial híbrida](/skypeforbusiness/hybrid/configure-federation-with-skype-for-business-online), pero se recomienda. Algunas capacidades, como el servicio de migración de reuniones y la interoperabilidad, dependen de esa topología.

Reuniones en primer lugar es compatible con cualquier versión de la Skype Empresarial Server (y se sabe que funciona con el Lync Server que ya no es compatible). Es compatible con cualquier cliente de Skype Empresarial compatible, pero las capacidades Better Together requieren un cliente reciente.

Una vez que se cumplan estos requisitos (y no antes), los usuarios podrán obtener [una licencia de Microsoft 365 o Office 365 y Teams](/office365/enterprise/assign-licenses-to-user-accounts).

Para disfrutar de la mejor experiencia de Reuniones en primer lugar, los usuarios deben estar habilitados para [Exchange Online](exchange-teams-interact.md), [SharePoint Online y OneDrive para la Empresa](sharepoint-onedrive-interact.md), y la creación de grupos de Microsoft 365. Reuniones en primer lugar es compatible con los usuarios cuyo buzón está en Exchange local, que no tienen SharePoint Online o OneDrive para la Empresa, o la creación de grupos de Microsoft 365. Sin embargo, su experiencia será menos completa. Para las organizaciones que usan Exchange Server local, puede haber (en función de la versión de Exchange Server) algunas limitaciones para crear y ver reuniones desde el cliente de Teams y algunas limitaciones con respecto a las capacidades de cumplimiento normativo.

Como mínimo, los usuarios deben tener [licencia para Teams](/microsoft-365/admin/manage/assign-licenses-to-users). Además, se puede obtener una licencia para [Audioconferencia](set-up-audio-conferencing-in-teams.md), si es necesario.

Le recomendamos [que conceda el modo **SfBOnly** o **SfBWithTeamsCollab**](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) como valor predeterminado del espacio empresarial en el momento de conceder la licencia a los usuarios. Esta configuración garantiza que los usuarios no empiecen a usar Teams por su cuenta en el modo **predeterminado de islas** antes de iniciar Reuniones en primer lugar.

Meetings First es compatible con clientes de escritorio completos (Windows y Mac), clientes de explorador y clientes móviles. También es compatible con [Salas de Microsoft Teams](/microsoftteams/room-systems/). Better Together requiere el cliente de escritorio completo.

## <a name="prepare-for-teams-meetings-in-meetings-first"></a>Prepararse para las reuniones de Teams primero en Reuniones

Para que los usuarios tengan la mejor experiencia posible en las reuniones de Teams, debe:

- Siga los pasos de [Reuniones y conferencias para Microsoft Teams](deploy-meetings-microsoft-teams-landing-page.md), en particular.
- [Evalúa tu entorno](3-envision-evaluate-my-environment.md).
- [Prepare la red de su organización para Microsoft Teams](prepare-network.md).
- Actualice sus salas de reuniones con [dispositivos y soluciones](/skypeforbusiness/certification/devices-meeting-rooms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json) compatibles con las salas de reuniones de Teams, o use la interoperabilidad de vídeo en la nube [para Microsoft Teams](cloud-video-interop.md) para habilitar sus salas y dispositivos de terceros existentes para unirse a las reuniones de Teams.
- Equipar a los usuarios con [dispositivos de audio y vídeo USB certificados](/skypeforbusiness/certification/devices-usb-devices?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json).
- Prepárese para [impulsar el conocimiento y la adopción de las reuniones de Teams](adopt-microsoft-teams-landing-page.md).
- [Planee la administración de servicios](4-envision-plan-my-service-management.md).
- Familiarícese con los informes de análisis de llamadas enriquecidos para [solucionar problemas de calidad de llamadas deficientes](use-call-analytics-to-troubleshoot-poor-call-quality.md).

Puede considerar la posibilidad de ejecutar un piloto preparado para producción a escala moderada en esta fase.

## <a name="configure-users-for-meetings-first"></a>Configurar primero los usuarios para reuniones

Una vez que haya autorizado a los usuarios y preparado su organización para las reuniones de Teams, es el momento de habilitar primero a los usuarios para las reuniones. Hemos hecho que sea más fácil: una configuración lo hará todo.

Todas las funcionalidades y experiencias de usuario en Reuniones En primer lugar, incluida la configuración del cliente de Teams y la [conformidad automática](teams-client-experience-and-conformance-to-coexistence-modes.md) de la experiencia del usuario, el servicio de migración de reuniones y las capacidades de Better Together, se configuran al conceder al usuario (o grupo de usuarios, o valor predeterminado del inquilino) el [modo de coexistencia SfBWithTeamsCollabAndMeetings](setting-your-coexistence-and-upgrade-settings.md) en el [Centro de administración de Microsoft Teams](manage-teams-in-modern-portal.md) o mediante [PowerShell](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).

![Captura de pantalla de la configuración de administrador para habilitar Reuniones en primer lugar.](media/teams-meeting-admin-settings.png)

Si quiere ocultar la aplicación Equipos y canales en el panel de navegación izquierdo del cliente de Teams de los usuarios para centrar aún más su experiencia en las reuniones, puede usar la [directiva de configuración](teams-app-setup-policies.md) de aplicaciones.

## <a name="reporting-and-call-analytics"></a>Análisis de informes y llamadas

El análisis de informes y llamadas para las reuniones de Teams en Reuniones en primer lugar no cambia de lo que se encuentran en otros modos.

## <a name="related-links"></a>Vínculos relacionados

Para obtener más información, vea [Elegir el recorrido de la actualización](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md), [Guía de migración e interoperabilidad](migration-interop-guidance-for-teams-with-skype.md) y [Coexistencia con Skype Empresarial](coexistence-chat-calls-presence.md) para obtener más información.
