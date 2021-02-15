---
title: Operaciones de Microsoft Teams| Administración de servicios | Calidad
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Tareas y actividades necesarias para la administración de servicios de Teams, incluida la supervisión del estado del servicio y la evaluación y la garantía de la calidad y el uso de la red
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3180eabe2886faaade690f7a5bc0f3f97226589
ms.sourcegitcommit: 1889ca28b9cb952b13c84efa3588957a327f9702
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841501"
---
# <a name="operate-your-service"></a>Ejecutar los servicios

![Diagrama de viaje de actualización, que enfatiza la fase de excelencia operativa](media/upgrade-banner-op-excellence.png "Fases del viaje de actualización, con énfasis en la fase de excelencia operativa")

Este artículo forma parte de la fase de excelencia operativa del viaje de actualización, que comienza tan pronto como haya completado la actualización de Skype Empresarial a Teams.

En este artículo se ofrece información general sobre los requisitos para operar correctamente Teams para su organización después de actualizar. Al operar correctamente los servicios de Teams, puede estar seguro de que está proporcionando una experiencia de alta calidad y confiable para su organización.

## <a name="introduction-to-the-operations-guide"></a>Introducción a la guía de operaciones

La Guía de operaciones le proporciona una descripción general de todas las tareas y actividades necesarias como parte de la función de administración de servicios de Microsoft Teams.

La administración de servicios es un tema muy amplio que cubre las operaciones del día a día del servicio de Microsoft Teams una vez que se ha implementado y habilitado para los usuarios. El servicio de Teams incluye Microsoft 365 u Office 365 y los componentes de infraestructura que se implementan de forma local (por ejemplo, redes).

Seguramente, el concepto de "administración de servicios" no es nuevo para la mayoría de organizaciones. Es posible que ya haya implementado procesos y tareas asociados a servicios existentes. Dicho esto, probablemente puede aumentar sus procesos actuales al planear la administración de servicios hoy para admitir Teams en el futuro.

La administración de servicios incluye todas las actividades y procesos relacionados con la administración de Teams de un extremo a otro. Como se indicó anteriormente, algunos componentes de la administración de servicios (la infraestructura que incluye el servicio de Microsoft 365 u Office 365) son responsabilidad de Microsoft, mientras que usted, como cliente, es responsable ante los usuarios para administrar los distintos aspectos de Teams, la red y los puntos de conexión que proporciona.

Las tareas y actividades de esta guía se agrupan en ocho categorías, como se muestra en el siguiente diagrama. Cada una de estas categorías se expandirá en las secciones siguientes.

![Diagrama que muestra una lista de categorías de tareas y actividades](media/operate-my-service-image1.png "Diagrama que muestra una lista de categorías de tareas y actividades que componen la administración de servicios para Teams. El diagrama también muestra que la administración de servicios es en gran medida una tarea del cliente.")

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Puntos de decisión</td><td><ul><li>Decida cómo se implementarán las operaciones para Teams.</li></ul></td></tr>

<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Pasos siguientes</td><td><ul><li>Revise la Guía de operaciones en su totalidad.</li><li>Implemente una estrategia de operaciones que se alinee con los objetivos de su organización para ofrecer la calidad y la confiabilidad de las cargas de trabajo de Teams.</li><li>Revise la Guía de revisión de la calidad de la experiencia.</li><li> Implemente una estrategia de operaciones para realizar revisiones periódicas de la calidad de la experiencia con el objeto de asegurarse de que su implementación de Teams funciona en sus capacidades máximas.</li></ul></td></tr>

</table>

### <a name="operational-role-mapping"></a>Asignación de roles operativos

La planificación que empezó a realizar durante la fase de visión es fundamental, ya que las actividades de operaciones comienzan cuando se habilitan los primeros usuarios piloto. En esta guía se enumeran las actividades y tareas que se deben realizar de forma diaria, semanal, mensual o según sea necesario para mantener una implementación de Teams de alta calidad. Esta guía proporciona conocimientos y orientación sobre cómo realizar estas actividades y tareas críticas.

Uno de los componentes cruciales de una implementación correcta es asegurarse de que la planificación que realice en la fase inicial de Visión incluye determinar quién será el responsable de realizar actividades específicas. Después de averiguar qué tareas y actividades se aplican a su implementación, es necesario comprenderlas y seguirlas por los grupos o personas que les asigne.

Cada equipo identificado debe revisar y ponerse de acuerdo sobre las tareas y responsabilidades identificadas y comenzar la preparación. Esto puede incluir formación y preparación, proporcionar actualizaciones para el plan de personal o garantizar que los proveedores externos estén listos para entregar.

Las actividades y los roles definidos en esta guía deben ser válidos en la mayoría de los escenarios, pero cada implementación de Teams es única; por lo tanto, puede usar esta guía como punto de partida para personalizar las actividades y los roles predeterminados según sus necesidades.

Asegúrese de que cada equipo responsable tenga un buen conocimiento de las actividades necesarias para ejecutar el servicio. Es fundamental que cada equipo acepte y señale su responsabilidad en la organización antes de que comience el primer piloto.

Una vez que se ha alcanzado un acuerdo, los equipos correspondientes deberían comenzar a poner en funcionamiento sus roles.

<table>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Pasos siguientes</td>
<td><ul><li>Use este documento para facilitar el ejercicio de asignación de funciones operativas.</li><li>Reúnase con los respectivos equipos de soporte técnico para asignar nombres a cada elemento en la lista de actividades necesarias.</li><li>Obtenga la aceptación o la aprobación de los roles asignados.</li><li>Asegúrese de que los equipos correspondientes tengan la formación, la preparación y los recursos adecuados para completar las actividades que se les requieran.</li></ul></td></table>

### <a name="teams-service-dependencies"></a>Dependencias del servicio de Teams

Microsoft Teams reúne tecnologías en Microsoft 365 y Office 365 para proporcionar un centro para el trabajo en equipo. Algunos ejemplos son:

- Azure Active Directory (Azure AD) proporciona servicios de autorización y autenticación para Teams.

- Exchange Online proporciona características avanzadas como retención legal y detección electrónica.

- SharePoint Online ofrece la posibilidad de compartir archivos en canales, y OneDrive para la Empresa ofrece un mecanismo para compartir archivos en un chat privado.

Las organizaciones también pueden aprovechar las inversiones existentes en infraestructura local. Por ejemplo, las cuentas locales de Active Directory existentes pueden usarse para la autenticación aprovechando Azure AD Connect. Algunas versiones de Exchange Server pueden usarse en lugar de Exchange Online.

Estas tecnologías se unen para proporcionar un conjunto de comunicaciones enriquecido, colaborativo e inteligente para los usuarios. Esta estrecha integración es un beneficio clave de Teams, pero también genera requisitos para la administración de servicios en estas tecnologías.

Esta guía trata sobre las áreas clave en las que centrarse para administrar el servicio de Teams. Es muy probable que tenga planes de administración de servicios para las tecnologías compatibles de las que depende Teams. Si no es así, tendrá que establecer planes de administración de servicios adecuados para esos componentes de tecnología (tanto locales como en línea). Esto ayudará a garantizar que los usuarios disfruten de una experiencia de alta calidad y de confianza con Teams.

#### <a name="references"></a>Referencias

[Información general sobre Microsoft Teams](teams-overview.md)

[Interacción entre Exchange y Microsoft Teams](exchange-teams-interact.md)

[Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams](sharepoint-onedrive-interact.md)

[Coexistencia e interoperabilidad de Microsoft Teams y Skype Empresarial](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>Actividades de la Guía de operaciones

En las siguientes secciones se proporciona información general de las actividades necesarias para operar correctamente el servicio Microsoft Teams. Incluyen referencia a herramientas, información contextual y contenido adicional para ayudarle a comprender la actividad y ayudar en las iniciativas de preparación.

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>Supervisar el estado del servicio

Es importante que comprenda el estado general del servicio Microsoft Teams para poder alertar de forma proactiva a los demás usuarios de su organización de cualquier evento que afecte al servicio. Como se ha descrito anteriormente, Teams depende de otros servicios de Microsoft 365 y Office 365 como Azure Active Directory, Exchange Online, SharePoint Online y OneDrive para la Empresa. Por este problema, es igualmente importante que supervise el estado de los servicios dependientes.

Incorpore esta actividad en el proceso de administración de incidentes para informar de forma proactiva a los usuarios, al departamento de soporte técnico y a sus equipos de operaciones, para prepararse para controlar las escalaciones de usuarios.

En las siguientes secciones se describen las herramientas que puede aprovechar para supervisar las [incidencias](https://technet.microsoft.com/library/office-365-service-health.aspx#Anchor_1) de servicio que afectan al servicio de Teams. En la tabla siguiente se incluye un resumen de las ventajas de cada herramienta y cuándo debería usar cada una.

| Herramienta de supervisión | Ventajas | Cuándo usar |
|---|---|---|
| Centro de administración de Microsoft 365 | Disponible desde cualquier dispositivo con un explorador compatible. | Úsese cuando no necesite notificaciones en tiempo real. |
| Aplicación de administración de Microsoft 365 | Proporciona notificaciones de inserción en su dispositivo móvil. | Use esta opción cuando necesite recibir notificaciones de incidentes de servicio mientras está fuera. |
| Microsoft System Center | Integración con Microsoft System Center. | Úsese cuando necesite funciones avanzadas de supervisión y soporte de notificaciones. |
| API de comunicaciones de servicio de Microsoft 365 | Acceso mediante programación al estado del servicio de Microsoft 365 u Office 365. | Úsese si necesita integración con una herramienta de supervisión de terceros o si desea crear su propia solución. |

> [!NOTE]
> Solo las personas a las que se les haya asignado el **rol de administrador de** servicios **o** administrador global pueden ver el estado del servicio.

### <a name="monitoring-with-the-microsoft-365-admin-center"></a>Supervisión con el Centro de administración de Microsoft 365

El Centro de administración de [](https://portal.office.com/adminportal/home#/servicehealth) [Microsoft 365](https://portal.office.com/) proporciona un panel Estado del servicio donde puede ver el estado actual del servicio de Teams además de los servicios dependientes.

### <a name="monitoring-with-the-mobile-app"></a>Supervisar con la aplicación móvil

La aplicación de administración de Microsoft 365 está disponible en Apple iOS, Android y Windows (PC y dispositivos móviles). La aplicación proporciona a los administradores de servicios información sobre el estado del servicio y los próximos cambios. La aplicación admite notificaciones de inserción que pueden avisarte casi inmediatamente después de que se haya publicado un aviso. Esto le ayudará a mantenerse al día sobre el estado, el estado y los próximos cambios en el servicio. El soporte técnico para notificaciones lo convierte en la herramienta de supervisión recomendada para administradores. Para obtener más información, vea:

[Aplicación móvil de Administración de Microsoft 365](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[Descargar la aplicación móvil Microsoft 365 Admin](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>Supervisión con Microsoft System Center

Microsoft System Center es una plataforma de administración integrada que le ayuda a administrar centros de datos, dispositivos cliente y entornos de TI de nube híbrida. Los administradores de Microsoft 365 u Office 365 que usan System Center ahora tienen la opción de importar el Módulo de administración, que les permite ver todas las comunicaciones de servicio en Operations Manager en System Center. El uso de esta herramienta le proporciona acceso al estado de los servicios suscritos, incidentes de servicio activos y resueltos, y las comunicaciones del Centro de mensajes (próximos cambios). Para obtener más información, consulte la siguiente [entrada de blog.](https://www.microsoft.com/en-us/microsoft-365/blog/2014/07/29/new-office-365-admin-tools/)

Si aprovecha System Center para supervisar el estado del servicio de Teams (y servicios dependientes), puede personalizar aún más el módulo de administración para alertar o notificar a grupos o personas específicas que se han identificado para reaccionar ante incidentes.
Estos grupos pueden incluir propietarios de servicios, departamento de soporte técnico, grupos de soporte técnico de segundo y tercer nivel, y administradores de incidentes de su organización.

### <a name="monitoring-for-advanced-scenarios"></a>Supervisión de escenarios avanzados

Puede supervisar el estado del servicio y los próximos cambios aprovechando la API de comunicaciones de servicio para obtener acceso al estado del servicio y a los cambios mediante programación. Use esta API para crear su propia herramienta de supervisión o conectar las herramientas de supervisión existentes a las comunicaciones de servicio de Microsoft 365 u Office 365, lo que podría simplificar el modo en que supervisa su entorno. Para obtener más información, [consulte Microsoft 365 u Office 365 para desarrolladores empresariales.](https://docs.microsoft.com/office/developer-program/microsoft-365-developer-program-faq)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas diarias,semanales/mensuales/según sea necesario

| Actividad | Descripción | Cadencia | Equipo asignado |
|---|---|---|---|
| Supervisar el estado del servicio | Supervise de manera proactiva el estado del servicio de Microsoft Teams (y los servicios dependientes) con las herramientas disponibles. Entre los servicios dependientes se incluyen: Exchange Online, SharePoint Online, OneDrive para la Empresa y Azure Active Directory. | En tiempo real | |
| Notificación de incidentes | Notifique a las partes interesadas internas de los eventos que afectan al servicio Teams. Las partes interesadas internas pueden incluir usuarios, departamento de soporte técnico y administradores de incidentes. | Según sea necesario | |

### <a name="references"></a>Referencias

[Cómo comprobar el estado del servicio de Microsoft 365 u Office 365](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[Comprobar el estado del servicio para Microsoft Teams](service-health.md)

[Continuidad y estado del servicio](https://technet.microsoft.com/library/office-365-service-health.aspx)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>Administrar el cambio de la organización

Microsoft Teams es un servicio basado en la nube. Con esto viene la capacidad de proporcionar nuevas características y funcionalidades a un ritmo rápido. Ofrecer innovación continua proporciona un beneficio evidente a las organizaciones, pero estos cambios deben administrarse correctamente dentro de la organización para evitar la resistencia de los usuarios o las escalaciones al departamento de soporte técnico.

Las actualizaciones de Teams se actualizan automáticamente para los usuarios. Los usuarios siempre tendrán el cliente más reciente y las características disponibles en el servicio Teams. No es posible administrar la implementación de actualizaciones de Teams para los usuarios, por lo que es de importancia crítica administrar el cambio a través de una comunicación, formación y programas de adopción eficaces. Si los usuarios son conscientes del cambio, sean conscientes de los beneficios y estén autorizados a aprovechar las nuevas capacidades que podrán adaptar más rápidamente y agradecen &mdash; el cambio.

### <a name="monitoring-for-change"></a>Supervisar el cambio

El primer paso en la administración de cambios es supervisar los cambios planeados para Teams. La mejor fuente para supervisar estos cambios es el mapa de ruta de [Microsoft 365,](https://www.microsoft.com/microsoft-365/roadmap)que enumera las características que están en desarrollo actualmente, que se están lanzando a los clientes o que se han lanzado completamente. Puede buscar características específicas de Teams con el filtro proporcionado o puede descargar la hoja de ruta en un archivo de Excel para realizar un análisis más exhaustivo. Para cada característica, la hoja de ruta proporciona una breve descripción, junto con la fecha de lanzamiento prevista.

En el [blog de Microsoft Teams,](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)puede obtener información sobre prácticas recomendadas, tendencias y noticias sobre las actualizaciones de productos de Teams. Espere a encontrar las principales actualizaciones de características de Teams que se anunciarán aquí. También puede suscribirse al blog a través de una fuente RSS. A continuación, [puede agregar la fuente RSS](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog) directamente a un canal de Teams para que todas las noticias importantes se entreguen directamente en Teams.

Todas las características que se lanzan se documentan en las notas [de la versión de Microsoft Teams.](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
Aquí encontrará una lista de características que se publicaron para equipos de escritorio, web y dispositivos móviles. El mismo conjunto de notas de la versión también está disponible en la **pestaña Novedades** de la [Ayuda.](get-help-in-microsoft-teams.md)

Familiarícese con los recursos disponibles y asegúrese de asignar propietarios correspondientes que supervisen el cambio.

### <a name="planning-for-change"></a>Planificación del cambio

Ahora que ya conoce los próximos cambios en el servicio Teams, el siguiente paso es prepararse y planear en consecuencia. Evalúe cada cambio para determinar qué cambios requieren comunicación a los usuarios, campañas de concienciación, formación para equipos de soporte técnico o usuarios, o campañas de evaluación y adopción de características. Este es el rol principal de un equipo de administración de cambios en su organización. A continuación se muestra una colección de tablas de ejemplo que pueden ayudarle a planear cambios.

#### <a name="feature-cloud-recording-release-date-january-2018"></a>Característica: Grabación en la nube (fecha de lanzamiento: enero de 2018)

**Seguimiento general**

| Cambiar disponibilidad | Estado | Notas/pasos siguientes | Propietario |
|---|---|---|---|
| Revisión legal | Completado | Esta característica es un requisito previo para incorporar el equipo de aprendizaje. | Equipo del proyecto |

**Administración de cambios técnicos**

| Cambiar disponibilidad | Estado | Notas/pasos siguientes | Propietario |
|---|---|---|---|
| Cambios de IT necesarios | Sí | El administrador debe habilitar la grabación solo para los usuarios identificados. | Equipo de soporte técnico |
| Preparación técnica completa | Sí | | Equipo de soporte técnico |
| | | | |

**Administración de cambios de usuario**

| Cambiar disponibilidad | Estado | Notas/pasos siguientes | Propietario |
|---|---|---|---|
| Impacto en el usuario | Bajo | | |
| Requisitos de disponibilidad del usuario | Sí | | |
| Comunicaciones listas | No | Se ha borrador del correo electrónico de comunicación, pendiente de revisión. | Communications Team |
| Aprendizaje listo | Sí | El aprendizaje aprovechará el vídeo de Microsoft existente. | Equipo de aprendizaje |

**Seguimiento del estado**

| Cambiar disponibilidad | Estado | Notas/pasos siguientes | Propietario |
|---|---|---|---|
| Estado de la versión | en curso | Pendiente de revisión por parte del patrocinador ejecutivo. | Equipo de administración de cambios |
| Firma de lanzamiento | | | |
| Fecha de lanzamiento | | | |

Para obtener más información sobre la planificación de la administración de cambios con Teams, vea Crear una estrategia de administración de [cambios para Microsoft Teams.](change-management-strategy.md)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas diarias,semanales/mensuales/según sea necesario

| Actividad| Descripción| Cadencia| Equipo asignado |
|---|---|---|---|
| Supervisar el cambio| Supervise los próximos cambios en el servicio Microsoft Teams.| Cada día||
| Planificación del cambio| Evalúe y planifique nuevas características y capacidades, incluidos los planes de comunicación, las campañas de concienciación y el aprendizaje.| Según sea necesario ||
| Disponibilidad del usuario| Realice campañas de comunicación, conciencia o aprendizaje dirigidas para asegurarse de que los usuarios estén preparados para el cambio que se realice.| Según sea necesario ||
| Preparación del equipo de soporte técnico | Realice campañas de aprendizaje, comunicación o conciencia dirigidas para asegurarse de que el equipo de soporte técnico esté preparado. Los equipos de soporte técnico pueden incluir el equipo "blanco", los grupos de soporte técnico, soporte técnico de nivel 2 o nivel 3, asociados externos, y así sucesivamente. | Según sea necesario ||

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>Evaluar el uso de Teams

Una vez que comience el piloto inicial, es fundamental establecer una cadencia regular para medir el uso real de Teams. Esto permite a su organización obtener información sobre cómo se alinea el uso real con el uso previsto durante la fase de visión. Aunque esta sección se centra en el uso de Teams, esto debería formar parte de un esfuerzo más amplio para medir y evaluar el uso de Microsoft 365 u Office 365 en general.

La revisión del uso con frecuencia al principio de la implementación le da la oportunidad de:

- Valide si los usuarios usan Teams.

- Identifique los posibles desafíos de adopción antes de crear problemas críticos en toda la organización.

- Comprenda si existen discrepancias entre los requisitos de la fase de visión y el uso real.

Si el uso no es lo que espera, puede deberse a un problema de implementación, a que el plan de adopción no se está ejecutando correctamente o a algún otro problema. Según la razón real por la que se ha reducido el uso, el administrador de servicios debe colaborar con los equipos relacionados para ayudar a eliminar las barreras de uso.

### <a name="measuring-usage-with-the-microsoft-365-admin-center"></a>Medición del uso con el Centro de administración de Microsoft 365

Los datos de uso de Teams están disponibles en el panel de informes. Los datos de uso de Teams se pueden encontrar en tres informes diferentes. El primer informe proporciona una vista de producto cruzada de cómo los usuarios se comunican y colaboran mediante los distintos servicios de Microsoft 365 u Office 365. Este informe puede encontrarse aquí: [Informes de Microsoft 365 en el Centro de administración: Usuarios activos](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

Los otros dos informes son específicos de Teams y proporcionan más detalles sobre el uso de Teams desde la perspectiva del usuario y el dispositivo. Ambos informes pueden encontrarse aquí:

[Informe de uso de dispositivos de Microsoft Teams](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-device-usage-917b3e1d-203e-4439-8539-634e80196687)

[Informe de actividad de usuario de Microsoft Teams](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-user-activity-07f67fc4-c0a4-4d3f-ad20-f40c7f6db524)

#### <a name="required-permissions"></a>Permisos necesarios

Las personas **a** las que se les haya asignado un rol de administrador global o un rol de administrador específico de un producto (administrador de **Exchange,** administrador de **Skype** Empresarial o administrador de **SharePoint)** pueden acceder a los informes de uso del centro de administración.

Además, el rol **de** lector De informes está disponible para los usuarios que necesitan tener acceso a los informes, pero que no realizan tareas que requieran permisos de administrador. Este rol se asigna para proporcionar informes de uso a cualquier persona que sea parte interesada y supervisar e impulsar la adopción. Para obtener más información sobre los diferentes roles disponibles, consulte [Acerca de los roles de administrador de Microsoft 365.](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)

### <a name="assessing-usage"></a>Evaluar el uso

Una vez que haya usado el panel de informes para medir el uso, es importante comparar el uso medido con cualquier indicador clave de éxito (KSIs) que definió durante la fase de visión del proyecto. Puede definir un KSI que se pueda definir como uso activo o que esté vinculado indirectamente al uso activo.

Es importante identificar las variaciones entre el uso real y el planeado antes de reanudar el lanzamiento a usuarios o sitios adicionales. Es probable que identifique los aprendizajes organizativos como parte de esta actividad que puede aprovechar para asegurarse de que el siguiente lote de sitios o usuarios no se encuentre con los mismos problemas.

En primer lugar, identifique si se trata de un problema técnico o de adopción. Empiece investigando los elementos siguientes para determinar dónde se encuentra el problema.

1. Valide la calidad realizando una [Revisión de calidad de la experiencia.](upgrade-monitor-quality.md)

2. Trabaje con el equipo del departamento de soporte técnico para comprobar que no hay problemas técnicos que impiden que los usuarios accedan o utilicen el servicio. Si hay tendencias de [](#endpoint-troubleshooting) problemas, use la sección de solución de problemas del extremo que se encuentra más adelante en este artículo para intentar solucionar el problema antes de involucrar al soporte técnico.

3. Trabaje con el equipo de formación y adopción para recopilar comentarios directos de los usuarios (vea Evaluar la opinión del usuario más adelante en este artículo) y para comprobar la eficacia de las actividades de adopción y concienciación. [](#assess-user-sentiment)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas diarias,semanales/mensuales/según sea necesario

| Actividad | Descripción | Cadencia | Equipo asignado |
|---|---|---|---|
| Uso de la medida (fase de habilitación) | Mida y evalúe el uso de Teams mientras los sitios se siguen incorporando durante la fase de habilitación. Solucionar problemas de uso según sea necesario. | Cada semana | |
| Medir el uso | Mida y evalúe el uso de Teams en la fase de valor de unidad (después de completar la implementación). Solucionar problemas de uso según sea necesario. | Cada dos semanas | |
| (fase de valor de unidad) | | | |
| Actualizar el plan de adopción | Actualice su plan de adopción en función de las diferencias de uso medido con los objetivos de planificación. | Según sea necesario | |

### <a name="references"></a>Referencias

[Acerca del Centro de administración de Microsoft 365](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Informes de actividades en el Centro de administración de Microsoft 365](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>Evaluar opinión del usuario

Comprender la opinión de los usuarios puede actuar como un indicador clave para medir el éxito de la implementación de Teams. Los comentarios de los usuarios pueden impulsar los cambios en su organización; esto puede incluir cambios en los planes de comunicación, los programas de aprendizaje o la forma en que ofrece soporte técnico a los usuarios.

Es importante recibir comentarios antes y continuar evaluando el estado de los usuarios durante el ciclo de vida del proyecto y más allá. Use las siguientes instrucciones para determinar el intervalo en que su organización buscará comentarios:

- **Comienzo del proyecto:** al evaluar la opinión de los usuarios al principio del proyecto, puede obtener una vista previa de cómo se sienten los usuarios sobre su experiencia en Teams.

- **Después de hitos principales:** mediante la recopilación de comentarios a lo largo del ciclo de vida del proyecto, puede evaluar la opinión de los usuarios de forma continua y realizar cambios según sea necesario. Esto es especialmente útil después de hitos importantes.

- **Conclusión** del proyecto: evaluar la opinión del usuario al final de un proyecto le dirá lo bien que ha hecho y dónde aún debe realizarse el trabajo, y le permite comparar resultados con la encuesta anterior.

- **Continuación:** siga miden la opinión de los usuarios de forma indefinida. Los cambios en la opinión de los usuarios pueden deberse a cambios en el entorno de su organización o a cambios en el servicio teams. Al medir la opinión de los usuarios a intervalos regulares, podrá comprender el rendimiento de sus equipos de administración de servicios y cómo está respondiendo su organización a los cambios en el servicio de Teams.

Los opiniones de los usuarios se pueden evaluar mediante muchos métodos diferentes. Pueden incluir encuestas de correo electrónico, entrevistas en persona o estilo telefónico, o simplemente crear un canal de comentarios en Teams o Yammer. Para obtener más información, vea [Procedimientos recomendados para métodos de comentarios de los usuarios en Microsoft Teams.](best-practices-feedback.md)

También puede usar un enfoque para todo el sector para evaluar la opinión de los usuarios denominada puntuación neta (NPS), que se describe en la sección siguiente.

### <a name="nps"></a>NPS

Net promoter score (NPS) is an industry-wide customer loyalty metric and a good approach to use to assess user sentiment. PARA calcular NPS, haga dos preguntas: "¿Qué probabilidad hay de que recomiendes Teams a un compañero?", seguida de la pregunta de forma libre"¿ Por qué?"

NPS es un índice entre -100 y 100 que mide la intención de un cliente de recomendar un producto o servicio de la compañía. NPS se basa en una encuesta anónima que se entrega a los usuarios a través del correo electrónico u otros medios electrónicos. NPS mide la fidelidad entre un proveedor y un consumidor. Se compone de solo una pregunta, que pide a los usuarios que den su experiencia de 1 a 10, con la opción de proporcionar comentarios adicionales. Los usuarios se clasifican en función de las siguientes clasificaciones:

- 9 o 10 son los patrocinadores: entusiastas leales que promocionarán su servicio y impulsarán a los demás.

- 7 u 8 son pasivos: satisfechos, pero no entusiastas, vulnerables a otro servicio u oferta.

- De 1 a 6 son los transportadores: los clientes insatisfechos que pueden dañar el servicio y impedir el crecimiento.

![Diagrama que muestra la escala de NPS](media/operate-my-service-image2.png "En este diagrama se muestra la escala de NPS. Muestra que los clasificadores de la 0 a la 6 son los que los detractores, del 7 al 8 son pasivos y del 9 al 10 son los patrocinadores.")

Aunque el número base de NPS es útil, obtenerás el máximo valor al analizar los comentarios de los usuarios. Le ayudarán a entender por qué el usuario recomienda (o no) Teams a otras personas. Estos comentarios pueden proporcionar comentarios valiosos para ayudar a los equipos de administración de proyectos o servicios a comprender los ajustes necesarios para proporcionar un servicio de calidad.

Para proporcionar encuestas NPS a su organización, puede usar su herramienta de encuesta en línea favorita.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas diarias,semanales/mensuales/según sea necesario

| Actividad | Descripción | Cadencia | Equipo asignado |
|---|---|---|---|
| Evaluar opinión del usuario | Capture y evalúe la opinión de los usuarios mediante encuestas o entrevistas, o a través de un canal de comentarios en Teams o Yammer. | Según sea necesario | |
| Actualizar planes de adopción | Impulsar el cambio en la organización en función de los comentarios de los usuarios; esto puede incluir cambios en los planes de comunicación, los programas de aprendizaje o la forma en que ofrece soporte técnico a los usuarios. | Según sea necesario | |

### <a name="references"></a>Referencias

[Net Promoter Score](https://en.wikipedia.org/wiki/Net_Promoter)

[Usar Yammer para recopilar comentarios](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[Procedimientos recomendados para los comentarios de los usuarios](best-practices-feedback.md)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>Administrar la calidad de la red

Muchos elementos básicos de planeación van a la optimización, el dimensionamiento derecho y la corrección de su infraestructura de red para garantizar una ruta de alta calidad y eficiente al servicio de Microsoft Teams. Las tareas y requisitos de planificación están cubiertos en nuestra [guía de disponibilidad de](prepare-network.md) red. Las redes a menudo evolucionan a lo largo del tiempo debido a actualizaciones, expansión u otros requisitos empresariales. Es importante que en cuenta los requisitos de Teams en las actividades de planificación de red.

Aunque la planificación de red es un aspecto crítico de la implementación de Teams, es igualmente importante asegurarse de que la red permanece en buen estado y se mantiene actualizada en función de los requisitos técnicos o empresariales cambiantes.

Para garantizar el estado de su red, es necesario realizar varias actividades de operaciones a intervalos regulares.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas diarias,semanales/mensuales/según sea necesario

| Actividad | Descripción | Cadencia | Equipo asignado |
|---|---|---|---|
| Supervisar direcciones URL y IP de Microsoft 365 u Office 365 | Supervise cualquier cambio en los intervalos de direcciones IP y URL de [Office 365](https://aka.ms/o365ips) con la fuente [RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) proporcionada e inicie una solicitud de cambio para los grupos de redes aplicables. | Cada día | |
| Actualizar la red en función de los cambios realizados en las DIRECCIONES IP y URL de Microsoft 365 u Office 365 | Realice actualizaciones en los componentes de red correspondientes (firewalls, servidores proxy, VPN, firewalls de lado cliente, y así sucesivamente) para reflejar los cambios en las url y los intervalos de direcciones IP de [Office 365.](https://aka.ms/o365ips) | Según sea necesario | |
| Proporcionar datos de creación | Proporcione información de subred actualizada al responsable de la calidad (o a las partes interesadas relevantes) para asegurarse de que las definiciones de compilación del [CQD](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) se mantienen actualizadas. | Según sea necesario | |
| Implementar cambio | Implemente cambios en la red para admitir cambios en los requisitos técnicos y empresariales de Teams. Los elementos de red pueden incluir:<ul><li>Firewalls</li><li>VPN</li><li>Redes cableadas y Wi-Fi cable</li><li>Conectividad a Internet y ExpressRoute</li><li>DNS</li></ul> | Según sea necesario | |
| Supervisión e informes de red | Supervise de un extremo a otro la red para identificar la disponibilidad, el uso y las tendencias de capacidad usando las herramientas de administración de red de terceros y las capacidades de creación de informes existentes de sus proveedores de red. Use datos de tendencia para la planificación de capacidad de red. | Diariamente, semanalmente, mensualmente | |
| Planificación de la capacidad | Colabore con los propietarios de servicio de Teams para comprender los requisitos técnicos y empresariales cambiantes que pueden impulsar cambios adicionales en la capacidad.  | Según sea necesario | |
| Solución de problemas y corrección de red | Ayude al departamento de soporte técnico de Teams, a los propietarios del servicio y a las principales partes interesadas a solucionar problemas relacionados con la conectividad, la confiabilidad o la calidad de Teams. Los elementos de red pueden incluir:<ul><li>Firewalls</li><li>VPN</li><li>Redes cableadas y Wi-Fi cable</li><li>Conectividad a Internet y ExpressRoute</li><li>DNS</li></ul> | Según sea necesario | |
| Recuperación ante desastres y pruebas de alta disponibilidad | Realice pruebas periódicas de alta disponibilidad y recuperación ante desastres en la infraestructura de red para asegurarse de que cumple los objetivos de nivel de servicio (SLOs) o los contratos de nivel de servicio (SLA) establecidos para el servicio de Teams. | Cada mes | |

### <a name="references"></a>Referencias

[Direcciones URL e intervalos de direcciones IP de Office 365](https://aka.ms/o365ips)

[Crear esquema de datos](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>Evaluar y garantizar la calidad

Todas las organizaciones necesitan un grupo o una persona para ser responsables de la calidad. Es, sin duda, el rol más importante en la administración de servicios. El rol de profesional de calidad se asigna a una persona o grupo que es apasionado de la experiencia de sus usuarios.
y requiere las habilidades adecuadas para identificar tendencias del entorno y el respaldo necesario para poder trabajar con otros equipos y dirigir las correcciones que corresponda. El mejor candidato para ser experto en calidad es normalmente el propietario del servicio al cliente. Dependiendo del tamaño y la complejidad de la organización, esta podría ser cualquier persona o grupo que le apasiona por garantizar una experiencia de usuario de alta calidad.

El profesional de calidad aprovecha las herramientas y procesos documentados existentes, como el panel de calidad de llamadas (CQD) y mejora y supervisa la calidad de las llamadas de [Teams,](monitor-call-quality-qos.md)para supervisar la experiencia del usuario, identificar tendencias de calidad y controlar la corrección cuando sea necesario.
El expertos en calidad debe trabajar con los equipos respectivos para dirigir las acciones de corrección e informar a un comité de dirección sobre el progreso y los problemas abiertos.

[Mejorar y supervisar la calidad de](monitor-call-quality-qos.md) las llamadas en Teams incluye actividades que evalúan y proporcionan instrucciones de corrección en áreas clave que tienen el mayor impacto en la mejora de la experiencia del usuario. Las instrucciones que se proporcionan en la Guía de revisión de la experiencia de calidad se centran en el uso del CQD Online como herramienta principal para informar e investigar cada área, con un enfoque en el audio para maximizar la adopción y el impacto. Las optimizaciones que se realicen en la red para mejorar la experiencia de audio se traducirán directamente en mejoras de las de vídeo y escritorio compartido.

Le recomendamos encarecidamente que designe al expertos en calidad al principio. Después de ser nominados, deberían empezar a familiarizarse con el contenido en Mejorar y supervisar la calidad de las llamadas [de Teams](monitor-call-quality-qos.md) y los materiales de aprendizaje asociados.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas diarias,semanales/mensuales/según sea necesario

| Actividad | Descripción | Cadencia | Equipo asignado |
|---|---|---|---|
| Nominar y entrenar a los campeones de la calidad del tren | Designe y entrena a un campeón de calidad. | Según sea necesario | |
| Realizar opiniones sobre la calidad de la experiencia (QERs) | Realice un TER para identificar tendencias en calidad y confiabilidad, revisar según objetivos definidos e informar a las principales partes interesadas de la organización. | Mensual (semanal durante las implementaciones) | |
| Corrección de unidades | Coordine los esfuerzos de corrección en toda la organización en función de las evaluaciones y resultados de QER. | Según sea necesario | |
| Actualizar los datos de creación en el CQD | Actualice o agregue nuevas definiciones de compilación en el CQD cuando se realicen cambios en la red (vea [Cargar información de compilación).](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) | Según sea necesario | |
| Completar el rol de campeón de calidad | Responsabilidad de calidad de una organización de un extremo a otro. Esto incluye:<ul><li>Asegúrese de que el QER se realice periódicamente.</li><li>Informe a las partes interesadas clave sobre el estado de la calidad.</li><li>Asegúrese de que las definiciones de datos de compilación estén actualizadas.</li><li>Coordine los esfuerzos de corrección en toda la organización para garantizar que los usuarios tengan una experiencia de alta calidad con Teams.</li></ul> | Cada día | |

### <a name="references"></a>Referencias

[Cargar información de edificio](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)

[Mejorar y supervisar la calidad de las llamadas en Teams](monitor-call-quality-qos.md)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>Administrar puntos de conexión

Los puntos de conexión de Microsoft Teams se pueden definir como cualquier pc, Mac, tableta o dispositivo móvil (o cualquier otro) que ejecute el cliente de Teams. El *término* extremo no solo abarca el propio dispositivo, sino la forma en que el usuario se conecta al dispositivo (por ejemplo, con el micrófono o altavoces integrados del dispositivo, auriculares o auriculares optimizados). Una vez implementados, no es necesario olvidar los puntos de conexión. Los puntos de conexión de Teams requieren un mantenimiento y un cuidado continuos. En las siguientes secciones se describen áreas específicas en las que centrarse.

### <a name="endpoint-requirements"></a>Requisitos del punto de conexión

Una de las principales ventajas de Teams es que el cliente se mantiene actualizado automáticamente. Los clientes de PC y Mac se actualizan mediante un proceso en segundo plano que comprueba si hay nuevas compilaciones y descarga el cliente nuevo cuando la aplicación está inactiva. Las aplicaciones móviles de Teams se mantienen actualizadas en las tiendas de aplicaciones correspondientes.

El cliente de Teams tiene requisitos mínimos en cuanto a la plataforma de software subyacente. Estos requisitos pueden cambiar con el tiempo y, por tanto, es importante que los supervise para ver si hay cambios. Por ejemplo, el cliente de Teams tiene una versión mínima de iOS. Si el cliente usa un explorador de Internet, el explorador debe mantenerse también al día. Puede encontrar una lista de plataformas admitidas en [Obtener clientes para Microsoft Teams.](get-clients.md)

### <a name="endpoint-firewalls"></a>Firewalls para los puntos de conexión

Los firewalls del cliente pueden repercutir de forma significativa en la experiencia de usuario.
Los firewall del cliente pueden afectar a la calidad de las llamadas e incluso evitar que se establezca una llamada. Una vez que se hayan configurado las exclusiones adecuadas en el firewall del cliente, es necesario mantenerlas actualizadas en función de la información de las DIRECCIONES URL e intervalos de direcciones IP de [Office 365.](https://aka.ms/o365ips) Su proveedor de terceros tendrá instrucciones específicas para actualizar las exclusiones.

### <a name="wi-fi-drivers"></a>Controladores Wi-Fi

Wi-Fi controladores pueden tener problemas. Por ejemplo, un controlador podría tener comportamientos de itinerancia muy agresivos entre puntos de acceso que pueden provocar cambios innecesarios en los puntos de acceso, llevando a una calidad de llamada deficiente. Puede que un controlador de Wi-Fi rendimiento deficiente se descubra a través de una Revisión de la calidad de la experiencia (vea Mejorar y supervisar la calidad de las llamadas [en Teams](monitor-call-quality-qos.md) para obtener más información). Es esencial implementar un proceso basado en la calidad que monitore los nuevos controladores de Wi-Fi y se asegure de que se prueban antes de implementarse en el número general de usuarios.

### <a name="endpoint-management"></a>Administración de puntos de conexión

Un catálogo de puntos de conexión y dispositivos de interfaz compatibles (como auriculares) debe estar disponible y mantenido. Este catálogo incluirá una lista de dispositivos aprobados que se seleccionaron y validaron como parte de las fases De visión e incorporación. Normalmente, se seleccionan dispositivos específicos para cada tipo de rol de la organización para satisfacer las necesidades de los atributos de ese rol. Todos los puntos de conexión tienen un ciclo de vida y necesita administrar los contratos de los proveedores, la garantía, el reemplazo, la distribución y las directivas de reparación asociadas con estos dispositivos.

### <a name="endpoint-troubleshooting"></a>Solución de problemas de puntos de conexión

Incluso si ha seguido las instrucciones anteriores, los usuarios de su organización todavía podrían tener problemas con Teams. Aunque es posible que el problema no tenga que ver con el propio punto de conexión, los síntomas del problema suelen llegar a través del cliente al usuario. Las siguientes instrucciones están pensadas para proporcionar pasos generales que puede seguir para resolver el problema; no está pensado para ser una guía completa de solución de problemas. Los pasos se proporcionan en un orden específico, pero no tienen que seguirse explícitamente y es posible que no sean aplicables, según la naturaleza del problema.

1. **Validar el estado del servicio:** El problema que un usuario puede estar experimentando puede estar relacionado con un evento que afecte negativamente al servicio de Teams o a sus servicios dependientes. Como primer paso, le recomendamos que confirme que no hay ningún problema de servicio activo. Consulte [cómo comprobar el estado del servicio de Microsoft 365.](https://docs.microsoft.com/office365/enterprise/view-service-health) Recuerde comprobar el estado de los servicios dependientes (por ejemplo, Exchange, SharePoint, OneDrive para la Empresa). La supervisión del estado del servicio se describe con más detalle en la sección anterior, Supervisar el [estado del servicio.](#monitor-service-health)

2. **Validar la conectividad de cliente:** Los problemas de conectividad provocan problemas de funcionalidad o inicio de sesión en Teams. Le recomendamos (especialmente para nuevos sitios o ubicaciones) que valide la conectividad con el servicio. Asegúrese de que se siguen las siguientes directrices de intervalos de direcciones IP y URL de [Office 365](https://aka.ms/o365ips) para cada sitio. Puede usar la Herramienta de evaluación de red [de Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para realizar una prueba de conectividad y validar que los puertos multimedia se han abierto correctamente para las capacidades de Teams. Los pasos detallados sobre cómo ejecutar las pruebas de conectividad se proporcionan en la guía [de preparación de](prepare-network.md) red.

3. **Compruebe la lista de problemas conocidos:** Consulte [la solución de problemas](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams) de Teams para determinar si uno de estos problemas ha afectado negativamente al usuario. Siga las soluciones alternativas proporcionadas (si hay una) para resolver el problema.

4. **Visite la comunidad de Microsoft Teams:** La [comunidad de Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams) ofrece espacios dedicados para Teams. La comunidad de Teams proporciona una lista de discusión, entradas de blog y anuncios centrados en Teams. Puedes publicar una pregunta o buscar en discusiones anteriores soluciones a tu problema.

5. **Ponte en contacto con el soporte técnico de Microsoft:** Puede ponerse en contacto con el soporte técnico de Microsoft para resolver problemas relacionados con Teams en línea o por teléfono. Para obtener más información, consulte [Ponerse en contacto con el soporte técnico para productos empresariales: Ayuda para administradores.](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products) Para los clientes Premier, las solicitudes de soporte se pueden iniciar siguiendo las instrucciones de ponerse en contacto con el soporte técnico [de Microsoft Teams (clientes Premier).](https://support.microsoft.com/premier/contacts)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas diarias,semanales/mensuales/según sea necesario

| Actividad | Descripción | Cadencia | Equipo asignado |
|---|---|---|---|
| Requisitos del punto de conexión | Asegúrese de que el punto de conexión de Teams sigue cumple todos los requisitos de software para Teams que aparecen en [Obtener clientes para Microsoft Teams.](get-clients.md) | Cada mes | |
| Firewalls para los puntos de conexión | Mantenga las exclusiones adecuadas en el firewall del punto de conexión en función de la información de las direcciones URL e intervalos de [direcciones IP de Office 365.](https://aka.ms/o365ips) Su proveedor de terceros tendrá instrucciones específicas para mantener las exclusiones. Suscríbase [a la fuente RSS](https://support.office.com/o365ip/rss) para recibir notificaciones automáticas de los cambios. | Según sea necesario | |
| Controladores Wi-Fi | Prueba y actualiza Wi-Fi controladores en el equipo. Valide los resultados con el CQD (mejorar y supervisar la[calidad de las llamadas en Teams).](monitor-call-quality-qos.md) | Según sea necesario | |
| Administración de puntos de conexión | Mantener el catálogo de puntos de conexión y dispositivos de interfaz compatibles (como auriculares). Administre las directivas de contratos, garantía, distribución, sustitución y reparación de proveedores. | Cada mes | |
| Solución de problemas de puntos de conexión | Las tareas de solución de problemas pueden incluir la comprobación de la conectividad, la consultoría de la lista de problemas conocidos, la recopilación de registros, el análisis y el escalamiento a Soporte técnico de Microsoft o a proveedores de terceros. | Según sea necesario | |

### <a name="references"></a>Referencias

[Direcciones URL e intervalos de direcciones IP de Office 365](https://aka.ms/o365ips)

[Obtener clientes para Microsoft Teams](get-clients.md)

[Comunidad de Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Solución de problemas de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

[Comprobar el estado del servicio para Microsoft Teams](service-health.md)

[Contactar con el soporte técnico para productos empresariales: ayuda para administradores](https://support.office.com/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

[Ponerse en contacto con el soporte técnico Premier](https://support.microsoft.com/premier/contacts)

[Solución de problemas de vídeo de Teams](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>Administrar Teams

Una vez implementado el servicio Microsoft Teams, deberá realizar varias actividades relacionadas con su administración. Las actividades van desde la administración del servicio y los usuarios individuales hasta el planeamiento de capacidad y el aprovisionamiento de licencias y números de teléfono. En las secciones siguientes se descubren algunas de estas tareas de administración comunes.

### <a name="service-administration"></a>Administración de servicios

El servicio teams tiene varias opciones de configuración que se pueden configurar en todo el espacio empresarial.
Los cambios realizados en la configuración del inquilino afectan a todos los usuarios que se han habilitado para Teams. Para obtener una lista detallada de estas opciones de configuración, consulte [Administrar la configuración de Microsoft Teams para su organización.](enable-features-office-365.md)

### <a name="user-administration"></a>Administración de usuarios

Para dar soporte a los usuarios, una organización puede requerir cualquier número de tareas relacionadas: las tareas específicas varían de una organización a la siguiente. En última instancia, estas tareas deben ser administradas por un equipo de soporte técnico al que se le han asignado estas tareas operativas. Por lo general, se necesitan las siguientes tareas para dar soporte a los usuarios de Teams.

#### <a name="general-tasks"></a>Tareas generales

[Administrar el acceso de los usuarios a Microsoft Teams](user-access.md)

### <a name="team-creation-optional"></a>Creación de equipos (opcional)

De forma predeterminada, todos los usuarios con un buzón en Exchange Online tienen permisos para crear grupos de Microsoft 365 y, por tanto, un equipo de Microsoft Teams. Si desea tener un control [](assign-roles-permissions.md#permissions-to-create-teams) más estrecho y restringir la creación de nuevos equipos (y, por tanto, la creación de nuevos grupos de Microsoft 365), puede delegar los derechos de creación y administración de grupos a un conjunto de administradores. Si su organización desea proseguir con esta opción, vea el proceso descrito en este artículo para permitir a los usuarios enviar solicitudes que son procesadas por un equipo asignado.

<!--ENDOFSECTION-->

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas diarias,semanales/mensuales/según sea necesario

| Actividad | Descripción | Cadencia | Equipo asignado |
|---|---|---|---|
| Administración de servicios | Administración de la configuración de Teams para todos los inquilinos. | Según sea necesario | |
| Administración de usuarios | Administración de la configuración y licencias basadas en el usuario en Teams. | Según sea necesario | |
| Administración de licencias | Planee las necesidades actuales y futuras de las licencias basadas en el consumo (planes de llamadas y créditos de comunicación) con el informe de uso de [RTC](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) y el informe de grupos de [minutos RTC.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) | Cada semana | |
| Administración de números de teléfono | Administre los números de teléfono disponibles para crecimiento futuro y ajuste los niveles de inventario para satisfacer las necesidades de la organización. | Cada semana | |
| Creación de equipos (opcional) | Revise y procese solicitudes para la creación de equipos. | Según sea necesario | |

<!--ENDOFSECTION-->
