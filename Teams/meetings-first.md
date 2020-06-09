---
title: Reunión en primer lugar-Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: francoid
description: Obtenga más información sobre las reuniones en primer lugar, donde los usuarios pueden crear su reunión en Teams, sin dejar de usar Skype empresarial para conversaciones, llamadas y presencia.
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
ms.openlocfilehash: 4e2ca0b4088a7855da8cf2bc5196ecc9f2082475
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "44637949"
---
# <a name="meetings-first"></a>Reuniones primero

"El primero de las reuniones" está dirigido y optimizado para organizaciones de Skype empresarial Server con Enterprise Voice on local que desean comenzar a usar las reuniones de Teams tan rápido como sea posible. Para estas organizaciones, las reuniones primero son una alternativa al uso del modo **islas** que da prioridad a la experiencia de reuniones de Teams.

## <a name="what-is-meetings-first"></a>¿Qué son las reuniones en primer lugar?

Las reuniones primero se basan en el modo de coexistencia de **SfBWithTeamsCollabAndMeetings** . En primer lugar, reuniones no es un producto ni una característica: es una configuración que aprovecha las capacidades y características de Teams y de Skype empresarial para proporcionar una experiencia de coexistencia adaptada exclusiva.

En las reuniones en primer lugar, los usuarios crean su reunión en Teams, mientras continúan usando Skype empresarial para conversaciones, llamadas y presencia. No hay ninguna superposición de modalidades entre Teams y Skype empresarial. La conversación, las llamadas y la presencia están activadas en Skype empresarial y desactivadas en Teams. Esto permite escenarios únicos "juntos" entre Skype empresarial y los equipos que mejoran la experiencia del usuario durante la coexistencia, así como escenarios de interoperabilidad con usuarios **solo de Teams** .

![Captura de pantalla del mejor escenario con Teams y Skype empresarial](media/meetings-first-meeting-in-meeting.png)

> [!Important]
> Las reuniones primero son más coincidentes para las organizaciones que tienen usuarios de la conversación de Active Teams. Los usuarios de la conversación de Active Teams no deben cambiar al modo de las reuniones en primer lugar, ya que perderían la posibilidad de chatear en Teams y acceder a su historial de chats. En su lugar, estos usuarios deben tener el modo **islas** y las reuniones solo se conceden a los usuarios que aún no están activos en la conversación en Teams.

## <a name="who-should-consider-meetings-first"></a>¿Quién debe considerar primero las reuniones?

En primer lugar, las reuniones se diseñaron para organizaciones que usan Skype empresarial Server con telefonía IP que desean acelerar su movimiento a reuniones de Teams, especialmente aquellos con una disciplina de ti sólida que desean una ruta de actualización determinista administrada a teams.

En el caso de organizaciones complejas o grandes, las migraciones de voz suelen hacerse en cada sitio y pueden tardar mucho tiempo, posiblemente varios años, generando grandes escenarios de coexistencia. Si esa coexistencia está en modo **islas** , los usuarios siempre tendrán la opción de dos soluciones de reunión (Skype empresarial y Teams), lo que puede dar lugar a situaciones confusas o subóptimas. A diferencia de las migraciones de voz, las migraciones de reuniones generalmente se pueden completar en toda la empresa en un breve período de tiempo. Las organizaciones que deseen cambiar de reunión a las reuniones de Teams tan rápido como sea posible (y sin esperar a que se complete la migración de voz) deberían considerar las reuniones en primer lugar.

Es posible que en primer lugar las reuniones no sean útiles para organizaciones que no tienen usuarios de voz de empresa. Estas organizaciones deberían poder actualizarse a **Teams** tan pronto como puedan adoptar reuniones de Teams. Deberían considerar la posibilidad de omitir las reuniones en primer lugar.

Además, las reuniones son útiles para las organizaciones cuyo ámbito es una solución de reunión de reproducción pura, por ejemplo, cuando se emite una RFP de "reuniones-solo".

## <a name="capabilities-in-meetings-first"></a>Características de las reuniones en primer lugar

Reunión, en primer lugar, reúne las siguientes funciones:

- [Aprovisionar un usuario de Skype empresarial Server (local)](https://docs.microsoft.com/microsoftteams/tutorial-audio-conferencing?tutorial-step=3) con la [Conferencia de audio de Teams](tutorial-audio-conferencing.yml).
- [Servicio de migración de reuniones](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms): las reuniones organizadas por el usuario se migrarán a la nube y se convertirán en reuniones de Teams, ya que el usuario se promueve a reuniones en primer lugar (requiere Exchange Online).
- Experiencia de usuario optimizada en Teams, centrada en las reuniones de Teams y los equipos y canales (que, opcionalmente, se pueden ocultar con la [Directiva de permisos de aplicaciones](teams-app-permission-policies.md)); Los [equipos de chat privado, las llamadas y la presencia propia](teams-client-experience-and-conformance-to-coexistence-modes.md) no se exponen en las reuniones en primer lugar, lo que permite el esfuerzo de implementación y adopción para centrarse plenamente en las reuniones.
- [Experiencia de reunión de equipos](tutorial-meetings-in-teams.yml)superiores.
- "Juntos es mejor" entre equipos y Skype empresarial: 
  - Suspensión automática: cuando se encuentra en una reunión en Teams, al entrar en una llamada en Skype empresarial, se pondrá en espera los equipos de la reunión y viceversa. Esto evita que los participantes de las reuniones hayan superpuesto las llamadas privadas.
    ![Captura de pantalla del mejor escenario con Teams y Skype empresarial](media/meetings-first-better-together-hold.png)
  - Conciliación de presencia: la actividad en Teams se refleja en la presencia del usuario, que es la presencia de Skype empresarial, ya que la conversación y las llamadas están en Skype empresarial. En concreto, cuando los usuarios de las reuniones se encuentran en una reunión de Teams, su presencia se actualizará para reflejarlo. Cuando presenten su pantalla, su presencia se actualizará para mostrar no molestar (según su configuración en Skype empresarial).
  - Reconciliación de control HID de dispositivo USB (también disponible en Mac): los controles de HID son aceptados por Teams durante las reuniones de Teams y Skype empresarial en todas las demás circunstancias.
  - A menos que se indique lo contrario, las capacidades más juntas requieren clientes de escritorio de Windows recientes en este momento.

## <a name="prerequisites-for-meetings-first"></a>Requisitos previos para las reuniones en primer lugar

Los únicos requisitos rígidos para las reuniones son los mismos que los de los equipos con Active Directory local y una implementación local de Skype empresarial:

- [Requisitos previos generales para Teams](upgrade-plan-journey-prerequisites.md), incluidos
- [Identidad y autenticación en Teams](identify-models-authentication.md) y
- [Configurar Azure Active Directory para Teams y Skype empresarial](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect).

No es necesaria una [topología híbrida de Skype empresarial](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-federation-with-skype-for-business-online) , pero se recomienda. Algunas funciones, como el servicio de migración de reuniones y la interoperabilidad, dependen de esa topología.

Las reuniones se admiten en primer lugar con cualquier versión de Skype empresarial Server (y se sabe que funciona con el servidor de Lync que ya no es compatible). Es compatible con cualquier cliente de Skype empresarial que sea compatible, pero es mejor que las capacidades de forma conjunta requieran un cliente reciente.

Una vez cumplidos estos requisitos (y no antes), los usuarios pueden tener [licencia para Microsoft 365 u Office 365 y Teams](https://docs.microsoft.com/office365/enterprise/assign-licenses-to-user-accounts).

Para las mejores reuniones en primer lugar, los usuarios deben estar habilitados para [Exchange Online](exchange-teams-interact.md), [SharePoint Online y OneDrive para la empresa](sharepoint-onedrive-interact.md), y la creación de grupos de Microsoft 365. Las reuniones se admiten en primer lugar para los usuarios cuyo buzón se encuentra en Exchange local, o que no tienen SharePoint Online o OneDrive para la empresa, o la creación de grupos de Microsoft 365. Sin embargo, su experiencia será menos completa. En concreto, en el caso de las organizaciones que usan Exchange Server local, puede haber (dependiendo de la versión de Exchange Server) algunas limitaciones para crear y ver reuniones en el cliente de equipos, así como con respecto a las capacidades de cumplimiento.

Como mínimo, los usuarios deben tener una [licencia para equipos](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide). Además, pueden tener una licencia de [audioconferencia](set-up-audio-conferencing-in-teams.md), si es necesario.

Le recomendamos que otorgue el modo [ **SfBOnly** o **SfBWithTeamsCollab** ](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) como valor predeterminado de tenant en el momento de otorgar la licencia a los usuarios. Esto garantiza que los usuarios no empiecen a usar Teams por sí mismos en el modo de **islas** predeterminadas antes de estar listo para iniciar reuniones en primer lugar.

Las reuniones se admiten primero en los clientes de escritorio (Windows y Mac), en los clientes del explorador y en los clientes móviles. También es compatible con [salas de Microsoft Teams](https://docs.microsoft.com/microsoftteams/room-systems/). Mejor juntos requiere el cliente de escritorio completo.

## <a name="prepare-for-teams-meetings-in-meetings-first"></a>Prepararse para las reuniones de Teams en las reuniones en primer lugar

Para que los usuarios tengan la mejor experiencia posible en las reuniones de Teams, debe hacer lo siguiente:

- Siga los pasos de [reuniones y conferencias de Microsoft Teams](deploy-meetings-microsoft-teams-landing-page.md), en especial.
- [Evaluar su entorno](3-envision-evaluate-my-environment.md).
- [Preparar la red de su organización para Microsoft Teams](prepare-network.md).
- Actualice sus salas de reunión con los [dispositivos y las soluciones](https://docs.microsoft.com/skypeforbusiness/certification/devices-meeting-rooms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)de la sala de reuniones con capacidad para empresas, o use [la interoperabilidad de vídeo en la nube para Microsoft Teams](cloud-video-interop.md) para permitir que los dispositivos y las salas de terceros existentes se unan a las reuniones de Teams.
- Equipar a tus usuarios con [dispositivos de audio y video USB certificados](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).
- Prepararse para [impulsar la detección y la adopción de reuniones de Teams](adopt-microsoft-teams-landing-page.md).
- [Planee la administración del servicio](4-envision-plan-my-service-management.md).
- Familiarizarse con los completos informes de análisis de llamadas para [solucionar problemas de baja calidad](use-call-analytics-to-troubleshoot-poor-call-quality.md)de las llamadas.

Es posible que considere la posibilidad de ejecutar un plan piloto preparado para producción de escala moderada en este momento.

## <a name="configure-users-for-meetings-first"></a>Configurar los usuarios para las reuniones en primer lugar

Una vez que haya otorgado la licencia a los usuarios y haya preparado la organización para las reuniones de Teams, es el momento de habilitar a los usuarios para que las vean en primer lugar. Lo hemos simplificado: una sola configuración lo hará todo.

Todas las características y las experiencias de usuario de las reuniones en primer lugar, incluida la configuración del cliente de Teams y el [cumplimiento automático](teams-client-experience-and-conformance-to-coexistence-modes.md) de la experiencia del usuario, el servicio de migración de reuniones y las capacidades más juntas, se configuran otorgando al usuario (o grupo de usuarios o valor predeterminado de inquilino) el modo [PowerShell](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)de [coexistencia de SfBWithTeamsCollabAndMeetings](setting-your-coexistence-and-upgrade-settings.md) en el centro de [Administración de Microsoft](manage-teams-in-modern-portal.md)

![Captura de pantalla de la configuración de administración para habilitar las reuniones en primer lugar](media/teams-meeting-admin-settings.png)

De manera opcional, si desea ocultar la aplicación equipos y canales desde el punto de acceso izquierdo del cliente de los equipos de los usuarios para centrar aún más su experiencia en las reuniones, puede usar la [Directiva de permisos](teams-app-permission-policies.md)de la aplicación.

## <a name="reporting-and-call-analytics"></a>Análisis de llamadas y informes

Los análisis de llamadas y reporting de las reuniones de Teams en las reuniones en primer lugar no cambian de lo que están en otros modos.

## <a name="related-links"></a>Vínculos relacionados

Después de revisar este artículo, es posible que desee consultar [elegir las instrucciones para la actualización, la](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md) [migración y la interoperabilidad](migration-interop-guidance-for-teams-with-skype.md), y la [coexistencia con Skype empresarial](coexistence-chat-calls-presence.md) para obtener más información.


