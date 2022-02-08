---
title: 'Reunión en primer lugar: Microsoft Teams'
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: lsomi
description: Obtenga información sobre Reuniones en primer lugar, donde los usuarios pueden crear su reunión en Teams, mientras siguen utilizando Skype Empresarial para chat, llamadas y presencia.
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
ms.openlocfilehash: d8e1f6519bab87137d978ed6792d12eb37bffac7
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385328"
---
# <a name="meetings-first"></a>Reuniones primero

"Reuniones en primer lugar" está dirigido y optimizado para Skype Empresarial Server organizaciones con Telefonía IP empresarial locales que quieren empezar a usar reuniones Teams lo más rápido posible. Para estas organizaciones, Meetings First es una alternativa al modo **Islas** que prioriza la experiencia Teams reuniones.

## <a name="what-is-meetings-first"></a>¿Qué es Reuniones primero?

Meetings First se basa en el modo de coexistencia **SfBWithTeamsCollabAndMeetings** . Reuniones Primero no es un producto o una característica: es una configuración que usa funcionalidades y características de Teams y Skype Empresarial para proporcionar una experiencia de coexistencia única y personalizada.

En Meetings First, los usuarios crean su reunión en Teams, mientras siguen utilizando Skype Empresarial chat, llamadas y presencia. No hay ninguna superposición de modalidades entre Teams y Skype Empresarial. El chat, las llamadas y la presencia están en Skype Empresarial y desactivados en Teams. Esto permite escenarios únicos "mejor juntos" entre Skype Empresarial y Teams que mejoran la experiencia del usuario durante la coexistencia, así como escenarios de interoperabilidad con Teams **solo** los usuarios.

![Captura de pantalla del mejor escenario junto con Teams y Skype Empresarial.](media/meetings-first-meeting-in-meeting.png)

> [!Important]
> Reuniones Primero es una mejor coincidencia para las organizaciones que no tienen o pocos usuarios de chat Teams activos. Los Teams de chat activos no deben cambiarse al modo Reuniones en primer lugar, ya que perderían la capacidad de chatear en Teams y acceder a su historial de chats. Estos usuarios deben estar en modo Islas  en su lugar, y Reuniones Primero solo se concede a los usuarios que aún no están activos en el chat en Teams.

## <a name="who-should-consider-meetings-first"></a>Quién debería considerar Reuniones en primer lugar?

Reuniones First se diseñó para organizaciones que usan Skype Empresarial Server con Telefonía IP empresarial que quieren acelerar su paso a reuniones de Teams, especialmente aquellas con una disciplina de TI sólida que desean una ruta de actualización administrada y determinista Teams.

En el caso de organizaciones complejas o grandes, las migraciones de voz normalmente se realizan en función de un sitio por sitio y pueden tardar mucho tiempo, posiblemente varios años, lo que da como resultado escenarios de coexistencia extendidos. Si esa coexistencia está  en modo Islas, los usuarios siempre tendrán la opción de elegir dos soluciones de reunión (Skype Empresarial y Teams), que pueden dar lugar a situaciones confusas o subóptimas. A diferencia de las migraciones de voz, las migraciones de reuniones generalmente se pueden completar en toda la empresa en un período corto de tiempo. Las organizaciones que quieren cambiar por completo Teams reuniones lo antes posible (y sin esperar a que se complete su migración de voz) deben considerar Reuniones en primer lugar.

Las reuniones primero pueden no ser útiles para las organizaciones que no tienen Telefonía IP empresarial usuarios. Estas organizaciones deben poder actualizar a **Teams solo** tan pronto como puedan adoptar Teams reuniones. Deben considerar omitir Reuniones en primer lugar.

Además, Meetings First es útil para organizaciones cuyo ámbito es una solución de reunión pura, por ejemplo, cuando se emite una RFP "solo para reuniones".

## <a name="capabilities-in-meetings-first"></a>Funcionalidades en Reuniones en primer lugar

Meeting First reúne las siguientes funcionalidades:

- [Aprovisione Skype Empresarial Server usuario (local)](./tutorial-audio-conferencing.yml?tutorial-step=3) con [Teams audioconferencia.](tutorial-audio-conferencing.yml)
- [Servicio de](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms) migración de reuniones: las reuniones organizadas por el usuario se migrarán Teams la nube y se convertirán en reuniones Teams medida que el usuario se convierta en Reuniones primero (requiere Exchange Online).
- Experiencia de usuario simplificada en Teams, centrada en Teams reuniones y equipos y [canales](teams-app-permission-policies.md) (que, opcionalmente, se pueden ocultar con la directiva permisos de aplicación); [Teams chat privado,](teams-client-experience-and-conformance-to-coexistence-modes.md) llamadas y presencia propia no se exponen en Reuniones en primer lugar, lo que permite que el esfuerzo de implementación y adopción se centre completamente en las reuniones.
- Experiencia [Teams reunión superior](tutorial-meetings-in-teams.yml).
- "Mejor juntos" entre Teams y Skype Empresarial: 
  - Retención automática: cuando se encuentra en una reunión de Teams, al recibir una llamada en Skype Empresarial, la reunión de Teams estará en espera y viceversa. Esto impide que los usuarios puedan escuchar sus llamadas privadas por los participantes de las reuniones.
    ![Captura de pantalla del mejor escenario junto con Teams y Skype Empresarial.](media/meetings-first-better-together-hold.png)
  - Conciliación de presencia: la actividad en Teams se refleja en la presencia del usuario, que es la presencia Skype Empresarial ya que el chat y las llamadas están en Skype Empresarial. En concreto, cuando los usuarios de Meetings First se encuentran en una reunión Teams, su presencia se actualizará para reflejarlo. Cuando presenten su pantalla, su presencia se actualizará para mostrar No molestar (en función de su configuración en Skype Empresarial).
  - Conciliación del control HID del dispositivo USB (también disponible en Mac): los controles HID se respetan por Teams mientras se encuentran en Teams reuniones y por Skype Empresarial en todas las demás circunstancias.
  - A menos que se indique lo contrario, las capacidades de Better Together requieren Windows clientes de escritorio recientes en este momento.

## <a name="prerequisites-for-meetings-first"></a>Requisitos previos para reuniones en primer lugar

Los únicos requisitos difíciles para Meetings First son los mismos que los requisitos para Teams con Active Directory local y una implementación local Skype Empresarial local:

- [Requisitos previos generales para Teams](upgrade-plan-journey-prerequisites.md), incluido
- [Identidad y autenticación en Teams](identify-models-authentication.md) y
- [Configure Azure Active Directory para Teams y Skype Empresarial](/skypeforbusiness/hybrid/configure-azure-ad-connect).

No [Skype Empresarial una topología](/skypeforbusiness/hybrid/configure-federation-with-skype-for-business-online) híbrida, pero se recomienda. Algunas funcionalidades, como el servicio de migración de reuniones y la interoperabilidad, dependen de esa topología.

Reuniones First es compatible con cualquier versión del Skype Empresarial Server (y se sabe que funciona con Lync Server que ya no es compatible). Es compatible con cualquier cliente Skype Empresarial, pero las capacidades de Better Together requieren un cliente reciente.

Una vez que se cumplen estos requisitos (y no antes), los usuarios pueden obtener licencia para Microsoft 365 o Office 365 [y Teams](/office365/enterprise/assign-licenses-to-user-accounts).

Para obtener la mejor experiencia de Meetings First, los usuarios deben estar habilitados para [Exchange Online,](exchange-teams-interact.md) [SharePoint Online y](sharepoint-onedrive-interact.md) OneDrive para la Empresa y Microsoft 365 grupo. Reuniones First es compatible con usuarios cuyo buzón está en Exchange local o que no tienen SharePoint Online o OneDrive Para empresas, o Microsoft 365 creación de grupos. Sin embargo, su experiencia será menos completa. En particular, para las organizaciones que usan Exchange Server local, puede haber (según la versión de Exchange Server) algunas limitaciones para crear y ver reuniones desde el cliente de Teams, así como con respecto a las capacidades de cumplimiento.

Como mínimo, los usuarios deben tener [licencia para Teams](/microsoft-365/admin/manage/assign-licenses-to-users). Además, se pueden obtener licencias para [audioconferencias](set-up-audio-conferencing-in-teams.md), si es necesario.

Le recomendamos que [conceda **el modo SfBOnly** **o SfBWithTeamsCollab**](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) como inquilino predeterminado en el momento en que licencia a los usuarios. Esto garantiza que los usuarios no empiecen a usar Teams por su cuenta en el modo predeterminado  islas antes de que esté listo para iniciar Reuniones primero.

Reuniones First es compatible con clientes de escritorio completo (Windows y Mac), en clientes de explorador y en clientes móviles. También es compatible con [Salas de Microsoft Teams](/microsoftteams/room-systems/). Better Together requiere el cliente de escritorio completo.

## <a name="prepare-for-teams-meetings-in-meetings-first"></a>Prepararse Teams reuniones en Reuniones primero

Para que los usuarios tengan la mejor experiencia posible en Teams reuniones, debe:

- Siga los pasos de [Reuniones y conferencias para Microsoft Teams](deploy-meetings-microsoft-teams-landing-page.md), en particular.
- [Evalúe su entorno](3-envision-evaluate-my-environment.md).
- [Prepare la red de su organización para Microsoft Teams](prepare-network.md).
- Teams Actualice sus salas de reuniones con soluciones y dispositivos de salas de reuniones [compatibles, o](/skypeforbusiness/certification/devices-meeting-rooms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json) use la interoperabilidad de vídeo en la nube para [Microsoft Teams](cloud-video-interop.md) para permitir que sus salas y dispositivos de terceros existentes se unan Teams reuniones.
- Equipe a los usuarios con [dispositivos de audio y vídeo USB certificados](/skypeforbusiness/certification/devices-usb-devices?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json).
- Prepárese para [impulsar el conocimiento y la adopción para Teams reuniones](adopt-microsoft-teams-landing-page.md).
- [Planee la administración de servicios](4-envision-plan-my-service-management.md).
- Familiarícese con los informes de Análisis de llamadas enriquecidos para [solucionar problemas de mala calidad de las llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md).

Es posible que considere la posibilidad de ejecutar un piloto preparado para producción a escala moderada en esta fase.

## <a name="configure-users-for-meetings-first"></a>Configurar usuarios para reuniones en primer lugar

Una vez que haya autorizado a los usuarios y preparado su organización para Teams reuniones, es el momento de habilitar los usuarios para Reuniones primero. Lo hemos hecho fácil: una sola configuración lo hará todo.

Todas las capacidades y experiencias de usuario en Reuniones en primer lugar, incluida la configuración de cliente de Teams y la [conformidad](teams-client-experience-and-conformance-to-coexistence-modes.md) automática de la experiencia de usuario, servicio de migración de reuniones y capacidades de Better Together, se configuran otorgando al usuario (o grupo de usuarios, o de forma predeterminada del inquilino) el modo de coexistencia [sfBWithTeamsCollabAndMeetings](setting-your-coexistence-and-upgrade-settings.md), ya sea en el centro de administración de [Microsoft Teams](manage-teams-in-modern-portal.md) [o mediante el uso del modo de coexistencia PowerShell](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).

![Captura de pantalla de la configuración de administrador para habilitar Reuniones en primer lugar.](media/teams-meeting-admin-settings.png)

Opcionalmente, si desea ocultar la aplicación Teams y Canales de la navegación izquierda del cliente de Teams de los usuarios para centrar aún más su experiencia en reuniones, esto se puede lograr con la directiva de configuración de la [aplicación.](teams-app-setup-policies.md)

## <a name="reporting-and-call-analytics"></a>Informes y análisis de llamadas

Los informes y los análisis de llamadas para Teams reuniones en Reuniones en primer lugar no cambian de lo que están en otros modos.

## <a name="related-links"></a>Vínculos relacionados

Después de revisar este artículo, es posible que desee consultar Elegir el viaje de [actualización, Las](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md) instrucciones de migración e [](coexistence-chat-calls-presence.md) interoperabilidad [y Coexistencia](migration-interop-guidance-for-teams-with-skype.md) con Skype Empresarial para obtener más información.
