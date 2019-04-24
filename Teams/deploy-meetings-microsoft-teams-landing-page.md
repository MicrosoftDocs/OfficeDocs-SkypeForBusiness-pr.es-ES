---
title: Reuniones y conferencias en Microsoft Teams
ms.reviewer: ''
description: Use estos recursos de implementación para ayudarle a implementar las reuniones en Microsoft Teams.
ms.topic: article
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/28/2019
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: f4cd3af52b98bb80d7424b84be71416dbceb6250
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232811"
---
# <a name="meetings--conferencing-in-microsoft-teams"></a>Reuniones y conferencias en Microsoft Teams

Ha completado la [Introducción](get-started-with-teams-quick-start.md). Ha implementado Teams con [chat, equipos, canales y aplicaciones](deploy-chat-teams-channels-microsoft-teams-landing-page.md) en toda la organización. Ahora está listo para agregar la carga de trabajo de reuniones, incluyendo [audioconferencias](deploy-audio-conferencing-teams-landing-page.md), vídeo y uso compartido. Le mostramos cómo. 


## <a name="meetings--conferencing-deployment-decisions"></a>Decisiones sobre la implementación de reuniones y conferencias

Teams proporciona una experiencia excelente para su organización y la configuración predeterminada parece funcionar para la mayoría de organizaciones. Este artículo le ayudará a decidir si cambiar alguna opción de la configuración predeterminada, en función del perfil y los requisitos empresariales de su organización, después, le guiará con cada cambio. Hemos dividido las opciones en dos grupos, comenzando por el conjunto principal de [cambios que es más probable que realice](#core-deployment-decisions). El segundo grupo incluye las [opciones adicionales](#additional-deployment-decisions) que puede que quiera configurar, según las necesidades de su organización.

> [!Tip]
> Vea la sesión siguiente para obtener más información acerca de las reuniones: [Introducción a las reuniones en Microsoft Teams para profesionales de TI](https://aka.ms/teams-meetings-intro)


## <a name="meetings--conferencing-prerequisites"></a>Requisitos previos para las reuniones y conferencias 

Antes de continuar con la implementación de reuniones en toda la organización, tómese un tiempo para revisar y confirmar que el entorno está listo para proporcionar la mejor experiencia posible a los usuarios. Revise la información siguiente y realice los cambios necesarios en su entorno.

Para obtener la mejor experiencia en Teams, su organización debe haber implementado Exchange Online y SharePoint Online, y debe tener un dominio verificado para O365 (por ejemplo, *contoso.com*).

Para implementar las reuniones en toda la organización, asegúrese de que todas las ubicaciones tienen acceso a internet para conectarse a los servicios de Office 365. Como mínimo, debería asegurarse de que los siguientes puertos comunes están abiertos a internet en todas las ubicaciones de usuarios:

- Puertos TCP 80 y 443 salientes de los clientes que usarán Teams.
- Puertos UDP de 3478 a 3481 salientes de los clientes que usarán Teams.

Puede usar el [Complemento de pruebas de red](https://www.powershellgallery.com/packages/NetworkTestingCompanion/1.5.2) para confirmar que las ubicaciones de red están listas para el tráfico de voz y vídeo que dará soporte a la experiencia de reuniones.

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
|¿Está mi red lista para la implementación de reuniones de Teams? | Para comprobar que la red está preparada, vea:<ul><li>[Preparar la red de la organización para Microsoft Teams](https://docs.microsoft.com/es-ES/MicrosoftTeams/prepare-network)</li><li>[Direcciones URL e intervalos de direcciones IP de Office 365](https://docs.microsoft.com/es-ES/MicrosoftTeams/office-365-urls-ip-address-ranges)</li></ul> |
|||

## <a name="core-deployment-decisions"></a>Decisiones de implementación principales

Estas son las opciones que la mayoría de organizaciones cambia (si la configuración predeterminada de Teams no sirve para la organización).

### <a name="teams-administrators"></a>Administradores de Teams

Teams ofrece un conjunto de roles de administrador personalizados que pueden usarse para administrar Teams en su organización. Los roles proporcionan distintas funciones a los administradores. 

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
|¿A quién se asignará el rol de Administrador de comunicaciones de Teams?|Para obtener más información sobre los roles de administrador de Teams, vea [Usar los roles de administrador de Microsoft Teams para administrar Teams](using-admin-roles.md).|
|¿A quién se asignará el rol de Ingeniero de soporte en comunicaciones de Teams?|Para asignar roles de administrador, vea [asignar roles de administrador y de no administrador a los usuarios con Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).|
|¿A quién se asignará el rol de Especialista de soporte en comunicaciones de Teams?||
|||

### <a name="meetings-settings"></a>Configuración de reuniones 

La configuración de las reuniones se usa para controlar si los usuarios anónimos pueden unirse a reuniones de Teams, configurar las invitaciones a reuniones y, si quiere activar la Calidad de servicio (QoS), establecer los puertos para el tráfico en tiempo real. Esta configuración se usará para todas las reuniones de Teams que los usuarios programen en su organización. 

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
|¿Voy a personalizar la configuración inicial de reuniones? |Consulte el [tutorial de Reuniones en Teams](tutorial-meetings-in-teams.yml) para obtener más información sobre la configuración de reuniones.|
|¿Voy a implementar QoS?|Vea [Calidad de servicio en Microsoft Teams](qos-in-teams.md) para obtener información acerca de los conceptos, escenarios e implementación de QoS.|
|||

### <a name="meeting-policies"></a>Directivas de reunión

Las directivas de reunión se usan para controlar qué características están disponibles para los usuarios al unirse a reuniones de Teams. Puede usar la directiva predeterminada o crear una nueva o más directivas de reunión personalizadas para los miembros que creen reuniones en su organización. Para obtener más información, consulte el [tutorial de Reuniones en Microsoft Teams](tutorial-meetings-in-teams.yml).

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
|<ul><li>¿Voy a personalizar las directivas iniciales de reuniones?</li><li>¿Necesito varias directivas de reuniones?</li><li>¿Cómo determino qué directiva de reuniones se aplica a cada grupo de usuarios?</li></ul>|<br>Lea [Administrar directivas de reunión en Teams](meeting-policies-in-teams.md).|
|||

### <a name="audio-conferencing"></a>Audioconferencia

La audioconferencia ofrece a las organizaciones puntos de entrada adicionales a cualquier reunión (puntual o programada) permitiendo a los participantes de la reunión unirse a través de la red telefónica conmutada (RTC) llamando con un teléfono fijo tradicional, una central de conmutación (PBX) o un teléfono móvil. 

Cuando esté listo para implementar las audioconferencias, consulte la guía en profundidad sobre la [Implementación de audioconferencias](deploy-audio-conferencing-teams-landing-page.md).

### <a name="meeting-room-and-personal-devices"></a>Sala de reuniones y dispositivos personales.

Para obtener una experiencia óptima de reunión en Teams, considere el uso de dispositivos de Teams como cámaras, auriculares, teléfonos y sistemas de sala. Para obtener más información, consulte [dispositivos de Teams para comunicaciones inteligentes](https://products.office.com/microsoft-teams/across-devices).

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
|¿Voy a comprar dispositivos personales para mis usuarios? |Lea [Administrar los dispositivos en Teams](device-management.md). |
|¿Voy a comprar e implementar dispositivos de sistemas de sala para las salas de conferencias?|Lea [Soluciones y dispositivos de salas de reuniones](https://docs.microsoft.com/skypeforbusiness/certification/devices-meeting-rooms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).|
|||

### <a name="reporting"></a>Informes

Use los informes de actividad para ver cómo los usuarios de su organización usan Teams. Por ejemplo, si algunos aún no utilizan Teams, puede que no sepan cómo empezar o no entiendan cómo pueden usar Teams para ser más productivos y mejorar la colaboración. Su organización puede usar los informes de actividad para decidir dónde debe dar prioridad a los esfuerzos de aprendizaje y comunicación. 


| Pregúntese lo siguiente: | Acción |
|--------------|--------|
|¿Quién será responsable de los informes?|Lea [Usar informes de actividad de Teams](teams-activity-reports.md).  |
|¿Quién será responsable de supervisar el uso?|Lea [Supervisar el uso y los comentarios en Teams](get-started-with-teams-monitor-usage-and-feedback.md).|
|||

## <a name="additional-deployment-decisions"></a>Decisiones de implementación adicionales

Puede que le interese cambiar esta configuración en función de las necesidades y la configuración de su organización.

### <a name="bandwidth-planning"></a>Planeamiento del ancho de banda 

El planeamiento de ancho de banda permite a las organizaciones estimar el ancho de banda que necesitarán para dar soporte a las reuniones en sus redes de área extensa y vínculos de internet, de esta manera pueden confirmar que la red está preparada correctamente para admitir un servicio de reuniones escalado. 

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
| ¿Necesito hacer planeación de ancho de banda antes y durante la implementación de reuniones? |Vea [Preparación de la red](3-envision-evaluate-my-environment.md#network-readiness) para obtener más información y vínculos a las herramientas para simplificar el proceso de planeación.|
|||

### <a name="meeting-recording-and-archiving"></a>Grabación y archivado de reuniones

Los usuarios pueden grabar sus reuniones y llamadas de grupo para capturar el vídeo, el audio y la actividad de pantalla compartida. También hay una opción para que las grabaciones tengan una transcripción automática, para que los usuarios puedan reproducir grabaciones de reunión con subtítulos y buscar elementos de discusión importantes en la transcripción. La grabación se produce en la nube y se guarda en Microsoft Stream, para que los usuarios puedan compartirla de forma segura en su organización. Para buscar la grabación de una reunión, vaya a la conversación de la reunión.

Para obtener más información, consulte [Grabación de reuniones en la nube de Teams](cloud-recording.md).

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
| ¿Voy a activar el servicio de transcripción de reuniones?|Vea [Activar o desactivar la transcripción de grabaciones](cloud-recording.md#turn-on-or-turn-off-recording-transcription)|
|||


### <a name="live-events-policies"></a>Directivas de eventos en directo

Las directivas de eventos en directo de Teams se usan para administrar la configuración de eventos para los grupos de usuarios. Puede usar la directiva predeterminada o crear otras directivas que se pueden asignar a los usuarios que llevan a cabo eventos en directo en su organización. 

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
| ¿Va a usar mi organización los eventos en directo de Teams ?| Consulte los [artículos de eventos en directo](teams-live-events/what-are-teams-live-events.md) para obtener más información sobre cómo planear, instalar y configurar los eventos en directo de Teams.|
|||

### <a name="conference-room-systems-rollout"></a>Implementación de sistemas de sala de conferencias

Las organizaciones con muchas salas de conferencias pueden considerar un enfoque estructurado para realizar un inventario de las salas, identificar los dispositivos apropiados y, después, implementarlos. 



| Pregúntese lo siguiente: | Acción |
|--------------|--------|
| ¿Qué necesito hacer para implementar los sistemas de sala de conferencias?|Consulte los artículos [Planear salas de Microsoft Teams](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).|
|||

### <a name="cloud-video-interop"></a>Interoperabilidad de vídeos en la nube

La interoperabilidad de vídeos en la nube permite que los dispositivos de salas de reuniones de terceros puedan unirse a reuniones de Teams. 

La teleconferencia de vídeo con colaboración de contenido le ayudará a sacar el máximo partido de las reuniones. Sin embargo, es caro actualizar los sistemas y dispositivos de sala de reuniones. La interoperabilidad de vídeos en la nube para Teams funciona con sistemas de terceros y ofrece una experiencia de reunión nativa para todos los participantes, tanto en salas de reuniones como en clientes de Teams. 

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
| ¿Voy a usar una solución de interoperabilidad de vídeo en la nube como parte de la implementación de sistemas de sala? | Lea [Interoperabilidad de vídeos en la nube para Teams](cloud-video-interop.md).|
|||


### <a name="personal-device-rollout"></a>Implementación de dispositivos personales

Al planear una mayor implementación de dispositivos personales para dar soporte a las implementaciones de voz o de reuniones, considere el uso de un proceso reiterativo de implementación sitio por sitio que ofrezca resultados de calidad.

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
|¿Voy a usar el enfoque de sitio por sitio para implementar reuniones? |  La [Guía de activación de sitios para Teams](3-onboard-deploy-my-service.md#site-enablement-playbook-for-microsoft-teams-voice-workloads) ofrece una buena base que puede usar para sus propias implementaciones. La guía se centra en la función de voz, pero los principios generales de reparto de dispositivos, preparación de cuenta, adopción y aprendizaje se aplican en una implementación de reuniones. |
|||

### <a name="troubleshoot-meeting-and-call-quality"></a>Solucionar problemas de calidad de las reuniones y llamadas 

Teams ofrece dos formas para supervisar y solucionar problemas de calidad de llamadas: [Análisis de llamadas y Panel de calidad de llamadas](difference-between-call-analytics-and-call-quality-dashboard.md) Análisis de llamadas muestra información detallada sobre dispositivos, redes y conectividad relacionada con llamadas concretas y reuniones de cada usuario. Análisis de llamadas está diseñado para ayudar a los administradores y agentes de soporte técnico a solucionar problemas de calidad de llamada con llamadas específicas, mientras que el Panel de calidad de llamadas está diseñado para ayudar a los administradores y los ingenieros de red a optimizar una red. El panel de calidad de llamada cambia el enfoque de usuarios específicos y, en su lugar, analiza la información global de toda la organización de Teams. 

|Pregúntese lo siguiente:|Acción |
|------------|-------|
| ¿Quién será responsable de la supervisión y solución de problemas de calidad de llamadas? | Lea [Usar el Análisis de llamadas para solucionar problemas de mala calidad en las llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md) para obtener información sobre los niveles de permisos necesarios para solucionar problemas de calidad de llamadas.|
|||

### <a name="operate-your-meetings-service"></a>Operar el servicio de reuniones

Es importante que comprenda el estado general del servicio de Teams para que pueda avisar proactivamente a otros usuarios de su organización sobre cualquier evento que afecte al servicio. Los artículos [Operar mi servicio](1-drive-value-operate-my-service.md) proporcionan instrucciones detalladas para las operaciones de servicio.

|Pregúntese lo siguiente:|Acción |
|------------|-------|
|¿Quién será responsable de administrar el servicio de reuniones en mi organización? | Asegúrese de que esta persona tiene los permisos de administrador de Teams que necesita para administrar el servicio de reuniones. Para obtener más información sobre los roles de administrador de Teams, vea [Usar los roles de administrador de Microsoft Teams para administrar Teams](using-admin-roles.md).|
|||


## <a name="next-steps"></a>Pasos siguientes
- [Impulsar la adopción](adopt-microsoft-teams-landing-page.md) de reuniones y conferencias en toda la organización.
- [Agregar audioconferencia](deploy-audio-conferencing-teams-landing-page.md)
- [Implementar voz en la nube](cloud-voice-landing-page.md)
- Incluya aplicaciones destacadas, como Planner, en la implementación inicial de Teams. Agregue otras [aplicaciones, bots y conectores](deploy-apps-microsoft-teams-landing-page.md) a medida que impulsa la adopción de Teams.
