---
title: Configurar Microsoft Teams en su organización
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Configure Teams en su empresa para permitir que los usuarios puedan colaborar mediante el chat y el uso compartido de archivos, configurar y asistir a reuniones de cualquier tamaño, y hablar por vídeo y voz.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: d8144b830bec7f51bd97c59211d629aae7ffb3c9
ms.sourcegitcommit: 4d76837f9481ca2cda437afdf11de5eaf7a57d99
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2021
ms.locfileid: "50726391"
---
# <a name="set-up-microsoft-teams-in-your-enterprise"></a>Configurar Microsoft Teams en su organización

La información de este artículo le guiará en la implementación de Teams en su organización.

> [!NOTE]
> Si aún no lo ha hecho, le recomendamos encarecidamente que empiece la implementación de Teams con un programa piloto. El piloto le permitirá a usted y a los usuarios pioneros familiarizarse con Teams y con sus características antes de su planificación y lanzamiento. Para obtener más información sobre cómo iniciar el piloto, consulte la [Introducción a Microsoft Teams](get-started-with-teams-quick-start.md).

Antes de que implemente Teams ampliamente, asegúrese de que su organización está lista revisando los elementos de [Asegúrese de que está listo](get-started-with-teams-quick-start.md#make-sure-youre-ready).

## <a name="plan-your-deployment"></a>Planear la implementación

Antes de empezar a implementar Teams, asegúrese de que ha completado el proceso de planeación. El proceso de planeación debe incluir:

- Descripción de la arquitectura de Teams
- Revisión y descripción de las cargas de trabajo de Teams y cómo funcionan con Microsoft 365
- Confianza en que su red y conexión a Internet tienen el hardware y la capacidad necesarios para admitir requisitos críticos, como las comunicaciones a tiempo real.
- Información acerca de los requisitos de cumplimiento normativo y regulatorio de la información almacenada en Teams y en otros servicios de Microsoft 365
- Creación de un plan de adopción para ayudar a los usuarios a comprender las ventajas de usar Teams

Le recomendamos encarecidamente que use el [Asesor de Teams](https://admin.teams.microsoft.com/teams-deployment) para ayudarle en la implementación. Para obtener detalles sobre el funcionamiento del asesor de Teams, consulte [Usar el asesor de Teams para ayudarle a implementar Microsoft Teams](use-advisor-teams-roll-out.md).

> [!TIP]
> Consulte cómo puede usar el asesor de Teams para ayudarle a planear la implementación de Teams completando el módulo [Implementación con el asesor de Teams](https://docs.microsoft.com/learn/modules/m365-teams-rollout-using-advisor/) en Microsoft Learn.

Para obtener información sobre la planeación de Teams, consulte [Información general de implementación empresarial de Teams](deploy-enterprise-overview.md).

## <a name="workloads"></a>Cargas de trabajo

Hay muchas formas de personalizar Teams. En las secciones siguientes se muestra cómo configurar cada carga de trabajo de Teams: **chats, equipos y canales**; **conferencias y reuniones** y **Sistema telefónico**. Podrá configurar cada carga de trabajo en el orden que desee. Aunque recomendamos configurar primero la carga de trabajo de los chats, equipos y canales, si lo desea puede empezar con reuniones y conferencias o incluso con Sistema telefónico.

#### <a name="chat-teams-and-channels"></a>[Entender los equipos y canales](#tab/ChatTeamsChannels)

El chat, los equipos y los canales son el eje central de Teams. El **chat** permite que uno o más usuarios se comuniquen entre sí, compartan archivos y se reúnan en privado. Los **equipos**, que pueden ser visibles para todos los usuarios de la organización o solo para los miembros de ese equipo, permiten a los usuarios adecuados colaborar en cualquier tipo de tarea u ocasión, desde un proyecto de larga duración hasta la planificación de una fiesta de cumpleaños. Los **canales** dentro de los equipos pueden segmentar temas, proyectos, departamentos o lo que necesite su equipo. Para obtener más información sobre el chat, los equipos y los canales, consulte la [Introducción a los equipos y canales](teams-channels-overview.md).

> [!TIP]
> Complete el módulo de administración de [Microsoft Teams](https://docs.microsoft.com/learn/modules/m365-teams-collab-manage-teams/) en Microsoft Learn para descubrir cómo administrar los roles de equipo y gestionar el acceso y las directivas de mensajería.

### <a name="administration-and-team-ownership"></a>Administración y propiedad del equipo

| Decision | Descripción |
|--|--|
| ¿Quiénes deben ser administradores de Teams? | Los roles de administrador se pueden usar para conceder permisos específicos a las personas que quiera que administren Teams. Es posible que las empresas pequeñas no necesiten estos roles adicionales, ya que la misma persona puede encargarse de manejar todos los aspectos de Teams. Siempre podrá agregar o quitar administradores en otro momento.<p>[Usar roles de administrador de Microsoft Teams para administrar Teams](using-admin-roles.md) |
| ¿Quiénes deben ser propietarios y miembros del Equipo? | Los propietarios del equipo controlan quién puede acceder a un equipo y sus canales. Pueden decidir si un equipo o canal es público (para la organización) o privado y configurar directivas; por ejemplo, si el canal debe moderarse o no. Los miembros pueden acceder al equipo y a sus canales (a menos que el canal se establezca como privado y los miembros no pertenezcan a ese canal), así como también ser designados como moderadores.<p>[Asignar miembros y propietarios de equipo en Microsoft Teams](assign-roles-permissions.md) |

### <a name="default-settings-and-lifecycle-policies"></a>Configuración predeterminada y directivas de ciclo de vida

| Decision | Descripción |
|--|--|
| ¿Qué directivas de mensajería deben aplicarse? | Los usuarios en Teams pueden acceder a las directivas de mensajería que controlan las características de chat y de mensajería del canal (como quién puede usar el chat, quién puede editar y eliminar mensajes enviados, etc.). Teams tiene una directiva global que se aplica a todos los usuarios. Todas las características de la directiva global están **activadas** de forma predeterminada.<p>Si quiere que la misma directiva se aplique a todos los usuarios, solo tiene que realizar cambios en esta directiva global (por ejemplo, desactivar la compatibilidad de memes en las conversaciones).<p>Si quiere usar diferentes directivas para distintos grupos de personas (por ejemplo, una directiva para los trabajadores de oficinas y otra para los trabajadores de fábrica), puede crear y asignar directivas. Al asignar una directiva a un usuario, la directiva global ya no se aplica a este.<p>[Administrar directivas de mensajería de Teams](messaging-policies-in-teams.md) |
| ¿Qué configuración de Equipo debe aplicarse? | La configuración de Teams le permite configurar los equipos con características como la integración de correo electrónico, opciones de almacenamiento de nube, pestaña de la organización, configuración de dispositivos de salas de reuniones y el ámbito de búsqueda. Cuando realice cambios en esta configuración, se aplicarán a todos los equipos de su organización. <p>[Configuración de Microsoft Teams](enable-features-office-365.md#teams-settings)  |

### <a name="external-and-guest-access"></a>Acceso externo y de invitado

| Decision | Descripción |
|--|--|
| ¿Debe habilitarse el acceso externo? | El acceso externo permite que cualquier persona de otra organización hable con las personas de la suya. Es una opción útil si tiene una relación estrecha con otra organización, como un proveedor, y quiere facilitar a las personas de ambas organizaciones chatear, mantener reuniones, etc. <p>El acceso externo es diferente del acceso de invitados. El acceso externo proporciona acceso a todas las personas de otra organización para que interactúen con las personas de la suya. El acceso de invitado permite a usuarios específicos interactuar con personas de su organización.<p>El acceso externo está **Desactivado** de forma predeterminada.<p>[Administrar el acceso externo en Microsoft Teams](manage-external-access.md)  |
| ¿Debe habilitar el acceso de invitado? |El acceso de invitado permite que las personas de su organización inviten a personas de fuera de la organización a acceder a los equipos y canales. El acceso de invitado suele usarse para colaborar con personas fuera de la organización que no tengan una relación formal con esta. Por ejemplo, puede invitar temporalmente a un planificador de proyectos para que trabaje en un proyecto.<p>El acceso de invitados es distinto al acceso externo. El acceso de invitado permite a usuarios específicos interactuar con personas de su organización. El acceso externo proporciona acceso a todas las personas de otra organización para que interactúen con las personas de la suya. <p>El acceso de invitado está **desactivado** de forma predeterminada. <p>[Activar o desactivar el acceso de invitado a Microsoft Teams](set-up-guests.md)  |

#### <a name="meetings-and-audio-conferencing"></a>[Reuniones y audioconferencias](#tab/MeetingsAudioConferencing)

Las reuniones y las conferencias permiten que las personas de la organización se reúnan entre sí y con usuarios ajenos a la organización. Cualquier usuario con un cliente de Teams o de Skype Empresarial puede unirse a las **reuniones** a las que haya sido invitado. Usando el micrófono, la cámara y la pantalla de su dispositivo, los participantes pueden unirse a la conversación sin necesidad de tener un teléfono. También pueden chatear, realizar llamadas de voz y compartir vídeo y aplicaciones con otros participantes a través de un equipo o de un dispositivo móvil.

El asistente de **Audioconferencia** permite a los participantes unirse a las reuniones a través de un teléfono normal al llamar a un número de teléfono de conferencia y especificar el id. de la reunión. Las audioconferencias son útiles cuando uno de los participantes no tiene una buena conexión a Internet, la reunión es solo de voz o hay alguna otra circunstancia que le impida al participante unirse a través del cliente de Teams.

> [!TIP]
> Si desea familiarizarse con las reuniones y los eventos, complete el módulo [Administrar reuniones, conferencias y eventos de Microsoft Teams](https://docs.microsoft.com/learn/modules/m365-teams-collab-manage-meetings) en Microsoft Learn.

### <a name="meetings"></a>Reuniones

| Decision | Descripción |
|--|--|
| Qué configuraciones de reunión a nivel de la organización deben aplicarse| Las directivas de reunión controlan las características de la reunión que están disponibles para los organizadores y los participantes de las reuniones. Usted decide si los participantes anónimos pueden unirse a reuniones y tiene la opción de personalizar las invitaciones a reuniones, controlar la forma en que se manejan los medios audiovisuales en tiempo real y mucho más. Cuando realice cambios en esta configuración, se aplicarán a todas las reuniones de su organización. <p>[Administrar la configuración de reuniones en Microsoft Teams](meeting-settings-in-teams.md)|
| ¿Qué directivas de reuniones deben aplicarse? | Las Directivas de reunión se usan para controlar las características disponibles para sus participantes en reuniones programadas por usuarios de la organización. Puede controlar si los usuarios tienen la opción de programar reuniones privadas, así como habilitar la opción Reunirse ahora, permitir grabar reuniones y mucho más. Teams tiene una directiva global que se aplica a todos los usuarios.<p> Si quiere que la misma directiva se aplique a todos los usuarios, solo tiene que realizar cambios en esta directiva global (por ejemplo, desactivar la grabación de conversaciones). <p>Si quiere usar diferentes directivas para distintos grupos de personas (por ejemplo, una directiva para los trabajadores de oficinas y otra para los ejecutivos), puede crear y asignar directivas. Al asignar una directiva a un usuario, la directiva global ya no se aplica a este.<p> [Administración de directivas de reunión en Teams](meeting-policies-in-teams.md)|
| ¿Desea permitir la grabación y el archivado de la reunión?| Los organizadores de la reunión pueden grabar y archivar reuniones en la nube. Puede activar y desactivar la grabación y el archivado de reuniones con las directivas de reunión.<p> [Grabación de reuniones en la nube de Teams](cloud-recording.md) |

### <a name="audio-conferencing"></a>Audioconferencia

| Decision | Descripción |
|--|--|
| ¿Desea configurar la interoperabilidad de vídeo con soluciones de terceros?| La interoperabilidad con vídeo en la nube permite a dispositivos de telepresencia de terceros y dispositivos de vídeo personales unirse a reuniones de Teams. Si ha invertido recursos en dispositivos de videoconferencia y de vídeo personales, puede integrarlos en Teams con la interoperabilidad de vídeo.<p> [Interoperabilidad de vídeos en la nube para Microsoft Teams](cloud-video-interop.md)|
| ¿Qué configuraciones de audioconferencia a nivel de la organización deben aplicarse?| La configuración de las audioconferencias le permite controlar la forma en que los participantes de la reunión llaman a las reuniones con un teléfono. Puede establecer la longitud de los PIN necesaria para unirse a reuniones, restablecer los id. de conferencia, habilitar o deshabilitar el envío de información de audioconferencia a participantes y así sucesivamente. Los cambios en la configuración de las audioconferencias son aplicables a todos los usuarios de su organización.<p>[Administrar la configuración de Audioconferencia para su organización en Microsoft Teams](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md) |
| ¿Necesitan los organizadores de la reunión llamar a cualquier destino?| Los créditos de comunicación se usan al llamar desde una reunión de audioconferencia a números de teléfono externos a su organización. Debe comprar suficientes créditos de comunicación para asegurarse de que no se quedará sin los necesarios durante las llamadas de audioconferencia.<p>Algunas suscripciones de audioconferencia pueden incluir llamadas salientes. Compruebe la información de su suscripción para obtener más información.<p> [Configurar Créditos de comunicaciones para su organización](set-up-communications-credits-for-your-organization.md)|
| ¿Qué restricciones de llamada saliente deben aplicarse?| Puede usar los controles de llamadas salientes para restringir el tipo de audioconferencias y llamadas que pueden realizar los usuarios de su organización. Por ejemplo, puede controlar si en las reuniones se tiene la posibilidad de llamar a números de teléfono internacionales o realizar llamadas salientes, si se debe llamar solo a determinados países o regiones, etc.<p>[Políticas de restricción de llamadas salientes para Audioconferencia y las llamadas RTC de usuario](outbound-calling-restriction-policies.md) |
| ¿Quiere cambiar cómo Teams interpreta los números de teléfono marcados? | Puede controlar cómo se interpretan los números de teléfono con los planes de marcado. Por ejemplo, puede establecer el número que quiere marcar para que llegue a una línea de teléfono externa, controlar la forma en que se administran las extensiones de teléfono, establecer un prefijo para que una extensión de marcado se traduzca en un número de teléfono completo, y así sucesivamente.<p> [Crear y administrar planes de marcado](create-and-manage-dial-plans.md) |
| ¿Desea habilitar los eventos en directo? | Los eventos en directo le permiten difundir vídeo y contenido de reuniones a un gran público. Si habilita los eventos en directo, puede establecer directivas para controlar cómo se usan. Por ejemplo, puede establecer qué URL deben usar los participantes para obtener soporte técnico, configurar un proveedor de distribución de vídeo de terceros (si lo tiene), etc. Teams tiene una directiva global que se aplica a todos los usuarios.<p>Si quiere que la misma directiva se aplique a todos los usuarios, solo tiene que realizar cambios en esta directiva global. <p>Si quiere usar diferentes directivas para distintos grupos de personas (por ejemplo, una directiva para los trabajadores de oficinas y otra para los ejecutivos), puede crear y asignar directivas. Al asignar una directiva a un usuario, la directiva global ya no se aplica a este.<p> [Definir eventos en directo en Microsoft Teams](teams-live-events/set-up-for-teams-live-events.md) |

#### <a name="phone-system-and-pstn-connectivity"></a>[Sistema telefónico y conectividad RTC](#tab/PhoneSystem)

Sistema telefónico le permite reemplazar su sistema telefónico local existente por un conjunto de características de Microsoft 365 estrechamente integrado en su experiencia en la nube.

| Decision | Descripción |
|--|--|
| ¿Quiere reemplazar el sistema telefónico local? | Configure sistema telefónico, los operadores automáticos, los planes de llamadas, las colas de llamadas, entre otros. <p> [Configurar Sistema telefónico en su organización](setting-up-your-phone-system.md)|
| ¿Quiere establecer las directivas de Correo de voz en la nube?| Puede controlar qué características de Correo de voz en la nube están disponibles para sus usuarios y cómo funcionan. Por ejemplo, puede habilitar o deshabilitar la transcripción del correo de voz para toda la organización, habilitar o deshabilitar la máscara de voz para usuarios específicos, etc.<p> [Configurar el Correo de voz en la nube](set-up-phone-system-voicemail.md) |
| ¿Quiere habilitar las llamadas de emergencia dinámicas?| Las llamadas de emergencia dinámicas le permiten configurar un mapa de ubicación en función de la configuración de la red y de otros metadatos para determinar dónde se debe enviar al personal de emergencia en caso de que un usuario haga una llamada de emergencia. Puede establecer la configuración de red, asignar direcciones de emergencia a ubicaciones, y mucho más.<p>[Planear y configurar las llamadas de emergencia dinámicas](configure-dynamic-emergency-calling.md) |
| ¿Quiere personalizar el comportamiento del identificador de llamada? | De forma predeterminada, el número de teléfono que se muestra cuando un usuario de Teams realiza una llamada es el número de teléfono del usuario. Puede cambiarlo para que sea el número principal de la compañía, bloquearlo, hacer que sea anónimo o usar otro número de servicio. Teams tiene una directiva global que se aplica a todos los usuarios.<p>Si quiere que la misma directiva se aplique a todos los usuarios, solo tiene que realizar cambios en esta directiva global. <p>Si quiere usar diferentes directivas para distintos grupos de personas (por ejemplo, una directiva para los trabajadores de oficinas y otra para los ejecutivos), puede crear y asignar directivas. Al asignar una directiva a un usuario, la directiva global ya no se aplica a este.<p> [Administrar directivas del id. de llamada en Microsoft Teams](caller-id-policies.md) |

---

## <a name="security"></a>Seguridad

Teams está diseñado y desarrollado conforme al [Ciclo de vida de desarrollo de seguridad (SDL) de la Informática de Confianza de Microsoft](https://www.microsoft.com/sdl/default.aspx). Para cumplir con el ciclo de vida de desarrollo de seguridad de Microsoft, Teams incorpora las tecnologías de seguridad estándar del sector como parte fundamental de su arquitectura. Entre ellas se incluyen:

- Diseñar modelos de amenazas con los que se prueban las características
- Incorporar mejoras relacionadas con la seguridad en el proceso de codificación y procedimientos
- Crear herramientas de tiempo integradas que detectan excesos en el búfer y otras amenazas potenciales de seguridad antes de que se pueda comprobar el código en el producto

Aunque Teams sigue la metodología "Diseñado para ser fiable", es imposible protegerse contra todas las amenazas de seguridad desconocidas. Por este motivo, se debe comprender cómo funciona Teams y cómo interactúa con otros sistemas. También es importante comprender cómo funcionan las amenazas comunes, como la suplantación de direcciones IP, los ataques por denegación de servicio, los ataques por intermediario etc., para que pueda diseñar la red y configuración de Teams contra ellos.

Para entender cómo incorpora Teams los aspectos básicos de seguridad en su diseño y obtener más información sobre las amenazas comunes, consulte [Seguridad y Microsoft Teams](teams-security-guide.md).

## <a name="compliance"></a>Cumplimiento

Teams y Microsoft 365 proporcionan muchas herramientas que pueden ayudarle a cumplir con los requisitos reglamentarios vigentes en la jurisdicción de su empresa o usuarios. Consulte los artículos siguientes para obtener información sobre cómo configurar cada característica de cumplimiento en Teams:

| Característica | Descripción|
|-|-|
| [Barreras de información](information-barriers-in-teams.md)| Impiden que usuarios o grupos se comuniquen entre sí o se encuentren en el selector de usuarios.|
| [Directivas de retención](retention-policies.md)| Le permite controlar cuánto tiempo deben conservarse los datos en Teams o si deben quitarse después de un tiempo determinado.|
| [Cumplimiento de las comunicaciones](communication-compliance.md)| Ayuda a reducir los riesgos de comunicación mediante la identificación y la toma de medidas contra lenguaje ofensivo, obsceno o intimidatorio; imágenes sexuales o sangrientas, y el uso compartido de información confidencial. |
| [Grabación basada en directiva para llamadas y reuniones](teams-recording-policy.md)| Le permite controlar si las llamadas y reuniones deben grabarse y almacenarse automáticamente para su posterior procesamiento, retención o análisis, así cómo decidir cuándo esto puede hacerse.|
| [Etiquetas de confidencialidad](sensitivity-labels.md)| Le ayuda a proteger y regular el acceso a la información confidencial mediante la creación de etiquetas que exijan opciones de privacidad seleccionadas.|
| [Prevención de pérdida de datos](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams?toc=%2Fmicrosoftteams%2Ftoc.json&bc=%2Fmicrosoftteams%2Fbreadcrumb%2Ftoc.json&view=o365-worldwide)| Le permite crear reglas que determinen cómo debe tratarse cierta información, como números de la seguridad social, números de tarjeta de crédito... Puede impedir, entre otras cosas, que determinada información se envíe o salga de la organización.|
| [eDiscovery](eDiscovery-investigation.md)| Le ayuda a buscar y recuperar contenido de su organización cuando esta recibe solicitudes de descubrimiento en procesos legales. |
| [Suspensión legal](legal-hold.md)| Le ayuda a conservar información en la organización, incluso si la elimina un usuario, cuando es necesario durante un procedimiento legal, de modo que pueda ser detectada durante las investigaciones de exhibición de documentos electrónicos. |
| [Búsqueda de contenido](content-search.md)| Permite consultar información sobre Teams. Abarca Exchange, SharePoint Online y OneDrive para la Empresa.|
| [Auditoría](audit-log-events.md)| Le permite ver información sobre una acción especificada, como quién realizó la acción, cuándo se realizó la acción, la dirección IP que se usó, etc. Entre las acciones se incluyen la creación o eliminación de equipos, la creación de canales, los cambios en la configuración de Teams, entre otros.|
| [Clave de cliente](https://docs.microsoft.com/microsoft-365/compliance/customer-key-tenant-level?toc=%2Fmicrosoftteams%2Ftoc.json&bc=%2Fmicrosoftteams%2Fbreadcrumb%2Ftoc.json&view=o365-worldwide)| Le permite crear una directiva de cifrado de datos con las claves de cifrado que proporcione.|

## <a name="clients"></a>Clientes

Cuando esté listo para que sus usuarios comiencen a usar Teams, podrán instalar el cliente de Teams en su equipo Windows, Mac o Apple, o en su dispositivo Android o iOS. Los usuarios pueden descargar el cliente de Teams directamente desde <https://teams.microsoft.com/downloads>.

Asegúrese de que todos los usuarios que vayan a emplear Teams tengan una licencia de Teams. Para obtener más información acerca de cómo asignar una licencia de Teams, consulte [Administrar el acceso del usuario a Teams](user-access.md#using-the-microsoft-365-admin-center).

> [!TIP]
> Para obtener recomendaciones sobre cómo planear la implementación del cliente de Teams, complete el módulo [Implementar clientes de Microsoft Teams](https://docs.microsoft.com/learn/modules/m365-teams-collab-deploy-clients/) en Microsoft Learn.

Si su organización usa Microsoft Endpoint Configuration Manager, alguna directiva de grupo o un mecanismo de distribución de terceros para implementar el software en los equipos de los usuarios, consulte [Instalar Microsoft Teams a través de Microsoft Endpoint Configuration Manager](msi-deployment.md).

Si desea obtener información detallada acerca de la implementación de clientes de Teams, consulte [Obtener clientes para Microsoft Teams](get-clients.md).

## <a name="training"></a>Aprendizaje

Para obtener información sobre cómo entrenar a los usuarios y administradores para que usen Teams, consulte [Aprendizaje de Microsoft Teams](training-microsoft-teams-landing-page.md).
