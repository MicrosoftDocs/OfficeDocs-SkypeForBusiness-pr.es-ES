---
title: 'Reunión en primer lugar: Microsoft Teams'
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: francoid
description: Obtenga información sobre Reuniones en primer lugar, donde los usuarios pueden crear sus reuniones en Teams y seguir utilizando Skype Empresarial para chat, llamadas y presencia.
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
ms.openlocfilehash: 34b32a1d421941e4e9c3bd743c5db1026d88a2ac
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809510"
---
# <a name="meetings-first"></a>Reuniones primero

"Reuniones en primer lugar" está dirigido y optimizado para las organizaciones de Skype Empresarial Server con Telefonía IP empresarial local que desean empezar a usar las reuniones de Teams lo antes posible. Para estas organizaciones, Reuniones primero es  una alternativa al modo Islas que prioriza la experiencia de reuniones de Teams.

## <a name="what-is-meetings-first"></a>¿Qué es Reuniones en primer lugar?

Reuniones first se basa en el modo de coexistencia **SfBWithTeamsCollabAndMeetings.** Reuniones primero no es un producto o una característica, es una configuración que aprovecha las capacidades y características de Teams y Skype Empresarial para proporcionar una experiencia de coexistencia única y adaptada.

En Reuniones en primer lugar, los usuarios crean su reunión en Teams, mientras siguen utilizando Skype Empresarial para chatear, llamar y presencia. No hay superposición de modalidades entre Teams y Skype Empresarial. El chat, las llamadas y la presencia están en Skype Empresarial y desactivados en Teams. Esto permite escenarios únicos "mejor juntos" entre Skype Empresarial y Teams que mejoran la experiencia del usuario durante la coexistencia, así como escenarios de interoperabilidad con los usuarios **solo de Teams.**

![Captura de pantalla del escenario mejor junto con Teams y Skype Empresarial](media/meetings-first-meeting-in-meeting.png)

> [!Important]
> Reuniones en primer lugar es un mejor resultado para las organizaciones que no tienen o pocos usuarios activos de chat de Teams. Los usuarios activos de chat de Teams no deberían cambiar al modo Reuniones en primer lugar, ya que perderían la capacidad de chatear en Teams y acceder a su historial de chats. En su lugar,  estos usuarios deberían estar en el modo islas y Las reuniones solo se conceden a los usuarios que aún no están activos en el chat en Teams.

## <a name="who-should-consider-meetings-first"></a>¿Quién debe considerar Reuniones en primer lugar?

Reuniones En primer lugar se diseñó para las organizaciones que usan Skype Empresarial Server con Telefonía IP empresarial que desean acelerar su movimiento a las reuniones de Teams, especialmente aquellos con una sólida disciplina de TI que desean una ruta de actualización administrada y determinista a Teams.

En el caso de organizaciones complejas o grandes, las migraciones de voz se realizan normalmente en función de un sitio por sitio y pueden tardar mucho tiempo, potencialmente varios años, lo que podría provocar escenarios de coexistencia extendidos. Si la coexistencia está en modo islas, los usuarios siempre tendrán la opción de elegir dos soluciones de reunión (Skype Empresarial y Teams), que pueden dar lugar a situaciones confusas o suboptimales.  A diferencia de las migraciones de voz, las migraciones de reuniones se pueden completar generalmente en toda la empresa en un período de tiempo corto. Las organizaciones que quieran cambiar completamente a las reuniones de Teams lo antes posible (y sin esperar a que se complete la migración de voz) deben considerar reuniones en primer lugar.

Las reuniones en primer lugar podrían no ser útiles para las organizaciones que no tienen Telefonía IP empresarial usuarios. Estas organizaciones deberían poder actualizar a **Teams solo** en cuanto puedan adoptar las reuniones de Teams. Considere la posibilidad de omitir Reuniones en primer lugar.

Además, Reuniones primero es útil para las organizaciones cuyo ámbito es una solución de reuniones de reproducción pura, por ejemplo, cuando se emite una RFP de "solo reuniones".

## <a name="capabilities-in-meetings-first"></a>Funcionalidades de Reuniones en primer lugar

La reunión en primer lugar reúne las siguientes capacidades:

- [Aprovisionar un usuario de Skype Empresarial Server (local)](https://docs.microsoft.com/microsoftteams/tutorial-audio-conferencing?tutorial-step=3) [con Audioconferencia de Teams.](tutorial-audio-conferencing.yml)
- [Servicio de](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)migración de reuniones: las reuniones organizadas por el usuario se migrarán a la nube y se convertirán a las reuniones de Teams cuando el usuario se promueve a Reuniones en primer lugar (requiere Exchange Online).
- Experiencia de usuario simplificada en Teams, centrada en las reuniones, equipos y canales de Teams (que, opcionalmente, pueden ocultarse con la directiva [de permisos de aplicación](teams-app-permission-policies.md)); [El chat privado, las llamadas](teams-client-experience-and-conformance-to-coexistence-modes.md) y la presencia en Teams no se exponen en Reuniones en primer lugar, lo que permite la implementación y el esfuerzo de adopción para centrarse completamente en las reuniones.
- Experiencia [de reunión de Teams superior.](tutorial-meetings-in-teams.yml)
- "Juntos mejor" entre Teams y Skype Empresarial: 
  - Retención automática: cuando se encuentra en una reunión en Teams, al entrar en una llamada en Skype Empresarial, la reunión de Teams estará en espera y viceversa. Esto impide que los participantes de las reuniones ensayen sus llamadas privadas.
    ![Captura de pantalla del escenario mejor junto con Teams y Skype Empresarial](media/meetings-first-better-together-hold.png)
  - Conciliación de presencia: la actividad en Teams se refleja en la presencia del usuario, que es la presencia de Skype Empresarial, ya que las llamadas y chats están en Skype Empresarial. En concreto, cuando los usuarios de Reuniones En primer lugar se encuentran en una reunión de Teams, su presencia se actualizará para reflejarlo. Cuando presenten su pantalla, su presencia se actualizará para mostrar No molestar (según su configuración en Skype Empresarial).
  - Conciliación de controles HID de dispositivo USB (también disponible en Mac): Teams respeta los controles HID mientras está en reuniones de Teams y skype empresarial en cualquier otra circunstancia.
  - A menos que se indique lo contrario, las funciones de Better Together requieren clientes de escritorio de Windows recientes en este momento.

## <a name="prerequisites-for-meetings-first"></a>Requisitos previos para reuniones primero

Los únicos requisitos más necesarios para Reuniones en primer lugar son los mismos que los requisitos de Teams con Active Directory local y una implementación local de Skype Empresarial:

- [Requisitos previos generales para Teams,](upgrade-plan-journey-prerequisites.md)incluidos
- [Identidad y autenticación en Teams y](identify-models-authentication.md)
- [Configure Azure Active Directory para Teams y Skype Empresarial.](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect)

No [se requiere una topología híbrida de Skype](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-federation-with-skype-for-business-online) Empresarial, pero se recomienda. Algunas funciones, como el servicio de migración de reuniones y la interoperabilidad, dependen de esa topología.

Reuniones primero es compatible con cualquier versión de Skype Empresarial Server (y se sabe que funciona con el servidor de Lync Server que ya no es compatible). Es compatible con cualquier cliente de Skype Empresarial, pero las funcionalidades Better Together requieren un cliente reciente.

Una vez que se cumplen estos requisitos (y no antes), los usuarios pueden obtener una licencia para [Microsoft 365 u Office 365 y Teams.](https://docs.microsoft.com/office365/enterprise/assign-licenses-to-user-accounts)

Para obtener la mejor experiencia de Reuniones en primer lugar, los usuarios deben estar habilitados para [Exchange Online,](exchange-teams-interact.md) [SharePoint Online y OneDrive](sharepoint-onedrive-interact.md)para la Empresa, y la creación de grupos de Microsoft 365. Reuniones primero es compatible con los usuarios cuyo buzón está en Exchange local, que no tienen SharePoint Online o OneDrive para la Empresa, o la creación de grupos de Microsoft 365. Sin embargo, su experiencia será menos completa. En particular, para las organizaciones que usan Exchange Server local, puede haber (dependiendo de la versión de Exchange Server) algunas limitaciones para crear y ver reuniones desde el cliente de Teams, así como con respecto a las capacidades de cumplimiento.

Como mínimo, los usuarios deben tener [licencia para Teams.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) Además, pueden obtener una licencia para [Audioconferencia,](set-up-audio-conferencing-in-teams.md)si es necesario.

Se recomienda conceder [el **modo SfBOnly** **o SfBWithTeamsCollab**](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) como valor predeterminado del inquilino al conceder licencias a los usuarios. Así se garantiza que los usuarios no empiecen a usar Teams por su cuenta en el modo predeterminado de las Islas antes de que usted esté listo para iniciar reuniones en primer lugar. 

Meetings First es compatible con clientes de escritorio completos (Windows y Mac), en clientes de explorador y en clientes móviles. También es compatible con Salas [de Microsoft Teams.](https://docs.microsoft.com/microsoftteams/room-systems/) Juntos mejor requiere el cliente de escritorio completo.

## <a name="prepare-for-teams-meetings-in-meetings-first"></a>Prepararse primero para las reuniones de Teams en Reuniones

Para que los usuarios tengan la mejor experiencia posible en las reuniones de Teams, debe:

- Siga los pasos de [Reuniones y conferencias para Microsoft Teams,](deploy-meetings-microsoft-teams-landing-page.md)en particular.
- [Evaluar el entorno.](3-envision-evaluate-my-environment.md)
- [Prepare la red de su organización para Microsoft Teams.](prepare-network.md)
- Actualice sus salas de reuniones con dispositivos y soluciones que sean compatibles con las salas de reuniones de [Teams,](https://docs.microsoft.com/skypeforbusiness/certification/devices-meeting-rooms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)o use cloud [Video Interoperabilidad](cloud-video-interop.md) para Microsoft Teams para permitir que sus dispositivos y salas de terceros existentes puedan unirse a reuniones de Teams.
- Preparar a los usuarios con [dispositivos de audio y vídeo USB certificados.](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- Prepárese para impulsar [el conocimiento y la adopción de las reuniones de Teams.](adopt-microsoft-teams-landing-page.md)
- [Planee la administración de servicios.](4-envision-plan-my-service-management.md)
- Familiarícese con los informes de análisis de llamadas enriquecidos [para solucionar problemas de mala calidad de las llamadas.](use-call-analytics-to-troubleshoot-poor-call-quality.md)

Considere la posibilidad de ejecutar un piloto preparado para la producción de escala moderada en esta fase.

## <a name="configure-users-for-meetings-first"></a>Configurar los usuarios para reuniones en primer lugar

Una vez que haya autorizado a los usuarios y preparado su organización para las reuniones de Teams, es el momento de habilitar a los usuarios para reuniones en primer lugar. Lo hemos hecho más fácil: con una sola configuración, todo se podrá hacer.

Todas las funcionalidades y experiencias de usuario en Reuniones en primer lugar, incluida la configuración del cliente de Teams y la [conformidad](teams-client-experience-and-conformance-to-coexistence-modes.md) automática de la experiencia del usuario, el servicio de migración de reuniones y las capacidades mejor juntas, se configuran al conceder al usuario (o grupo de usuarios o valor predeterminado del espacio empresarial) el modo de coexistencia [SfBWithTeamsCollabAndMeetings](setting-your-coexistence-and-upgrade-settings.md) en el centro de administración de [Microsoft Teams](manage-teams-in-modern-portal.md) o mediante [PowerShell.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

![Captura de pantalla de la configuración de administración para habilitar Reuniones en primer lugar](media/teams-meeting-admin-settings.png)

Opcionalmente, si quiere ocultar la aplicación Equipos y canales del panel de navegación izquierdo del cliente de Teams de los usuarios para centrar más su experiencia en las reuniones, esto puede conseguirse con la directiva de permisos de [aplicación.](teams-app-permission-policies.md)

## <a name="reporting-and-call-analytics"></a>Informes y análisis de llamadas

Los informes y el análisis de llamadas para las reuniones de Teams en reuniones en primer lugar no cambian de lo que hacen en otros modos.

## <a name="related-links"></a>Vínculos relacionados

Después de revisar este artículo, es posible que [](migration-interop-guidance-for-teams-with-skype.md)desee consultar Elegir el viaje de [actualización,](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)las instrucciones de migración e interoperabilidad y la coexistencia con [Skype](coexistence-chat-calls-presence.md) Empresarial para obtener más información.


