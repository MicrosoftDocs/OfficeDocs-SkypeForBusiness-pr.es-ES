---
title: Operaciones para Microsoft Teams | Administración de servicios | Compra
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Tareas y actividades necesarias para la administración de servicios de Teams, como la supervisión del estado del servicio, la evaluación y la seguridad de la calidad y el uso de la red
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
ms.openlocfilehash: 434b7e0fed87d6273d13c7cb646079d51d7c1ddc
ms.sourcegitcommit: 8b172e9a0d0626c9a88998600d4b17c6c8cdadd2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44761478"
---
# <a name="operate-your-service"></a>Ejecutar los servicios

![Diagrama de viaje de actualización, énfasis en la fase de excelencia operativa](media/upgrade-banner-op-excellence.png "Etapas del viaje de actualización, con énfasis en la fase de excelencia operativa")

Este artículo forma parte de la fase de excelencia operativa de su viaje de actualización, que comienza tan pronto como haya completado la actualización de Skype empresarial a teams.

Este artículo proporciona una descripción general de los requisitos para que los equipos de su organización funcionen correctamente después de la actualización. Al funcionar correctamente los servicios de Teams, puede asegurarse de que está proporcionando una experiencia de alta calidad y confiable para su organización.

## <a name="introduction-to-the-operations-guide"></a>Introducción a la guía de operaciones

La guía de operaciones le ofrece información general sobre todas las tareas y actividades necesarias como parte de la función de administración de servicios de Microsoft Teams.

La administración de servicios es un tema muy amplio que cubre las operaciones del día a día del servicio de Microsoft Teams una vez que se ha implementado y habilitado para los usuarios. El servicio de Teams abarca Microsoft 365 u Office 365 y los componentes de infraestructura implementados localmente (por ejemplo, redes).

Seguramente, el concepto de "administración de servicios" no es nuevo para la mayoría de organizaciones. Es posible que ya haya implementado procesos y tareas asociados a servicios existentes. Dicho esto, es posible que pueda complementar sus procesos actuales al planear la administración de servicios hoy para admitir equipos en el futuro.

La administración de servicios engloba todas las actividades y los procesos implicados en la administración de los equipos de un extremo a otro. Como se mencionó anteriormente, algunos componentes de la administración de servicios (la infraestructura que el propio servicio de Microsoft 365 u Office 365) son responsabilidad de Microsoft, mientras que usted, el cliente, se responsabilizará a los usuarios de administrar los diversos aspectos de Teams, la red y los puntos de conexión que proporciona.

Las tareas y actividades de esta guía se agrupan en ocho categorías, tal como se muestra en el siguiente diagrama. Cada una de estas categorías se expandirá en las secciones siguientes.

![Un diagrama que muestra una lista de categorías de tareas y actividades](media/operate-my-service-image1.png "Un diagrama que muestra una lista de las categorías de tareas y actividades que incluye la administración de servicios para los equipos. El diagrama también representa que la administración de servicios es en gran medida una tarea de cliente.")

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Puntos de decisión</td><td><ul><li>Decidir cómo se implementarán las operaciones para Teams.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Pasos siguientes</td><td><ul><li>Revise completa la guía de operaciones.</li><li>Implemente una estrategia de operaciones que se alinee con los objetivos de su organización para ofrecer la calidad y confiabilidad de las cargas de trabajo de Teams.</li><li>Revise la guía de revisión de la calidad de la experiencia.</li><li> Implemente una estrategia de operaciones para realizar regularmente revisiones de la experiencia de la experiencia para asegurarse de que su implementación de equipos está funcionando a su máxima capacidad.</li></ul></td></tr>
</table>

### <a name="operational-role-mapping"></a>Asignación de roles operativos

La planificación que se está aprovechando para las operaciones durante la fase de previsión es crítica, ya que las actividades de operaciones comienzan cuando se habilitan los primeros usuarios de la prueba piloto. En esta guía se enumeran las actividades y tareas que deben realizarse diariamente, semanalmente, mensualmente o según sea necesario para mantener una implementación de equipos de alta calidad. Esta guía proporciona información y consejos sobre cómo realizar estas actividades y tareas críticas.

Un componente crucial de una implementación exitosa es garantizar que la planificación que realiza en el momento de la fase de previsión incluye determinar quién será el responsable de realizar actividades específicas. Una vez que haya averiguado qué tareas y actividades se aplican a su implementación, deben ser entendidos y seguidas por los grupos o las personas que les asigne.

Cada equipo que identifique debe revisar y aceptar las tareas y responsabilidades identificadas y comenzar la preparación. Esto puede incluir formación y preparación, proporcionar actualizaciones para el plan de personal o garantizar que los proveedores externos estén listos para su entrega.

Las actividades y roles definidos en esta guía deben ser válidos en la mayoría de los escenarios, pero todas las implementaciones de equipos son únicas; por lo tanto, puede usar esta guía como punto de partida para personalizar las actividades y los roles predeterminados para satisfacer sus necesidades.

Asegúrese de que cada equipo contable tenga una buena comprensión de las actividades necesarias para ejecutar el servicio. Es fundamental que cada equipo acepte y desactive la responsabilidad de su organización antes de que comience la primera prueba piloto.

Una vez que se haya implementado un contrato, los equipos correspondientes deberán comenzar a operar sus roles.

<table>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Pasos siguientes</td>
<td><ul><li>Use este documento para facilitar el ejercicio de asignación de roles operativos.</li><li>Reunirse con los respectivos equipos de soporte técnico para asignar nombres a cada elemento de la lista de actividades necesarias.</li><li>Gana la aceptación o la aprobación de los roles asignados.</li><li>Asegúrese de que los equipos correspondientes tengan la formación, preparación y recursos adecuados para completar las actividades que necesiten.</li></ul></td></table>

### <a name="teams-service-dependencies"></a>Dependencias del servicio de Teams

Microsoft Teams reúne tecnologías en Microsoft 365 y Office 365 para proporcionar un hub para el trabajo en equipo. Entre los ejemplos se incluyen:

- Azure Active Directory (Azure AD) proporciona servicios de autenticación y autorización para Teams.

- Exchange Online proporciona características avanzadas como la retención legal y el descubrimiento electrónico.

- SharePoint Online ofrece la posibilidad de compartir archivos en canales y OneDrive para la empresa proporciona un mecanismo para compartir archivos dentro de una conversación privada.

Las organizaciones también pueden aprovechar las inversiones existentes en la infraestructura local. Por ejemplo, se pueden usar cuentas locales existentes de Active Directory para la autenticación aprovechando Azure AD Connect. Algunas versiones de Exchange Server se pueden usar en lugar de Exchange Online.

Estas tecnologías se combinan para ofrecer a los usuarios un conjunto de programas de comunicaciones inteligente, colaborativo y enriquecido. Esta estrecha integración es un beneficio clave de Teams, pero también impulsa un requisito para la administración de servicios en estas tecnologías.

Esta guía cubre las principales áreas de focalización para administrar el servicio de Teams. Lo más probable es que haya planes de administración de servicios para las tecnologías de asistencia que dependen de Teams. Si no es así, tendrá que establecer planes de administración de servicios adecuados para esos componentes tecnológicos (locales y en línea). Esto ayudará a garantizar que los usuarios disfrutan de una experiencia confiable y de alta calidad con Teams.

#### <a name="references"></a>Referencias

[Información general sobre Microsoft Teams](teams-overview.md)

[Interacción entre Exchange y Microsoft Teams](exchange-teams-interact.md)

[Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams](sharepoint-onedrive-interact.md)

[Coexistencia e interoperabilidad de Microsoft Teams y Skype empresarial](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>Actividades de la guía de operaciones

En las siguientes secciones se ofrece información general sobre las actividades necesarias para operar correctamente el servicio de Microsoft Teams. Incluyen una referencia a herramientas, información contextual y contenido adicional que le ayudan a comprender la actividad y ayudar a las iniciativas de preparación.

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>Supervisar el estado del servicio

Es importante que comprenda el estado general del servicio Microsoft Teams para que pueda avisar de forma proactiva sobre otros usuarios de su organización de cualquier evento que afecte al servicio. Como se ha descrito anteriormente, Teams depende de otros servicios de Microsoft 365 y Office 365, como Azure Active Directory, Exchange Online, SharePoint Online y OneDrive para la empresa. Por eso, es igualmente importante que Supervises el estado de los servicios dependientes.

Incorpore esta actividad en el proceso de administración de incidentes para informar de forma proactiva a los usuarios, al Departamento de soporte técnico y a sus equipos de operaciones para prepararse para administrar los aumentos de usuario.

En las siguientes secciones se describen las herramientas que puede aprovechar para supervisar los [incidentes de servicio](https://technet.microsoft.com/library/office-365-service-health.aspx#Anchor_1) que afectan al servicio de Teams. En la tabla siguiente se incluye un resumen de las ventajas de cada herramienta y cuándo se debe usar cada una de ellas.

| Herramienta de supervisión | Ventajas | Cuándo usar |
|---|---|---|
| Centro de administración de Microsoft 365 | Disponible desde cualquier dispositivo con un explorador compatible. | Usar cuando no necesite notificaciones en tiempo real. |
| Aplicación de administración de Microsoft 365 | Proporciona notificaciones de inserción a su dispositivo móvil. | Utilícelo cuando necesite recibir notificaciones de incidentes de servicio mientras está de viaje. |
| Microsoft System Center | Integración con Microsoft System Center. | Utilícelo cuando necesite capacidades de supervisión avanzadas y soporte de notificaciones. |
| API de comunicaciones de servicio de Microsoft 365 | Acceso mediante programación al estado del servicio de Microsoft 365 u Office 365. | Utilícelo cuando necesite la integración con una herramienta de supervisión de terceros o desee crear su propia solución. |

> [!NOTE]
> Solo las personas que tienen asignado el rol de **Administrador** **global** o de administrador de servicios pueden ver el estado del servicio.

### <a name="monitoring-with-the-microsoft-365-admin-center"></a>Supervisión con el centro de administración de Microsoft 365

El [centro de administración de Microsoft 365](https://portal.office.com/) proporciona un [Panel de estado del servicio](https://portal.office.com/adminportal/home#/servicehealth) en el que puede ver el estado actual del servicio de Teams, además de los servicios dependientes.

### <a name="monitoring-with-the-mobile-app"></a>Supervisar con la aplicación móvil

La aplicación de administración de Microsoft 365 está disponible en Apple iOS, Android y Windows (PC y móvil). La aplicación proporciona a los administradores de servicios información sobre el estado del servicio y los próximos cambios. La aplicación admite notificaciones Push que pueden alertarte casi inmediatamente después de que se haya publicado un aviso. Esto le ayuda a estar al día de la situación, la salud y los próximos cambios en el servicio. La compatibilidad de notificaciones lo convierte en la herramienta de supervisión recomendada para los administradores. Para obtener más información, vea:

[Aplicación móvil de administración de Microsoft 365](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[Descargar la aplicación móvil de administración de Microsoft 365](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>Supervisión con Microsoft System Center

Microsoft System Center es una plataforma de administración integrada que le ayuda a administrar el centro de información, los dispositivos cliente y los entornos de TI de nube híbrida. Los administradores de Microsoft 365 o de Office 365 que usan System Center ahora tienen la opción de importar el módulo de administración, que les permite ver todas las comunicaciones de servicio dentro de Operations Manager en System Center. El uso de esta herramienta le da acceso al estado de los servicios suscritos, los incidentes de servicio activos y resueltos y las comunicaciones del centro de mensajes (próximos cambios). Para obtener más información, consulte la siguiente [entrada de blog](https://blogs.office.com/2014/07/29/new-office-365-admin-tools/?eu=true).

Si aprovecha System Center para supervisar el estado del servicio de Teams (y los servicios dependientes), puede personalizar aún más el módulo de administración para alertar o notificar a grupos específicos o a individuos que hayan sido identificados para que respondan a incidentes.
Estos grupos pueden incluir los administradores de servicios, los departamentos de soporte técnico, los grupos de soporte de segundo nivel y de tercer nivel, y los administradores de incidentes de su organización.

### <a name="monitoring-for-advanced-scenarios"></a>Supervisión de escenarios avanzados

Puede supervisar el estado del servicio y los próximos cambios aprovechando la API de comunicaciones de servicio para obtener acceso a estado y cambios de servicio mediante programación. Use esta API para crear su propia herramienta de supervisión o Conecte sus herramientas de supervisión existentes a las comunicaciones de servicio de Microsoft 365 u Office 365, lo que puede simplificar la supervisión de su entorno. Para obtener más información, consulte [Microsoft 365 u Office 365 para programadores de empresa](https://msdn.microsoft.com/library/jj984343(v=office.15).aspx).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas diarias/semanales/mensuales/según sea necesario

| Actividad | Descripción | Cadencia publicación | Equipo asignado |
|---|---|---|---|
| Supervisar el estado del servicio | Supervise de forma proactiva el estado del servicio de Microsoft Teams (y los servicios dependientes) con las herramientas disponibles. Entre los servicios dependientes se incluyen Exchange Online, SharePoint Online, OneDrive para la empresa, Azure Active Directory. | En tiempo real | |
| Notificación de incidente | Notifique a los participantes internos los eventos que afectan al servicio de Teams. Entre los participantes internos se incluyen los usuarios, el Departamento de soporte técnico y los administradores de incidentes. | Según sea necesario | |

### <a name="references"></a>Referencias

[Cómo comprobar el estado del servicio de Microsoft 365 u Office 365](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[Comprobar el estado del servicio para Microsoft Teams](service-health.md)

[Continuidad y estado del servicio](https://technet.microsoft.com/library/office-365-service-health.aspx)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>Administrar el cambio organizacional

Microsoft Teams es un servicio basado en la nube. Gracias a esto se obtiene la capacidad de ofrecer nuevas características y funcionalidades a un ritmo rápido. Ofrecer una innovación continua ofrece una ventaja obvia para las organizaciones, pero estos cambios deben administrarse adecuadamente dentro de la organización para evitar la resistencia del usuario o el aumento de nivel al Departamento de soporte técnico.

Las actualizaciones de Teams se distribuyen automáticamente a los usuarios. Los usuarios siempre tendrán el cliente y las características más recientes disponibles en el servicio de Teams. No es posible administrar la implementación de actualizaciones de Teams para los usuarios, por lo que es muy importante administrar los cambios mediante programas de comunicación, aprendizaje y adopción eficaces. Si los usuarios son conscientes del cambio, les ha informado sobre los beneficios y están capacitados para aprovechar las nuevas capacidades, podrán &mdash; adaptarse más rápidamente y Bienvenido al cambio.

### <a name="monitoring-for-change"></a>Supervisión de cambios

El primer paso de la administración de cambios es la supervisión de los cambios planeados para Teams. La mejor fuente de supervisión de estos cambios es la [hoja de ruta de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap), que enumera las características actualmente en desarrollo, que se están implementando para los clientes o que se han iniciado completamente. Puede buscar características específicas de Teams mediante el filtro proporcionado o puede descargar la hoja de ruta a un archivo de Excel para realizar análisis adicionales. Para cada característica, la hoja de ruta proporciona una breve descripción, junto con la fecha de lanzamiento prevista.

En el [blog de Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog), puede obtener información sobre las prácticas recomendadas, las tendencias y las novedades de las actualizaciones de productos de Teams. Es posible que se anuncien actualizaciones de características principales a teams aquí. También puede suscribirse al blog a través de una fuente RSS. Después, puede agregar [la fuente RSS](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog) directamente a un canal de Teams, de modo que todas las noticias importantes se entreguen directamente dentro de Teams.

Todas las características que se publican se documentan en las [notas de la versión de Microsoft Teams](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de).
Aquí encontrarás una lista de características que se lanzaron para dispositivos de escritorio, Web y móviles. El mismo conjunto de notas de la versión también está disponible en **la pestaña novedades de la** [ayuda](get-help-in-microsoft-teams.md).

Familiarícese con los recursos disponibles y asegúrese de que asigna los propietarios correspondientes para que supervisen el cambio.

### <a name="planning-for-change"></a>Planificación de cambio

Ahora que tiene constancia de los próximos cambios en el servicio de Teams, el siguiente paso es preparar y planificar según corresponda. Evalúe cada cambio para determinar qué cambios requieren comunicación a los usuarios, campañas de concienciación, aprendizaje para equipos de soporte técnico o usuarios, o campañas de evaluación y adopción de características. Esta es la función principal de un equipo de administración de cambios de su organización. A continuación se muestra una colección de tablas de ejemplo que pueden ayudarle a planear el cambio.

#### <a name="feature-cloud-recording-release-date-january-2018"></a>Característica: grabación en la nube (fecha de publicación: 2018 de enero)

**Seguimiento general**

| Cambiar preparación | Statu | Notas y próximos pasos | Propietario |
|---|---|---|---|
| Revisión legal | Llena | Esta característica es un requisito previo para entablar al equipo de aprendizaje. | Equipo del proyecto |

**Administración de cambios técnicos**

| Cambiar preparación | Statu | Notas y próximos pasos | Propietario |
|---|---|---|---|
| ES necesario realizar cambios | Sí | El administrador debe habilitar la grabación solo para usuarios identificados. | Equipo de soporte técnico |
| Preparación técnica completada | Sí | | Equipo de soporte técnico |
| | | | |

**Administración de cambios de usuario**

| Cambiar preparación | Statu | Notas y próximos pasos | Propietario |
|---|---|---|---|
| Impacto en el usuario | Bajo | | |
| Disponibilidad del usuario obligatoria | Sí | | |
| Comunicaciones listas | No | El correo electrónico de comunicación ha sido borrado: pendiente de revisión. | Equipo de comunicaciones |
| Preparación de la formación | Sí | El aprendizaje aprovechará el video de Microsoft existente. | Equipo de aprendizaje |

**Pista de estado**

| Cambiar preparación | Statu | Notas y próximos pasos | Propietario |
|---|---|---|---|
| Estado de la liberación | en curso | Pendiente de revisión por parte del Patrocinador Ejecutivo. | Equipo de administración de cambios |
| Liberar el cierre | | | |
| Fecha de lanzamiento | | | |

Para obtener más información sobre la planeación de la administración de cambios con Teams, vea [crear una estrategia de administración de cambios para Microsoft Teams](change-management-strategy.md).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas diarias/semanales/mensuales/según sea necesario

| Actividad| Descripción| Cadencia publicación| Equipo asignado |
|---|---|---|---|
| Supervisar el cambio| Supervisar los próximos cambios en el servicio de Microsoft Teams.| Cada día||
| Planificación de cambio| Evalúe y planifique las nuevas características y capacidades, entre las que se incluyen los planes de comunicación, las campañas de concienciación y el aprendizaje.| Según sea necesario ||
| Preparación del usuario| Realice campañas de comunicación, conocimiento o aprendizaje de destino para asegurarse de que los usuarios estén listos para el próximo cambio.| Según sea necesario ||
| Compatibilidad de equipo | Realice campañas de comunicación, conciencia o aprendizaje de destino para asegurarse de que el equipo de soporte técnico esté listo. Los equipos de soporte técnico pueden incluir el equipo de "guante blanca", el servicio de asistencia al usuario, el nivel 2 o el nivel 3, los partners externos, etc. | Según sea necesario ||

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>Evaluar el uso de Teams

Después de comenzar el piloto inicial, es fundamental establecer un ritmo regular para medir el uso real de los equipos. Esto permite a su organización obtener información sobre cómo se alinea el uso real con el uso que predictó durante la fase de previsión. Aunque esta sección se centra en el uso de equipos, debe formar parte de un esfuerzo más amplio para medir y evaluar el uso general de Microsoft 365 u Office 365.

La revisión del uso frecuente en la implementación le da la oportunidad de:

- Validar si los usuarios están usando Teams.

- Identifique posibles desafíos de adopción antes de que creen problemas críticos en toda la organización.

- Comprender si existen discrepancias entre los requisitos de fase de previsión y el uso real.

Si el uso no es lo que espera, puede deberse a un problema de implementación o el plan de adopción no se está ejecutando correctamente o hay algún otro problema. Según el motivo real que haya detrás del uso reducido, el administrador de servicios debe colaborar con los equipos relacionados para ayudar a eliminar las barreras de uso.

### <a name="measuring-usage-with-the-microsoft-365-admin-center"></a>Medir el uso con el centro de administración de Microsoft 365

Los datos de uso de Teams están disponibles en el panel de informes. Los datos de uso de Teams se pueden encontrar en tres informes diferentes. El primer informe proporciona una vista de producto cruzado de cómo los usuarios se comunican y colaboran con los diversos servicios de Microsoft 365 u Office 365. Este informe se puede encontrar aquí: [informes de Microsoft 365 en el centro de administración: usuarios activos](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

Los otros dos informes son específicos de Teams y proporcionan más información sobre el uso de equipos desde una perspectiva de usuario y dispositivo. Ambos informes se pueden encontrar aquí:

[Informe de uso de dispositivos de Microsoft Teams](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-device-usage-917b3e1d-203e-4439-8539-634e80196687)

[Informe de actividad de usuario de Microsoft Teams](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-user-activity-07f67fc4-c0a4-4d3f-ad20-f40c7f6db524)

#### <a name="required-permissions"></a>Permisos necesarios

Es posible obtener acceso a los informes de uso en el centro de administración mediante personas a las que se les haya asignado una función de **administrador global** o un rol de administrador específico de producto (**Administrador de Exchange**, **Administrador de Skype empresarial**, administrador de **SharePoint**).

Además, la función **lector de informes** está disponible para los usuarios que necesiten acceder a los informes, pero no realizar las tareas que requieran permisos de nivel de administrador. Puede asignar este rol para proporcionar informes de uso a cualquier persona que sea parte interesada, supervisar y conducir la adopción. Para obtener más información sobre las diferentes funciones disponibles, consulte los [roles de administrador de Microsoft 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="assessing-usage"></a>Evaluar el uso

Después de usar el panel de informes para medir el uso, es importante comparar el uso medido con cualquier indicador de éxito clave (KSIs) que definió durante la fase de Previsión del proyecto. Puede definir una KSI que se puede definir como uso activo, o una que esté vinculada indirectamente al uso activo.

Es importante identificar las variaciones entre el uso real y el planeado antes de reanudar el despliegue en otros sitios o usuarios. Probablemente identificará aprendizajes organizacionales como parte de esta actividad que puede aprovechar para asegurarse de que el próximo lote de sitios o usuarios no tenga los mismos problemas.

En primer lugar, determine si se trata de un problema técnico o de adopción. Empiece por investigar los elementos siguientes, por orden, para determinar dónde está el problema.

1. Valida la calidad al realizar una [revisión de la calidad de la experiencia](upgrade-monitor-quality.md).

2. Trabaje con el equipo de asistencia al usuario para comprobar que no hay problemas técnicos de tendencias que impidan que los usuarios tengan acceso o utilicen el servicio. Si existen tendencias de problemas, use la sección [solución de problemas de extremos](#endpoint-troubleshooting) , más adelante en este artículo, para intentar resolver el problema antes de que se pueda usar el soporte técnico.

3. Trabaje con el equipo de formación y adopción para recopilar comentarios directos de los usuarios (consulte [evaluar la opinión del usuario](#assess-user-sentiment) más adelante en este artículo), así como comprobar la eficacia de las actividades de conciencia e adopción.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas diarias/semanales/mensuales/según sea necesario

| Actividad | Descripción | Cadencia publicación | Equipo asignado |
|---|---|---|---|
| Medir el uso (fase de habilitación) | Mida y evalúe el uso de los equipos a medida que se incorporan sitios durante la fase de habilitación. Solucione problemas de uso según sea necesario. | Cada semana | |
| Medir el uso | Mida y evalúe el uso de Teams en la fase de valor de unidad (una vez completada la implementación). Solucione problemas de uso según sea necesario. | Quincenal | |
| (fase de valor de unidad) | | | |
| Plan de adopción de actualizaciones | Actualice su plan de adopción según cómo se compare el uso medido con los objetivos de planeación. | Según sea necesario | |

### <a name="references"></a>Referencias

[Acerca del centro de administración de Microsoft 365](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Informes de actividades en el centro de administración de Microsoft 365](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>Evaluar la opinión del usuario

Comprender la opinión del usuario puede actuar como un indicador clave para dar forma al éxito de la implementación de Teams. Los comentarios de los usuarios pueden impulsar cambios en la organización; Esto puede incluir cambios en los planes de comunicación, programas de formación o la manera en que ofrezca soporte técnico a los usuarios.

Es importante obtener comentarios pronto y continuar con la evaluación de la opinión del usuario durante todo el ciclo de vida del proyecto y más allá. Use las siguientes instrucciones para determinar el intervalo en el que su organización buscará comentarios:

- **Principio del proyecto**: al evaluar las sentimientos del usuario al principio del proyecto, puede obtener una vista previa de cómo los usuarios sienten la experiencia de su equipo.

- **Después de los hitos principales**: mediante la recopilación de comentarios durante el ciclo de vida del proyecto, puede medir la opinión del usuario de manera continua y realizar los cambios necesarios. Esto es especialmente útil después de hitos importantes.

- **Conclusión del proyecto**: evaluar la opinión del usuario al final de un proyecto le dirá lo bien que ha hecho y dónde debe realizarse el trabajo, y le permitirá comparar los resultados con la encuesta anterior.

- **Continuo**: continúe para medir la opinión del usuario indefinidamente. Los cambios en la opinión del usuario pueden deberse a cambios en el entorno de su organización o a cambios en el servicio de Teams. Al evaluar la opinión del usuario a intervalos regulares, puede comprender el rendimiento de los equipos de administración de servicios y el modo en que la organización responde a los cambios en el servicio de Teams.

La opinión del usuario puede evaluarse a través de muchos métodos diferentes. Esto puede incluir encuestas de correo electrónico, entrevistas a personas o a teléfonos, o simplemente crear un canal de comentarios en Teams o Yammer. Para obtener más información, vea [procedimientos recomendados para los métodos de comentarios de los usuarios en Microsoft Teams](best-practices-feedback.md).

También puede usar un enfoque industrywide para evaluar el valor de los usuarios denominados puntuación de promotor de red (NPS), que se describe en la sección siguiente.

### <a name="nps"></a>NPS

La puntuación de Promoter de red (NPS) es una métrica de fidelidad de cliente de industrywide y un buen enfoque para evaluar la opinión del usuario. NPS se puede calcular formulando dos preguntas: "¿Qué probabilidades hay de que recomiendes equipos a un colega?", seguido de la pregunta de forma libre, "¿por qué?"

NPS es un índice comprendido entre-100 y 100 que mide la disposición de un cliente para recomendar un producto o servicio de una empresa. NPS se basa en una encuesta anónima que se envía a los usuarios por correo electrónico u otros medios electrónicos. NPS mide la lealtad entre un proveedor y un consumidor. Se compone de una sola pregunta, que pide a los usuarios que clasifiquen su experiencia de 1 a 10, con la opción de proporcionar comentarios adicionales. A continuación, los usuarios se clasifican según las siguientes clasificaciones:

- 9 o 10 son promocionales: entusiastas de la lealtad, que promocionarán tu servicio y cargarán otros.

- 7 o 8 son pasivas: satisfecho, no entusiasta, vulnerable a otro servicio u oferta.

- De 1 a 6 son elementos interactivos: clientes insatisfechos que pueden dañar tu servicio e impedir el crecimiento.

![Un diagrama que muestra la escala de NPS](media/operate-my-service-image2.png "Este diagrama muestra la escala de NPS. Muestra que las clasificaciones de 0 a 6 son elementos interactivos, entre 7 y 8, que son pasivas y de 9 a 10 son promocionales.")

Aunque la cantidad básica de NPS es útil, obtendrá el máximo valor de analizar los comentarios de usuario. Le ayudarán a comprender por qué el usuario recomendaría (o no) equipos a otras personas. Estos comentarios pueden proporcionar valiosos comentarios para ayudar al equipo de administración de servicios o proyectos a comprender los ajustes necesarios para proporcionar un servicio de calidad.

Para proporcionar encuestas de NPS a su organización, puede aprovechar su herramienta favorita de investigación en línea.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas diarias/semanales/mensuales/según sea necesario

| Actividad | Descripción | Cadencia publicación | Equipo asignado |
|---|---|---|---|
| Evaluar la opinión del usuario | Capture y evalúe la opinión de los usuarios mediante encuestas o entrevistas, o a través de un canal de comentarios en Teams o Yammer. | Según sea necesario | |
| Planes de adopción de actualizaciones | Impulsar el cambio de su organización en función de los comentarios de los usuarios; Esto puede incluir cambios en los planes de comunicación, programas de formación o la manera en que ofrezca soporte técnico a los usuarios. | Según sea necesario | |

### <a name="references"></a>Referencias

[Puntuación neta Promoter](https://en.wikipedia.org/wiki/Net_Promoter)

[Uso de Yammer para recopilar comentarios](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[Procedimientos recomendados para los comentarios de los usuarios](best-practices-feedback.md)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>Administrar la calidad de la red

Muchos de los principales elementos de planeación van a optimizar, ajustar el tamaño y remediar la infraestructura de red para garantizar una ruta eficaz y de alta calidad al servicio de Microsoft Teams. Las tareas y los requisitos de planificación se cubren en nuestra guía de [preparación de redes](prepare-network.md) . Las redes suelen evolucionar a lo largo del tiempo debido a actualizaciones, expansión u otros requisitos empresariales. Es importante que tenga en cuenta los requisitos de los equipos de las actividades de planificación de red.

Aunque el planeamiento de redes es un aspecto fundamental de una implementación de equipos, es igualmente importante garantizar que la red siga siendo saludable y se mantenga al día, en función de los cambios en los requisitos técnicos o de negocio.

Para garantizar el estado de la red, es necesario realizar una serie de actividades de operaciones a intervalos regulares.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas diarias/semanales/mensuales/según sea necesario

| Actividad | Descripción | Cadencia publicación | Equipo asignado |
|---|---|---|---|
| Supervisar el IPs y las direcciones URL de Microsoft 365 u Office 365 | Supervise los cambios realizados en las [direcciones URL y los intervalos de direcciones IP de Office 365](https://aka.ms/o365ips) con la [fuente RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) proporcionada e inicie una solicitud de cambio en los grupos de red correspondientes. | Cada día | |
| Actualizar la red según los cambios realizados en los protocolos IP y URL de Microsoft 365 u Office 365 | Realice actualizaciones de los componentes de red aplicables (firewalls, servidores proxy, VPN, firewalls del cliente, etc.) para reflejar los cambios en las [direcciones URL y los intervalos de direcciones IP de Office 365](https://aka.ms/o365ips). | Según sea necesario | |
| Proporcionar datos de compilación | Proporcione información actualizada sobre la subred al experto en calidad (o a las partes interesadas relevantes) para asegurarse de que las [definiciones del edificio del CQD](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) se mantienen actualizadas. | Según sea necesario | |
| Implementar el cambio | Implemente cambios en la red para admitir los requisitos técnicos y empresariales de cambiar de equipo. Los elementos de la red pueden incluir:<ul><li>Firewalls</li><li>VPN</li><li>Redes cableadas y Wi-Fi</li><li>Conectividad a Internet y ExpressRoute</li><li>DNS</li></ul> | Según sea necesario | |
| Supervisión e informes de red | Supervise la red de principio a fin para la disponibilidad, la utilización y las tendencias de capacidad con las herramientas de administración de redes de terceros existentes y las capacidades de creación de informes disponibles en los proveedores de red. Use datos de tendencia para planear la capacidad de la red. | Diariamente, semanalmente, mensualmente | |
| Planificación de la capacidad | Colabore con los propietarios del servicio de Teams para comprender los cambios de requisitos técnicos y de negocio que podrían conducir cambios de capacidad adicionales.  | Según sea necesario | |
| Solución de problemas y corrección de redes | Ayudar a los equipos de asistencia al usuario, a los propietarios de servicios y a los participantes clave para solucionar y corregir problemas relacionados con la conectividad, la confiabilidad o la calidad de Teams. Los elementos de la red pueden incluir:<ul><li>Firewalls</li><li>VPN</li><li>Redes cableadas y Wi-Fi</li><li>Conectividad a Internet y ExpressRoute</li><li>DNS</li></ul> | Según sea necesario | |
| Pruebas de recuperación ante desastres y alta disponibilidad | Realice pruebas normales de alta disponibilidad y de recuperación ante desastres en la infraestructura de red para asegurarse de que cumple con los objetivos de nivel de servicio (SLOs) establecidos o los contratos de nivel de servicio (SLA) del servicio de Teams. | Cada mes | |

### <a name="references"></a>Referencias

[Direcciones URL e intervalos de direcciones IP de Office 365](https://aka.ms/o365ips)

[Generando esquema de datos](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>Evaluar y garantizar la calidad

Todas las organizaciones necesitan un grupo o una persona para que sea responsable de la calidad. Es, sin duda, el rol más importante en la administración de servicios. El rol de preexperto de calidad se asigna a una persona o grupo que es apasionado de la experiencia de los usuarios.
y requiere las habilidades adecuadas para identificar tendencias del entorno y el respaldo necesario para poder trabajar con otros equipos y dirigir las correcciones que corresponda. El mejor candidato para ser experto en calidad es normalmente el propietario del servicio al cliente. Según el tamaño y la complejidad de la organización, puede ser cualquier persona o grupo con pasión para garantizar una experiencia de usuario de alta calidad.

El defensor de calidad aprovecha las herramientas existentes y los procesos documentados, como el panel de calidad de llamadas (CQD) y la guía de revisión de la calidad de la experiencia, para supervisar la experiencia del usuario, identificar tendencias de calidad y controlar la corrección cuando sea necesario.
El experto en calidad debe trabajar con los equipos respectivos para impulsar acciones de corrección e informar a un Comité de dirección sobre el progreso y los problemas pendientes.

La [Guía de revisión de la calidad de la experiencia](https://aka.ms/qerguide) incluye actividades que evalúan y proporcionan instrucciones de corrección en áreas clave que tienen el mayor impacto en la mejora de la experiencia del usuario. Las instrucciones proporcionadas en la guía de revisión de la experiencia de calidad se centran en usar el CQD online como la herramienta principal para informar e investigar cada área, centrándose en el audio para maximizar la adopción y el impacto. Las optimizaciones que se realicen en la red para mejorar la experiencia de audio se traducirán directamente en mejoras de las de vídeo y escritorio compartido.

Le recomendamos encarecidamente que se nominar a la calidad del experto en el primer momento. Después de ser nombrados, deben empezar a familiarizarse con el contenido de la guía de revisión de la calidad de la experiencia y los materiales de aprendizaje relacionados.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas diarias/semanales/mensuales/según sea necesario

| Actividad | Descripción | Cadencia publicación | Equipo asignado |
|---|---|---|---|
| Nominar y experto en calidad del tren | Nombra y entrena un campeón de calidad. | Según sea necesario | |
| Realizar revisiones de la calidad de la experiencia (QERs) | Realice una QER para identificar tendencias en cuanto a la calidad y la confiabilidad, la revisión con los destinos definidos y el informe a los accionistas clave de la organización. | Mensual (semanal durante implementaciones) | |
| Corrección de unidades | Coordine los esfuerzos de corrección en toda la organización en función de las comprobaciones y las averiguaciones de QER. | Según sea necesario | |
| Actualizar datos de compilación en el CQD | Actualice o agregue nuevas definiciones de creación en el CQD cuando se realicen cambios en la red (consulte [cargar información de creación](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)). | Según sea necesario | |
| Rellenar el rol de calidad de experto | Responsabilidad end-to-end de la calidad de la organización. Esto incluye:<ul><li>Asegúrate de que el QER se lleve a cabo de forma periódica.</li><li>Denunciar a participantes clave en el estado de la calidad.</li><li>Asegúrese de que las definiciones de datos de compilación estén actualizadas.</li><li>Coordine los esfuerzos de corrección en toda la organización para asegurarse de que los usuarios tengan una experiencia de alta calidad con Teams.</li></ul> | Cada día | |

### <a name="references"></a>Referencias

[Cargar información de compilación](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)

[Guía de revisión de la experiencia de calidad](https://aka.ms/qerguide)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>Administrar puntos de conexión

Los puntos de conexión de Microsoft Teams se pueden definir como cualquier PC, Mac, tableta o teléfono móvil (o cualquier otro dispositivo) que ejecute el cliente de Teams. El *extremo* de término no solo engloba el dispositivo en sí, sino que se conecta al dispositivo (por ejemplo, mediante el micrófono o el altavoz incorporado del dispositivo, Earbuds o un auricular con micrófono optimizado). Después de su implementación, no se deben olvidar los puntos de conexión. Los puntos de conexión de Teams requieren mantenimiento y cuidado continuos. En las siguientes secciones se describen las áreas específicas en las que centrarse.

### <a name="endpoint-requirements"></a>Requisitos de los extremos

Uno de los beneficios clave de Teams es que el cliente se mantiene actualizado automáticamente. Los clientes de PC y Mac se actualizan mediante un proceso en segundo plano que comprueba si hay nuevas compilaciones y descarga el cliente nuevo cuando la aplicación está inactiva. Las aplicaciones móviles de Teams se mantienen actualizadas a través de sus respectivos almacenes de aplicaciones.

El cliente de Teams tiene los requisitos mínimos en cuanto a la plataforma de software subyacente. Estos requisitos pueden cambiar con el tiempo y, por lo tanto, es importante que los supervise para realizar cambios. Por ejemplo, el cliente de Teams tiene una versión mínima de iOS. Si el cliente usa un explorador de Internet, el explorador también tiene que mantenerse actualizado. Puede encontrar una lista de las plataformas compatibles en [obtener clientes para Microsoft Teams](get-clients.md).

### <a name="endpoint-firewalls"></a>Firewalls para los puntos de conexión

Los firewalls del cliente pueden repercutir de forma significativa en la experiencia de usuario.
Los firewalls del cliente pueden afectar a la calidad de las llamadas e incluso impedir que se establezca una llamada. Una vez que se hayan configurado las exclusiones apropiadas en el firewall del cliente, deberán estar actualizadas en función de la información de las [direcciones URL y los intervalos de direcciones IP de Office 365](https://aka.ms/o365ips). Su proveedor de terceros tendrá instrucciones específicas sobre cómo actualizar las exclusiones.

### <a name="wi-fi-drivers"></a>Controladores Wi-Fi

Los drivers Wi-Fi pueden ser problemáticos. Como ejemplo, un controlador puede tener comportamientos de itinerancia muy agresivos entre puntos de acceso que pueden inducir un cambio de punto de acceso innecesario, lo que lleva a una mala calidad de las llamadas. Es posible que se descubra un controlador Wi-Fi de mala ejecución a través de la revisión de la calidad de la experiencia (consulte la guía de revisión de la [calidad de la experiencia](https://aka.ms/qerguide) para obtener más detalles). Es esencial implementar un proceso basado en la calidad que supervise los nuevos drivers de Wi-Fi y garantice que estén probados antes de implementarlos en la población general de usuarios.

### <a name="endpoint-management"></a>Administración de extremos

Debe haber disponible y mantenido un catálogo de puntos de conexión y dispositivos de interfaz compatibles (como auriculares con micrófono). Este catálogo incluirá una lista de los dispositivos aprobados que fueron seleccionados y validados como parte de las fases de enVision e integrados. Normalmente, se seleccionan dispositivos específicos para cada tipo de rol de su organización para satisfacer las necesidades de los atributos de ese rol. Todos los puntos de conexión tienen un ciclo de vida y es necesario administrar las directivas de contratos de proveedores, la garantía, la sustitución, la distribución y la reparación asociadas con estos dispositivos.

### <a name="endpoint-troubleshooting"></a>Solución de problemas de extremos

Incluso si ha seguido las instrucciones anteriores, los usuarios de su organización seguirán teniendo problemas con Teams. Aunque es posible que el problema no esté relacionado con el extremo, los síntomas del problema generalmente se exponen a través del cliente para el usuario. Las siguientes instrucciones pretenden proporcionar los pasos generales que puede tomar para resolver el problema; no se trata de una guía completa para la solución de problemas. Los pasos se proporcionan en un orden específico, pero no tienen que seguirse explícitamente y es posible que no sean aplicables, en función de la naturaleza del problema.

1. **Validar el estado del servicio:** El problema que un usuario puede estar experimentando puede estar relacionado con un evento que afecta negativamente al servicio de Teams o a sus servicios dependientes. Como primer paso, le recomendamos que confirme que no hay ningún problema de servicio activo. Consulte [Cómo comprobar el estado del servicio de Microsoft 365](https://docs.microsoft.com/office365/enterprise/view-service-health). Recuerde comprobar el estado de los servicios dependientes (por ejemplo, Exchange, SharePoint, OneDrive para la empresa). La supervisión del estado del servicio se describe con más detalle en la sección anterior, [supervisar el estado del servicio](#monitor-service-health).

2. **Validar la Conectividad del cliente:** Los problemas de conectividad causan problemas de inicio de sesión o de funcionalidad en Teams. Recomendamos (especialmente para sitios o ubicaciones nuevos) que valide la conectividad con el servicio. Asegúrese de seguir la siguiente guía de [direcciones URL e intervalos de direcciones IP de Office 365](https://aka.ms/o365ips) para cada sitio. Puede aprovechar la [herramienta de evaluación de redes de Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para realizar una prueba de conectividad con el fin de validar que los puertos multimedia se han abierto correctamente para las capacidades de Teams. Los pasos detallados sobre cómo ejecutar las pruebas de conectividad se proporcionan en la guía de [preparación de red](prepare-network.md) .

3. **Compruebe la lista de problemas conocidos:** Consulte la [solución de problemas de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams) para determinar si el usuario se ha visto afectado negativamente por uno de estos problemas. Siga las soluciones proporcionadas (si hay alguna) para resolver el problema.

4. **Visite la comunidad de Microsoft Teams:** La [comunidad de Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams) ofrece espacios dedicados para los equipos. La comunidad de Teams proporciona una lista de discusión, entradas de blog y anuncios centrados en los equipos. Puede publicar una pregunta o buscar discusiones anteriores para obtener soluciones a su problema.

5. **Póngase en contacto con el soporte técnico de Microsoft:** Puede ponerse en contacto con el soporte técnico de Microsoft para problemas con Teams online o por teléfono. Para obtener más información, consulte [ponerse en contacto con el soporte técnico para productos empresariales](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json). Para los clientes de Premier, las solicitudes de asistencia pueden iniciarse siguiendo las instrucciones de [ponerse en contacto con el soporte técnico de Microsoft Teams (clientes de Premier)](https://support.microsoft.com/premier/contacts).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas diarias/semanales/mensuales/según sea necesario

| Actividad | Descripción | Cadencia publicación | Equipo asignado |
|---|---|---|---|
| Requisitos de los extremos | Asegúrese de que el punto de conexión de Teams siga cumpliendo todos los requisitos de software para Teams que aparecen en [obtener clientes para Microsoft Teams](get-clients.md). | Cada mes | |
| Firewalls para los puntos de conexión | Mantenga las exclusiones apropiadas en el Firewall de extremo en función de la información de las [direcciones URL y los intervalos de direcciones IP de Office 365](https://aka.ms/o365ips). Su proveedor de terceros tendrá una orientación específica sobre cómo mantener las exclusiones. Suscribirse a la [fuente RSS](https://support.office.com/o365ip/rss) para recibir notificaciones automáticas de los cambios. | Según sea necesario | |
| Controladores Wi-Fi | Pruebe y actualice los drivers Wi-Fi en su PC. Valide los resultados con el CQD ([Guía de revisión de la calidad de la experiencia](https://aka.ms/qerguide)). | Según sea necesario | |
| Administración de extremos | Mantenga el catálogo de los puntos de conexión y los dispositivos de interfaz compatibles (como auriculares con micrófono). Administrar contratos de proveedores, la garantía, la distribución, la sustitución y las directivas de reparación. | Cada mes | |
| Solución de problemas de extremos | Las tareas de solución de problemas pueden incluir la comprobación de la conectividad, la consulta de la lista de problemas conocidos, la recopilación de registros, el análisis y el escalamiento al soporte técnico de Microsoft o a proveedores de terceros. | Según sea necesario | |

### <a name="references"></a>Referencias

[Direcciones URL e intervalos de direcciones IP de Office 365](https://aka.ms/o365ips)

[Obtener clientes para Microsoft Teams](get-clients.md)

[Comunidad de Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Solución de problemas de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

[Comprobar el estado del servicio para Microsoft Teams](service-health.md)

[Contactar al soporte técnico para productos empresariales: ayuda para administradores](https://support.office.com/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

[Ponerse en contacto con el soporte Premier](https://support.microsoft.com/premier/contacts)

[Vídeo sobre la solución de problemas de Teams](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>Administrar Teams

Después de implementar el servicio Microsoft Teams, tendrá que realizar varias actividades relacionadas con su administración. Las actividades abarcan desde administrar el servicio y los usuarios individuales hasta la planificación de la capacidad y los números de teléfono y licencias. En las secciones siguientes se describen algunas de estas tareas de administración comunes.

### <a name="service-administration"></a>Administración de servicios

El servicio de Teams tiene varias opciones de configuración que se pueden configurar para todo el inquilino.
Los cambios realizados en la configuración de inquilino afectan a todos los usuarios que se han habilitado para los equipos. Para obtener una lista detallada de esta configuración, vea [administrar la configuración de Microsoft Teams para su organización](enable-features-office-365.md).

### <a name="user-administration"></a>Administración de usuarios

Para admitir usuarios, una organización puede requerir cualquier cantidad de tareas relacionadas: las tareas específicas varían de una organización a la siguiente. En última instancia, estas tareas deben ser administradas por un equipo de soporte al que se le hayan asignado estos deberes operativos. Las siguientes tareas suelen necesitarse para admitir usuarios en Teams.

#### <a name="general-tasks"></a>Tareas generales

[Administrar el acceso de los usuarios a Microsoft Teams](user-access.md)

### <a name="team-creation-optional"></a>Creación de equipos (opcional)

De forma predeterminada, todos los usuarios con un buzón en Exchange Online tienen permisos para crear grupos de Microsoft 365 y, por lo tanto, un equipo en Microsoft Teams. Si desea tener un control más estricto y [restringir la creación de nuevos equipos](assign-roles-permissions.md#permissions-to-create-teams) (y, por tanto, la creación de nuevos grupos de Microsoft 365), puede delegar la creación de grupos y derechos de administración a un conjunto de administradores. Si su organización desea seguir esta opción, consulte el proceso descrito en este artículo para permitir que los usuarios envíen solicitudes procesadas por un equipo asignado.

<!--ENDOFSECTION-->

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas diarias/semanales/mensuales/según sea necesario

| Actividad | Descripción | Cadencia publicación | Equipo asignado |
|---|---|---|---|
| Administración de servicios | Administración de la configuración de Teams para todo el inquilino. | Según sea necesario | |
| Administración de usuarios | Administración de la configuración y las licencias basadas en usuarios en Teams. | Según sea necesario | |
| Administración de licencias | Planee las necesidades actuales y futuras de las licencias de usuario y basadas en el consumo (planes de llamadas y créditos de comunicación) aprovechando el [Informe de uso de RTC](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) y el informe de grupos de [minutos RTC](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) . | Cada semana | |
| Administración de números de teléfono | Administra los números de teléfono disponibles para el crecimiento futuro y ajusta los niveles de inventario para satisfacer las necesidades de tu organización. | Cada semana | |
| Creación de equipos (opcional) | Revise y procese las solicitudes de creación del equipo. | Según sea necesario | |

<!--ENDOFSECTION-->
