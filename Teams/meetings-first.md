---
title: 'Reunión en primer lugar: Microsoft Teams'
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: lsomi
description: Obtenga información sobre Reuniones en primer lugar, donde los usuarios pueden crear su reunión en Teams, mientras siguen utilizando Skype Empresarial para chat, llamadas y presencia.
localization_priority: Normal
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
ms.openlocfilehash: b75f9bf5328b25a1ce1fd695a90163f63a61f823
ms.sourcegitcommit: bd7847de9d1402476f8faaeae2ff97ec60d86a1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2021
ms.locfileid: "51262587"
---
# <a name="meetings-first"></a>Reuniones primero

"Reuniones primero" está dirigido y optimizado para las organizaciones de Skype Empresarial Server con Telefonía IP empresarial locales que quieren empezar a usar las reuniones de Teams lo más rápido posible. Para estas organizaciones, Meetings First es una alternativa al modo **Islas** que prioriza la experiencia de reuniones de Teams.

## <a name="what-is-meetings-first"></a>¿Qué es Reuniones primero?

Meetings First se basa en el modo de coexistencia **SfBWithTeamsCollabAndMeetings.** Reuniones First no es un producto o una característica: es una configuración que usa las capacidades y características de Teams y Skype Empresarial para proporcionar una experiencia de coexistencia única y personalizada.

En Meetings First, los usuarios crean su reunión en Teams, mientras siguen utilizando Skype Empresarial para chat, llamadas y presencia. No hay ninguna superposición de modalidades entre Teams y Skype Empresarial. El chat, las llamadas y la presencia están en Skype Empresarial y en Teams. Esto permite escenarios únicos "mejor juntos" entre Skype Empresarial y Teams que mejoran la experiencia del usuario durante la coexistencia, así como escenarios de interoperabilidad con usuarios solo de **Teams.**

![Captura de pantalla del mejor escenario junto con Teams y Skype Empresarial](media/meetings-first-meeting-in-meeting.png)

> [!Important]
> Reuniones Primero es una mejor coincidencia para las organizaciones que no tienen o pocos usuarios de chat activos de Teams. Los usuarios de chat de Active Teams no deben cambiarse al modo Reuniones en primer lugar, ya que perderían la capacidad de chatear en Teams y acceder a su historial de chats. En su lugar,  estos usuarios deben estar en modo Islas y Las reuniones en primer lugar solo se conceden a los usuarios que aún no están activos en el chat en Teams.

## <a name="who-should-consider-meetings-first"></a>¿Quién debe considerar Reuniones en primer lugar?

Reuniones First se diseñó para organizaciones que usan Skype Empresarial Server con Telefonía IP empresarial que quieren acelerar su paso a las reuniones de Teams, especialmente aquellos con una disciplina de TI sólida que quieren una ruta de actualización administrada y determinista a Teams.

En el caso de organizaciones complejas o grandes, las migraciones de voz normalmente se realizan en función de un sitio por sitio y pueden tardar mucho tiempo, posiblemente varios años, lo que da como resultado escenarios de coexistencia extendidos. Si esa coexistencia está en modo Islas, los usuarios siempre tendrán la opción de elegir dos soluciones de reunión (Skype Empresarial y Teams), que pueden resultar en situaciones confusas o subóptimas.  A diferencia de las migraciones de voz, las migraciones de reuniones generalmente se pueden completar en toda la empresa en un período corto de tiempo. Las organizaciones que quieran cambiar por completo a las reuniones de Teams lo antes posible (y sin esperar a que se complete su migración de voz) deben considerar Reuniones en primer lugar.

Reuniones En primer lugar, es posible que no sea útil para las organizaciones que no tienen Telefonía IP empresarial usuarios. Estas organizaciones deben poder actualizar a **Teams solo** tan pronto como puedan adoptar reuniones de Teams. Deben considerar omitir Reuniones en primer lugar.

Además, Meetings First es útil para organizaciones cuyo ámbito es una solución de reunión pura, por ejemplo, cuando se emite una RFP "solo para reuniones".

## <a name="capabilities-in-meetings-first"></a>Funcionalidades en Reuniones en primer lugar

Meeting First reúne las siguientes funcionalidades:

- [Aprovisionar un usuario de Skype Empresarial Server (local)](./tutorial-audio-conferencing.yml?tutorial-step=3) con [audioconferencias de Teams.](tutorial-audio-conferencing.yml)
- [Servicio de](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)migración de reuniones: las reuniones organizadas por el usuario se migrarán a la nube y se convertirán en reuniones de Teams a medida que el usuario se promociona a Reuniones primero (requiere Exchange Online).
- Experiencia de usuario simplificada en Teams, centrada en reuniones y equipos y canales de Teams (que, opcionalmente, se pueden ocultar con la directiva [permisos de aplicación);](teams-app-permission-policies.md) [El chat privado, las llamadas](teams-client-experience-and-conformance-to-coexistence-modes.md) y la presencia propia de Teams no se exponen en Reuniones en primer lugar, lo que permite que el esfuerzo de implementación y adopción se centre completamente en las reuniones.
- Experiencia [de reunión superior de Teams.](tutorial-meetings-in-teams.yml)
- "Mejor juntos" entre Teams y Skype Empresarial: 
  - Retención automática: Cuando se encuentra en una reunión de Teams, al recibir una llamada en Skype Empresarial, la reunión de Teams estará en espera y viceversa. Esto impide que los usuarios puedan escuchar sus llamadas privadas por los participantes de las reuniones.
    ![Captura de pantalla del mejor escenario junto con Teams y Skype Empresarial](media/meetings-first-better-together-hold.png)
  - Conciliación de presencia: la actividad en Teams se refleja en la presencia del usuario, que es la presencia de Skype Empresarial, ya que el chat y las llamadas están en Skype Empresarial. En concreto, cuando los usuarios de Meetings First se encuentran en una reunión de Teams, su presencia se actualizará para reflejarlo. Cuando presenten su pantalla, su presencia se actualizará para mostrar No molestar (en función de su configuración en Skype Empresarial).
  - Conciliación del control HID del dispositivo USB (también disponible en Mac): Los controles HID son honrados por Teams durante las reuniones de Teams y por Skype Empresarial en todas las demás circunstancias.
  - A menos que se indique lo contrario, las capacidades de Better Together requieren clientes de escritorio de Windows recientes en este momento.

## <a name="prerequisites-for-meetings-first"></a>Requisitos previos para reuniones en primer lugar

Los únicos requisitos difíciles para Reuniones en primer lugar son los mismos que los requisitos para Teams con Active Directory local y una implementación local de Skype Empresarial:

- [Requisitos previos generales para Teams,](upgrade-plan-journey-prerequisites.md)incluidos
- [Identidad y autenticación en Teams](identify-models-authentication.md) y
- [Configure Azure Active Directory para Teams y Skype Empresarial.](/skypeforbusiness/hybrid/configure-azure-ad-connect)

No [se requiere una topología](/skypeforbusiness/hybrid/configure-federation-with-skype-for-business-online) híbrida de Skype Empresarial, pero se recomienda. Algunas funcionalidades, como el servicio de migración de reuniones y la interoperabilidad, dependen de esa topología.

Reuniones First es compatible con cualquier versión de Skype Empresarial Server (y se sabe que funciona con Lync Server que ya no es compatible). Es compatible con cualquier cliente de Skype Empresarial compatible, pero las capacidades de Better Together requieren un cliente reciente.

Una vez que se cumplen estos requisitos (y no antes), los usuarios pueden obtener licencia para [Microsoft 365 u Office 365 y Teams.](/office365/enterprise/assign-licenses-to-user-accounts)

Para obtener la mejor experiencia de Meetings First, los usuarios deben estar habilitados para [Exchange Online,](exchange-teams-interact.md)SharePoint Online y [OneDrive para](sharepoint-onedrive-interact.md)la Empresa y la creación de grupos de Microsoft 365. Reuniones First es compatible con usuarios cuyo buzón está en Exchange local o que no tienen SharePoint Online, OneDrive para la Empresa o creación de grupos de Microsoft 365. Sin embargo, su experiencia será menos completa. En particular, para las organizaciones que usan Exchange Server local, puede haber (dependiendo de la versión de Exchange Server) algunas limitaciones para crear y ver reuniones desde el cliente de Teams, así como con respecto a las capacidades de cumplimiento.

Como mínimo, los usuarios deben tener [licencia para Teams.](/microsoft-365/admin/manage/assign-licenses-to-users) Además, se pueden licenciar para [audioconferencias,](set-up-audio-conferencing-in-teams.md)si es necesario.

Le recomendamos que [conceda **el modo SfBOnly** **o SfBWithTeamsCollab**](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) como inquilino predeterminado en el momento en que licencia a los usuarios. Esto garantiza que los usuarios no empiecen  a usar Teams por su cuenta en el modo predeterminado islas antes de que esté listo para iniciar Reuniones primero.

Reuniones First es compatible con clientes de escritorio completos (Windows y Mac), en clientes de explorador y en clientes móviles. También es compatible con [Microsoft Teams Rooms.](/microsoftteams/room-systems/) Better Together requiere el cliente de escritorio completo.

## <a name="prepare-for-teams-meetings-in-meetings-first"></a>Prepararse para reuniones de Teams en Reuniones primero

Para que los usuarios tengan la mejor experiencia posible en las reuniones de Teams, debe:

- Siga los pasos de [Reuniones y conferencias para Microsoft Teams,](deploy-meetings-microsoft-teams-landing-page.md)en particular.
- [Evalúe su entorno](3-envision-evaluate-my-environment.md).
- [Prepare la red de su organización para Microsoft Teams.](prepare-network.md)
- Actualice sus salas de reuniones con soluciones y dispositivos de salas de reuniones compatibles con [Teams,](/skypeforbusiness/certification/devices-meeting-rooms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json)o use la interoperabilidad de vídeo en la nube para [Microsoft Teams](cloud-video-interop.md) para permitir que sus salas y dispositivos de terceros existentes se unan a las reuniones de Teams.
- Equipe a los usuarios [con dispositivos de audio y vídeo USB certificados.](/skypeforbusiness/certification/devices-usb-devices?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json)
- Prepárese para [impulsar el conocimiento y la adopción para las reuniones de Teams.](adopt-microsoft-teams-landing-page.md)
- [Planear la administración de servicios](4-envision-plan-my-service-management.md).
- Familiarícese con los informes de Análisis de llamadas enriquecidos para [solucionar problemas de mala calidad de las llamadas.](use-call-analytics-to-troubleshoot-poor-call-quality.md)

Es posible que considere la posibilidad de ejecutar un piloto preparado para producción a escala moderada en esta fase.

## <a name="configure-users-for-meetings-first"></a>Configurar usuarios para reuniones en primer lugar

Una vez que haya autorizado a los usuarios y preparado su organización para reuniones de Teams, es el momento de habilitar a los usuarios para Reuniones en primer lugar. Lo hemos hecho fácil: una sola configuración lo hará todo.

Todas las capacidades y experiencias de usuario en Reuniones en primer lugar, incluida la configuración del cliente de Teams y la [conformidad](teams-client-experience-and-conformance-to-coexistence-modes.md) automática de la experiencia de usuario, servicio de migración de reuniones y capacidades de Better Together, se configuran otorgando al usuario (o grupo de usuarios, o de forma predeterminada del inquilino) el modo de coexistencia [SfBWithTeamsCollabAndMeetings,](setting-your-coexistence-and-upgrade-settings.md) ya sea en el centro de administración de [Microsoft Teams](manage-teams-in-modern-portal.md) o mediante [PowerShell.](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

![Captura de pantalla de la configuración de administración para habilitar Reuniones en primer lugar](media/teams-meeting-admin-settings.png)

Opcionalmente, si desea ocultar la aplicación Teams y Canales de la navegación izquierda del cliente de Teams de los usuarios para centrar aún más su experiencia en reuniones, que se puede lograr mediante la directiva de configuración de la [aplicación.](teams-app-setup-policies.md)

## <a name="reporting-and-call-analytics"></a>Informes y análisis de llamadas

Los análisis de informes y llamadas para reuniones de Teams en Reuniones en primer lugar no cambian de lo que están en otros modos.

## <a name="related-links"></a>Vínculos relacionados

Después de revisar este artículo, es posible que desee consultar Elegir el viaje de [actualización,](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)las instrucciones de migración e interoperabilidad [y](migration-interop-guidance-for-teams-with-skype.md)la coexistencia con [Skype Empresarial](coexistence-chat-calls-presence.md) para obtener más información.
