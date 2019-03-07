---
title: Operaciones para equipos de Microsoft | Administración de servicios | Calidad
author: turgayo
ms.author: turgayo
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Las tareas y actividades necesarias para la administración de servicio de los equipos, incluidos supervisar el estado del servicio y evaluar y garantizar la calidad de la red y uso
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 42df00ed52b62d70d8c9ea734291d77e0ba038ad
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460503"
---
![Fases de la actualización viaje, con especial hincapié en la fase de excelencia operativa] (media/upgrade-banner-op-excellence.png "Fases de la actualización viaje, con especial hincapié en la fase de excelencia operativa")

En este artículo forma parte de la fase de excelencia operativa de su viaje de actualización, que comienza en cuanto se haya completado la actualización de Skype para la empresa a los equipos.

# <a name="operate-your-service"></a>Usar el servicio

En este artículo se proporciona una visión general de los requisitos para el funcionamiento correctamente los equipos de la organización después de haber actualizado. Por funciona correctamente los servicios de los equipos, puede estar seguro de que si va a proporcionar una experiencia confiable de alta calidad para su organización.

## <a name="introduction-to-the-operations-guide"></a>Introducción a la guía de operaciones

La Guía de operaciones le ofrece una visión general de todas las tareas y actividades necesarias como parte de la función de administración de servicios para Microsoft Teams.

La administración de servicios es un tema muy amplio que cubre las operaciones del día a día del servicio de Microsoft Teams una vez que se ha implementado y habilitado para los usuarios. El servicio de Teams abarca Microsoft Office 365 y los componentes de infraestructura que se implementan en local (por ejemplo, las redes).

Seguramente, el concepto de "administración de servicios" no es nuevo para la mayoría de organizaciones. Es posible que ya se ha implementado los procesos y las tareas que están asociadas con servicios existentes. Dicho esto, probablemente puede aumentar sus procesos actuales al planear la administración del servicio de hoy en día admitir los equipos en el futuro.

Administración del servicio abarca todas las actividades y procesos implicados en la administración de equipos de un extremo a otro. Tal y como se ha mencionado anteriormente, algunos componentes de administración de servicios, la infraestructura que se compone del propio servicio de Office 365: son responsabilidad de Microsoft, mientras que usted, el cliente, es responsables de los usuarios para administrar los diversos aspectos de los equipos de la red y los extremos que proporciona.

Las tareas y actividades de esta guía se agrupan en ocho categorías como se muestra en el siguiente diagrama. Cada una de estas categorías se expandirá tras en las secciones siguientes.

![Un diagrama que muestra una lista de categorías de tareas y actividades que comprende las tareas de administración de servicios para los equipos. El diagrama también describe que administración de servicios es en gran medida una tarea de cliente.] (media/operate-my-service-image1.png "Un diagrama que muestra una lista de categorías de tareas y actividades que comprende las tareas de administración de servicios para los equipos. El diagrama también describe que administración de servicios es en gran medida una tarea de cliente.")

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Puntos de decisión</td><td><ul><li>Decidir cómo se implementarán las operaciones para los equipos.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Pasos siguientes</td><td><ul><li>Revise a la Guía de operaciones en su totalidad.</li><li>Implementar una estrategia de operaciones que se alinea con los objetivos de la organización para ofrecer la calidad y la fiabilidad de cargas de trabajo de los equipos.</li><li>Revise a la Guía de revisión de calidad de experiencia.</li><li> Implementar una estrategia de operaciones para llevar a cabo con regularidad revisiones de calidad de experiencia para asegurarse de que la implementación de los equipos está funcionando a su capacidad máxima.</li></ul></td></tr>
</table>

### <a name="operational-role-mapping"></a>Asignación de roles operativos

La planeación que llevó a cabo para operaciones durante la fase de previsión es fundamental, ya que las actividades de operaciones comenzar cuando se habilitan la primera que los usuarios pilotos. Esta guía enumera las actividades y tareas que se deben realizar de forma diaria, semanal, mensual o como sea necesario para mantener una implementación de los equipos de alta calidad. Esta guía proporciona los conocimientos y las instrucciones sobre cómo realizar estas tareas y actividades críticas.

Es un componente esencial de una implementación correcta para asegurarse de que el diseño que realice en la fase de previsión incluye determinar quién será responsable de realizar actividades específicas. Una vez que ha podido averiguar qué tareas y actividades se aplican a la implementación, deben se entiende y seguido de los grupos o las personas que les asigne.

Cada equipo que se identifica debe revisar y está de acuerdo en las tareas y responsabilidades identificadas e iniciar la preparación del. Esto podría incluir formación y preparación, que proporciona actualizaciones para el plan de personal o asegurarse de que los proveedores externos están listos para entregar.

Las actividades y funciones definidas en esta guía deben ser válidas en la mayoría de los escenarios, pero cada implementación de los equipos es único. por lo tanto, puede usar a esta guía como punto de partida para personalizar las actividades y funciones de forma predeterminada para satisfacer sus necesidades.

Asegúrese de que cada equipo responsable tiene una buena comprensión de las actividades que son necesarios para ejecutar el servicio. Es muy importante que cada equipo acepta y cierra una sesión en su responsabilidad en la organización antes de que comience la primera prueba piloto.

Una vez un contrato, deben iniciar los equipos correspondientes que controle sus roles.

<table>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Pasos siguientes</td>
<td><ul><li>Use este documento para facilitar el ejercicio de la asignación de rol operativas.</li><li>Cumplir con los equipos de soporte técnico respectivos para asignar nombres a cada elemento de la lista de actividades necesarias.</li><li>Obtener la aceptación o cierre la sesión en los roles asignados.</li><li>Asegúrese de que los equipos correspondientes tengan la formación adecuada, preparación y recursos para llevar a cabo las actividades necesarias de ellos.</li></ul></td></table>

### <a name="teams-service-dependencies"></a>Dependencias de servicio de los equipos

Microsoft Teams reúne tecnologías a través de Office 365 para proporcionar un concentrador de trabajo en equipo. Algunos ejemplos son:

- Azure Active Directory (AD Azure) proporciona servicios de autenticación y autorización para los equipos.

- Exchange Online proporciona características avanzadas como retención legal y exhibición de documentos electrónicos.

- SharePoint Online proporciona la capacidad de compartir archivos en canales y OneDrive para la empresa proporciona un mecanismo para uso compartido de archivos dentro de un chat privado.

Las organizaciones también pueden aprovechar las inversiones existentes en infraestructura local. Por ejemplo, cuentas de Active Directory local existentes pueden utilizarse para la autenticación mediante el aprovechamiento de Azure Connect de AD. Ciertas versiones de Exchange Server se pueden usar en lugar de Exchange Online.

Estas tecnologías se reúnan para proporcionar un conjunto de aplicaciones de comunicaciones enriquecidas, colaboración e inteligente para los usuarios. Esta estrecha integración es una ventaja clave de los equipos, pero también impulsa un requisito para la administración de servicio a través de estas tecnologías.

Esta guía trata las áreas clave de enfoque para administrar el servicio de los equipos. Probablemente, tener planes de servicio de administración en lugar de las tecnologías de apoyo que depende de los equipos. Si no, necesitará establecer planes de administración de servicio adecuados para esos componentes de la tecnología (tanto local y en línea) así como. Esto le ayudará a asegurarse de que los usuarios disfrutan de una experiencia confiable de alta calidad con los equipos.

#### <a name="references"></a>Referencias

[Información general sobre Microsoft Teams](teams-overview.md)

[Interacción entre Exchange y Microsoft Teams](exchange-teams-interact.md)

[Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams](sharepoint-onedrive-interact.md)

[Microsoft Teams y Skype para la interoperabilidad y coexistencia de negocio](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>Actividades de la Guía de operaciones

En las secciones siguientes proporcionan una visión general de las actividades que son necesarios para que funcione correctamente el servicio de Microsoft Teams. Incluyen referencia a herramientas, información contextual y contenido adicional para ayudarle a comprender la actividad y ayudar en las iniciativas de preparación.

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>Estado del servicio de Monitor

Es importante comprender el estado general del servicio Microsoft Teams por lo que puede alerta forma proactiva otras personas de la organización de cualquier evento que afecta al servicio. Tal y como se ha descrito anteriormente, los equipos depende de otros servicios de Office 365, como Azure Active Directory, Exchange Online, SharePoint Online y OneDrive para la empresa. Por este motivo, es igualmente importante que supervisar el estado de los servicios dependientes.

Incorporar esta actividad en el proceso de administración de incidentes para informar de forma proactiva a los usuarios, el departamento de soporte técnico y los equipos de operaciones para preparar tratar las extensiones de usuario.

Las secciones siguientes describen las herramientas que puede aprovechar para supervisar la de [incidentes de servicio](https://technet.microsoft.com/library/office-365-service-health.aspx#Anchor_1) que afectan al servicio de los equipos. Un resumen de las ventajas de cada herramienta, y cuándo se debe usar cada uno de ellos se incluye en la siguiente tabla.

| Herramienta de supervisión | Ventajas | Cuándo se debe usar |
|---|---|---|
| Portal de Office 365 | Disponible desde cualquier dispositivo con un explorador compatible. | Se utiliza cuando no es necesario notificaciones en tiempo real. |
| Aplicación de administración de Office 365 | Proporciona notificaciones de inserción a su dispositivo móvil. | Se utiliza cuando se necesita recibir una notificación de incidentes del servicio mientras está fuera de la oficina. |
| Microsoft System Center | Integración con Microsoft System Center. | Se utiliza cuando necesita capacidades avanzadas de supervisión y soporte técnico de notificación. |
| API de comunicación de servicio de Office 365 | Acceso mediante programación para el mantenimiento del servicio Office 365. | Se utiliza cuando necesita integración con una herramienta de supervisión de terceros o si desea crear su propia solución. |

> [!NOTE]
> Sólo los individuos que tienen asignados la función de **administrador global** o **Administrador de servicio** pueden ver el estado del servicio.

### <a name="monitoring-with-the-office-365-portal"></a>Supervisión con el portal de Office 365

El [portal de Office 365](https://portal.office.com/) proporciona un [panel de estado de servicio](https://portal.office.com/adminportal/home#/servicehealth) en la que puede ver el estado actual del servicio de los equipos además de los servicios dependientes.

### <a name="monitoring-with-the-mobile-app"></a>Supervisión con la aplicación móvil

La aplicación de administración de Office 365 está disponible en Apple iOS, Android y Windows (PC y mobile). La aplicación proporciona a los administradores del servicio información sobre el estado del servicio y los próximos cambios. La aplicación es compatible con las notificaciones de inserción que le pueden alertar casi inmediatamente después de que se ha registrado un documento informativo. Esto le ayudará a mantenerse al día en el estado, mantenimiento y cualquier próximos cambios en el servicio. La compatibilidad de notificación permite que la herramienta de supervisión recomendada para los administradores. Para obtener más información, vea:

[Aplicación móvil de administración de Office 365](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[Descargar la aplicación móvil de administración de Office 365](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>Supervisión con Microsoft System Center

Microsoft System Center es una plataforma de administración integrada que ayuda a administrar centros de datos, los dispositivos de cliente y híbrida en la nube entornos de TI. Los administradores de Office 365 que usar System Center ahora tienen la opción para importar el módulo de administración de Office 365, que les permite ver todas las comunicaciones de servicio dentro de Operations Manager en System Center. Uso de esta herramienta le proporciona acceso al estado de los servicios suscritos, los incidentes de servicio activos y resueltos y sus comunicaciones de centro de mensajes (próximos cambios). Para obtener más información, consulte la siguiente [entrada de blog](https://blogs.office.com/2014/07/29/new-office-365-admin-tools/?eu=true).

Si se aprovecha la System Center para supervisar el estado de servicio de los equipos (y servicios dependientes), puede personalizar aún más el paquete de administración para la alerta o notificar a determinados grupos o las personas que se hayan identificado ante los incidentes.
Estos grupos pueden incluir los propietarios de servicio, asistencia, los grupos de soporte de segundo nivel y tercer nivel y los administradores de incidentes en la organización.

### <a name="monitoring-for-advanced-scenarios"></a>Supervisión para escenarios avanzados

Puede supervisar el estado del servicio y los próximos cambios mediante el aprovechamiento de la API de comunicaciones de Office 365 Service para obtener acceso a los cambios y el estado del servicio Office 365 mediante programación. Utilice esta API para crear su propia supervisión herramienta o conectar sus herramientas de supervisión existentes para las comunicaciones de servicio de Office 365, potencialmente simplificación de cómo supervisar el entorno. Para obtener más información, vea [Office 365 para desarrolladores de la empresa](https://msdn.microsoft.com/library/jj984343(v=office.15).aspx).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas de diario o semanal o mensual/según sea necesario

| Actividad | Descripción | Cadencia | Equipo asignado |
|---|---|---|---|
| Estado del servicio de Monitor | Forma proactiva, supervise el estado del servicio de Microsoft Teams, (y servicios dependientes) mediante el uso de las herramientas disponibles. Incluyen servicios dependientes: Exchange Online, SharePoint Online, OneDrive para la empresa, Azure Active Directory. | En tiempo real | |
| Notificación de incidentes | Notificar a los participantes internos de eventos que afectan al servicio de los equipos. Los participantes internos pueden incluir usuarios, asistencia y los administradores de incidente. | Según sea necesario | |

### <a name="references"></a>Referencias

[Cómo comprobar el estado del servicio Office 365](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[Comprobar el estado del servicio para Microsoft Teams](service-health.md)

[La continuidad y el estado del servicio](https://technet.microsoft.com/library/office-365-service-health.aspx)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>Administrar cambios en la organización

Microsoft Teams es un servicio basado en la nube. Con el incluye la capacidad de proporcionar las nuevas características y funcionalidad con rapidez. Proporciona una innovación continuada de ofrecer una ventaja obvia a las organizaciones, pero estos cambios deben administrarse de forma adecuada dentro de la organización para evitar la resistencia del usuario o escalaciones a su departamento de soporte técnico.

Las actualizaciones de los equipos se implementan automáticamente a los usuarios. Los usuarios siempre tendrá las últimas cliente y las características disponibles en el servicio de los equipos. No es posible administrar la implantación de las actualizaciones de los equipos a los usuarios, por lo tanto, es sumamente importante administrar el cambio a través de programas de comunicación, aprendizaje y adopción eficaces. Si los usuarios conozcan el cambio, informado acerca de las ventajas y habilitadas para sacar provecho de las nuevas capacidades&mdash;podrá adaptarse más rápidamente y el cambio de bienvenida.

### <a name="monitoring-for-change"></a>Supervisión de cambio

El primer paso para la administración de cambios está supervisando los cambios que se ha planeado para los equipos. La mejor fuente para la supervisión de estos cambios es la [Guía básica de 365 de Microsoft](https://www.microsoft.com/microsoft-365/roadmap), que se enumeran las características que están actualmente en desarrollo, que se implantan a los clientes, o se han iniciado completamente. Puede buscar para características específicas de los equipos mediante el filtro proporcionado, o puede descargar la guía básica para un archivo de Excel para su análisis posterior. Para cada característica, la guía ofrece una descripción breve, junto con la fecha de lanzamiento anticipado.

En el [blog de equipos de Microsoft](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog), puede obtener información sobre procedimientos recomendados, las tendencias y noticias sobre las actualizaciones de los equipos del producto. Esperar buscar actualizaciones características principales de los equipos se anuncian aquí. También puede suscribirse al blog de a través de una fuente RSS. A continuación, puede agregar [la fuente RSS](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog) directamente en un canal de los equipos, por lo que todas las noticias importantes se entregan directamente dentro de los equipos.

Todas las características que se liberan se documentan en las [Notas de la versión para equipos de Microsoft](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de).
Aquí encontrará una lista de características que se han publicado para escritorio, web y dispositivos móviles. El mismo conjunto de notas de la versión también están disponibles en la ficha **Cuáles son las novedades** en la [Ayuda](get-help-in-microsoft-teams.md).

Familiarizarse con los recursos disponibles y asegúrese de que se asignan a supervisar para cambiar los propietarios de aplicables.

### <a name="planning-for-change"></a>Planificación de cambios

Ahora que se ha de tener en cuenta próximos cambios en el servicio de los equipos, el siguiente paso es preparar y planear en consecuencia. Evaluar cada cambio para determinar qué cambios requieren la comunicación a los usuarios, campañas de sensibilización, formación para profesionales de equipos de soporte técnico o a los usuarios o las campañas de evaluación y adopción de característica. Esto es la función principal de un equipo de administración de cambios en la organización. A continuación es una colección de tablas que le ayudarán a planeación para cambiar de ejemplo.

#### <a name="feature-cloud-recording-release-date-january-2018"></a>Característica: En la nube grabación (fecha de publicación: enero de 2018)

**Pista general**

| Preparación de cambio | Estado | Los pasos de notas y siguiente | Propietario |
|---|---|---|---|
| Revisión legal | Completado | Esta característica es un requisito previo para el equipo de recursos de aprendizaje de incorporación. | Equipo del proyecto |

**Administración de cambios técnicos**

| Preparación de cambio | Estado | Los pasos de notas y siguiente | Propietario |
|---|---|---|---|
| Cambios de TI necesarios | Sí | Administrador necesita habilitar grabación identificados sólo para los usuarios. | Equipo de soporte técnico |
| Preparación técnica completa | Sí | | Equipo de soporte técnico |
| | | | |

**Administración de cambio de usuario**

| Preparación de cambio | Estado | Los pasos de notas y siguiente | Propietario |
|---|---|---|---|
| Impacto de usuario | Bajo | | |
| Preparación del usuario requerido | Sí | | |
| Comunicaciones listas | No | Correo electrónico de comunicación haya sido redactada — pendientes de revisión. | Equipo de comunicaciones |
| Recursos de aprendizaje listo | Sí | Recursos de aprendizaje aprovechará vídeo de Microsoft existente. | Equipo de formación |

**Seguimiento de estado**

| Preparación de cambio | Estado | Los pasos de notas y siguiente | Propietario |
|---|---|---|---|
| Estado de publicación | en curso | Revisión pendiente por el patrocinador ejecutivo. | Equipo de administración de cambios |
| Cierre la sesión de la versión | | | |
| Fecha de lanzamiento | | | |

Para obtener más información acerca de la planeación de la administración de cambio con los equipos, vea [crear una estrategia de administración de cambios para los equipos de Microsoft](change-management-strategy.md).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas de diario o semanal o mensual/según sea necesario

| Actividad| Descripción| Cadencia| Equipo asignado |
|---|---|---|---|
| Monitor de cambio| Supervisar las próximos cambios al servicio Microsoft Teams.| Cada día||
| Planificación de cambios| Evaluación y planeación de las nuevas características y capacidades, incluidos los planes de comunicación, campañas de sensibilización y formación.| Según sea necesario ||
| Preparación del usuario| Lleve a cabo comunicación dirigida, conocimiento del producto o las campañas de formación para asegurarse de que los usuarios están preparados para el cambio próximo.| Según sea necesario ||
| Preparación del equipo de soporte técnico | Lleve a cabo comunicación dirigida, conocimiento del producto o las campañas de formación para asegurarse de que el equipo de soporte técnico está listo. Equipos de soporte técnico pueden incluir el equipo "guante blanco", asistencia, nivel 2 o nivel 3 soporte técnico, socios externos y así sucesivamente. | Según sea necesario ||

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>Evaluar el uso de los equipos

Después de que comience la prueba piloto inicial, es muy importante establecer una cadencia regular para medir el uso de los equipos real. Esto permite que la organización para obtener entendimiento uso real se alinea con el uso de previstos durante la fase de previsión. Aunque en esta sección se centra en el uso de los equipos, debe ser parte de un esfuerzo más amplio para medir y evaluación de Office 365 uso general.

Revisión de uso con frecuencia antes de la implementación le ofrece la oportunidad de:

- Validar si los usuarios utilizan los equipos.

- Identificar los posibles retos de adopción antes de crear problemas críticos en toda la organización.

- Comprender si hay discrepancias entre los requisitos de la fase de previsión y el uso real.

Si uso no es lo que espera, puede deberse a un problema de implementación o el plan de adopción no se va a ejecutar correctamente, o en cualquier otro problema. Según el motivo real detrás del uso bajo, el administrador del servicio debe colaborar con los equipos relacionados para ayudar a eliminar las barreras de uso.

### <a name="measuring-usage-with-the-office-365-admin-center"></a>Medir el uso con el centro de administración de Office 365

Los datos de uso de los equipos están disponibles en el panel de informes. Datos de uso de los equipos pueden encontrarse en tres diferentes informes. El primer informe proporciona una vista de producto cruzado de cómo los usuarios comunicarán y colaboran mediante el uso de los distintos servicios de Office 365. Este informe se puede encontrar aquí: [informe de usuarios activos de Office 365](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

Los otros dos informes son específicos de los equipos, y que proporcionan más detalles sobre el uso de los equipos desde una perspectiva de dispositivo y el usuario. Ambos informes pueden encontrarse aquí:

[Informe de uso de dispositivos de Microsoft Teams](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-device-usage-917b3e1d-203e-4439-8539-634e80196687)

[Informe de actividad de usuario de Microsoft Teams](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-user-activity-07f67fc4-c0a4-4d3f-ad20-f40c7f6db524)

#### <a name="required-permissions"></a>Permisos necesarios

Se pueden tener acceso a los informes de uso en el centro de administración por personas que tengan asignadas una función de **Administrador Global** o un rol de administrador de producto específico (**Administrador de Exchange**, **Skype para Administrador empresarial**, **SharePoint Administrador de**).

Además, la función de **lector de informes** está disponible para los usuarios que necesitan tener acceso a los informes, pero no realizan las tareas que requieren permisos de nivel de administrador. Asignar este rol para proporcionar los informes de uso para cualquier persona que es un participante, para la adopción de monitor y la unidad. Para obtener más información acerca de las distintas funciones disponibles, vea [los roles de administrador acerca de Office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="assessing-usage"></a>Evaluación de uso

Después de que se ha utilizado el panel de informes para medir el uso, es importante comparar el uso medido contra cualquier indicadores clave para el éxito (KSIs) que ha definido durante la fase de previsión del proyecto. Puede definir un KSI que puede definirse como uso activo o uno que indirectamente está vinculada para uso activo.

Es importante identificar las variaciones entre uso planeado y real antes de reanudar la implantación a sitios adicionales o a los usuarios. Es probable que podrá identificar conocimientos organizativas como parte de esta actividad que puede aprovechar para asegurarse de que el siguiente lote de sitios o los usuarios no tiene el mismos problemas.

En primer lugar, determinar con precisión si se trata de un problema técnico o adopción. Empezar por investigar los elementos a continuación, en orden, para determinar dónde está el problema.

1. Validar la calidad mediante la realización de una [Revisión de calidad de experiencia](upgrade-monitor-quality.md).

2. Trabajar con el equipo del departamento de soporte técnico para comprobar que no hay ningún problema técnico tendencia impide a los usuarios tener acceso o uso del servicio. Si existen tendencias de problemas, use la sección [solución de problemas de extremo](#endpoint-troubleshooting) más adelante en este artículo para intentar resolver el problema antes de contratación de soporte técnico.

3. Trabajar con el equipo de adopción y aprendizaje para recopilar los comentarios de los usuarios (consulte la [opinión de los clientes de Assess usuario](#assess-user-sentiment) más adelante en este artículo) así como para comprobar la eficacia de las actividades de sensibilización y adopción.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas de diario o semanal o mensual/según sea necesario

| Actividad | Descripción | Cadencia | Equipo asignado |
|---|---|---|---|
| Uso de medida (fase habilitación) | Medir y evaluar el uso de los equipos, como sitios siguen siendo onboarded durante la fase de habilitación. Solución de problemas de uso según sea necesario. | Cada semana | |
| Uso de medida | Medir y evaluar el uso de los equipos en la fase de valor de unidad (después de que se ha completado la implementación). Solución de problemas de uso según sea necesario. | Bisemanales | |
| (fase de valor de unidad) | | | |
| Actualizar el plan de adopción | Actualización en función de su plan de adopción de uso medido cómo se compara con los objetivos de planeación. | Según sea necesario | |

### <a name="references"></a>Referencias

[Acerca del centro de administración de Office 365](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Informes de actividades en el Centro de administración de Office 365](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>Evaluar la opinión de los clientes de usuario

Descripción de la opinión de los clientes de usuario puede actuar como un indicador clave de cómo determinar el éxito de la implementación de los equipos que ofrecen. Los comentarios del usuario pueden controlar los cambios en la organización; Esto puede incluir los cambios realizados en los planes de comunicación, programas de formación o la forma en que ofrecer soporte técnico a los usuarios.

Es importante obtener comentarios pronto y continuar con la opinión de los clientes de usuario a lo largo del ciclo de vida del proyecto y más allá de evaluación. Use las directrices siguientes para determinar el intervalo en el que la organización buscará los comentarios:

- **A partir del proyecto**: evaluando la opinión de los clientes de usuario al principio del proyecto, puede obtener una vista anticipada en cómo se sienten a los usuarios sobre su experiencia de los equipos.

- **Después de hitos principales**: mediante la recopilación de comentarios a lo largo del ciclo de vida del proyecto, puede evaluar la opinión de los clientes de usuario de forma continua y realice los cambios según sea necesario. Esto es especialmente útil después de hitos principales.

- **Conclusión de Project**: evaluar la opinión de los clientes de usuario al final de un proyecto le indicará cómo también ha realizado y donde trabajo aún debe realizarse y permiten comparar los resultados de la encuesta anterior.

- **En curso**: continuar medir la opinión de los clientes de usuario indefinidamente. Es posible que los cambios en la opinión de los clientes de usuario debido a los cambios en el entorno de su organización o los cambios realizados en el servicio de los equipos. Por cómo determinar ofrecen la opinión de los clientes de usuario a intervalos regulares, puede comprender grado en la realización de los equipos de administración de servicio y cómo la organización está respondiendo a los cambios en el servicio de los equipos.

Puede ser evaluado la opinión de los clientes de usuario a través de muchos métodos diferentes. Estos pueden incluir encuestas de correo electrónico, en persona o entrevistas de estilo de teléfono o simplemente crear un canal de comentarios en los equipos o Yammer. Para obtener más información, vea [procedimientos recomendados para los métodos de comentarios del usuario en los equipos de Microsoft](best-practices-feedback.md).

También puede utilizar un enfoque de formación para evaluar la opinión de usuario llamado promotor neto puntuación (NPS), que se describe en la sección siguiente.

### <a name="nps"></a>NPS

Puntuación promotor neto (NPS) es una métrica de fidelidad del cliente formación y un buen método para usar para evaluar la opinión de los clientes de usuario. NPS se puede calcular mediante dos preguntas: "¿con qué probabilidad va a recomendar los equipos a un compañero?", seguido de la forma libre pregunta, "¿por qué?"

NPS es un índice comprendido entre -100 y 100 que mide su deseo de un cliente a recomendar una compañía producto o servicio. NPS se basa en una encuesta anónima que se entrega a los usuarios a través de correo electrónico u otros medios electrónicos. NPS mide la fidelidad entre un proveedor y un consumidor. Consta de una pregunta, que pide a los usuarios clasificar su experiencia comprendido entre 1 y 10, con la opción de proporcionar comentarios adicionales. Los usuarios, a continuación, se clasifican en función de las clasificaciones siguientes:

- 9 o 10 son activadores: leales entusiastas que será promover su servicio y que otros usuarios de combustible.

- 7 u 8 son pasivo: satisfecho pero no entusiasta, vulnerables a otro servicio o una oferta.

- De 1 a 6 son detractores: insatisfacción en los clientes que puede dañar su servicio y obstaculizar crecimiento.

![Este diagrama muestra la escala NPS. Muestra que las clasificaciones de 0 a 6 son detractores, son pasivos 7 a 8 y 9 y 10 son activadores.] (media/operate-my-service-image2.png "Este diagrama muestra la escala NPS. Muestra que las clasificaciones de 0 a 6 son detractores, son pasivos 7 a 8 y 9 y 10 son activadores.")

Aunque el número NPS base es útil, obtendrá el máximo valor desde el análisis de comentarios del usuario. Le ayudarán a comprender por qué el usuario sería (o no) recomienda los equipos a otros usuarios. Estos comentarios pueden proporcionar valiosa información para ayudar a los proyectos o equipos de administración de servicio comprender los ajustes necesarios para proporcionar una calidad de servicio.

Para proporcionar las encuestas NPS para su organización, puede aprovechar la herramienta de favoritos encuesta en línea.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Diario o semanal o mensual o como sea necesario tareas

| Actividad | Descripción | Cadencia | Equipo asignado |
|---|---|---|---|
| Evaluar la opinión de los clientes de usuario | Captura y evaluar la opinión de los clientes de usuario mediante el uso de encuestas o entrevistas, o a través de un canal de comentarios en los equipos o Yammer. | Según sea necesario | |
| Actualizar los planes de adopción | Cambio de la unidad en la organización en función de los comentarios del usuario; Esto puede incluir los cambios realizados en los planes de comunicación, programas de formación o la forma en que ofrecer soporte técnico a los usuarios. | Según sea necesario | |

### <a name="references"></a>Referencias

[Puntuación promotor NET](https://en.wikipedia.org/wiki/Net_Promoter)

[Uso de Yammer para recopilar comentarios](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[Procedimientos recomendados para los comentarios del usuario](best-practices-feedback.md)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>Administrar la calidad de la red

Muchos elementos de la planeación principales irán a optimizar, determinar el tamaño adecuado y solucionar relativos a la infraestructura de red para garantizar una ruta de acceso de alta calidad y eficaz para el servicio de Microsoft Teams. Se tratan las tareas y los requisitos de planeación en nuestra guía de [preparación de la red](upgrade-prepare-environment-prepare-network.md) . Redes a menudo evolucionan con el tiempo debido a las actualizaciones, la expansión u otros requisitos empresariales. Es importante que se tiene en cuenta los requisitos para los equipos en la red de las actividades de planificación.

Aunque el diseño de la red es un aspecto fundamental de una implementación de los equipos, es igualmente importante garantizar la red permanece en buen estada y se mantiene actual, basándose en los cambiantes requisitos técnicos o empresariales.

Para garantizar el mantenimiento de la red, un número de actividades de las operaciones debe realizarse a intervalos regulares.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas de diario o semanal o mensual/según sea necesario

| Actividad | Descripción | Cadencia | Equipo asignado |
|---|---|---|---|
| Supervisión de Office 365 IP y direcciones URL | Supervisar los cambios en [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://aka.ms/o365ips) mediante el uso de la [fuente RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) proporcionada e iniciar una solicitud de cambio a los grupos de redes correspondientes. | Cada día | |
| Actualización de la red en función de los cambios realizados en Office 365 IP y direcciones URL | Realizar actualizaciones en los componentes de red aplicables (firewalls, servidores proxy, las redes privadas virtuales, firewalls de cliente y así sucesivamente) para reflejar los cambios realizados en [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://aka.ms/o365ips). | Según sea necesario | |
| Proporcionar datos de creación | Proporcionar información de subred actualizadas al Campeón de calidad (o partes interesadas relevantes) para asegurarse de que la [creación de definiciones de CQD](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) se mantienen actualizados. | Según sea necesario | |
| Implementar cambio | Implementar los cambios en la red a requisitos técnicos y empresariales cambiantes de los equipos de soporte técnico. Pueden incluir elementos de red:<ul><li>Firewalls</li><li>Redes privadas virtuales</li><li>Con cable y redes Wi-Fi</li><li>La conectividad a Internet y ExpressRoute</li><li>DNS</li></ul> | Según sea necesario | |
| Supervisión de la red y creación de informes | Supervisar la red a fin de disponibilidad, la utilización y las tendencias de capacidad utilizando las herramientas de administración de red de terceros existente y capacidades disponibles de los proveedores de redes de reporting. Usar datos de tendencias para la planificación de capacidad de red. | Diariamente, semanalmente, mensualmente | |
| Planificación de la capacidad | Colaborar con los propietarios de servicio de los equipos a comprender los requisitos empresariales y técnicos que es posible que los cambios de la capacidad adicional de unidad de cambio. Sacar provecho de los resultados desde el [Organizador de la red](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) para asegurarse de que suficiente ancho de banda está disponible para Microsoft Teams. | Según sea necesario | |
| Solución de problemas de red y corrección | Prestar asistencia a la asistencia de equipos, los propietarios de servicio y las partes interesadas clave para solucionar problemas y corregir los problemas a relacionados con la conectividad de los equipos, confiabilidad o calidad. Pueden incluir elementos de red:<ul><li>Firewalls</li><li>Redes privadas virtuales</li><li>Con cable y redes Wi-Fi</li><li>La conectividad a Internet y ExpressRoute</li><li>DNS</li></ul> | Según sea necesario | |
| Recuperación ante desastres y pruebas de alta disponibilidad | Lleve a cabo regular alta disponibilidad y recuperación ante desastres pruebas en la infraestructura de red para asegurarse de que cumple los objetivos de nivel de servicio indicada (SLOs) o acuerdos de nivel de servicio (SLA) para el servicio de los equipos. | Cada mes | |

### <a name="references"></a>Referencias

[Planificador de red](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner)

[Direcciones URL e intervalos de direcciones IP de Office 365](https://aka.ms/o365ips)

[Esquema de datos de creación](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>Evaluar y garantizar la calidad

Todas las organizaciones necesitan un individuo o grupo sea responsable de calidad. Es, sin duda, el rol más importante en la administración de servicios. La función de los pesos pesados calidad se asigna a una persona o grupo que es entusiastas acerca de la experiencia de sus usuarios.
y requiere las habilidades adecuadas para identificar tendencias del entorno y el respaldo necesario para poder trabajar con otros equipos y dirigir las correcciones que corresponda. El mejor candidato para ser experto en calidad es normalmente el propietario del servicio al cliente. Según el tamaño y la complejidad de la organización, podría tratarse de cualquier persona o grupo con pasión para garantizar una experiencia de usuario de alta calidad.

El Campeón de calidad aprovecha las herramientas existentes y procesos documentados, como el panel de calidad de llamadas (CQD) y la calidad de experiencia revisión guía, para supervisar la experiencia del usuario, identifican las tendencias de calidad y corrección de la unidad donde sea necesario.
El Campeón de calidad debe trabajar con los equipos respectivos a las acciones de corrección de unidad y el informe a un Comité de dirección sobre el progreso y cualquier problema open.

La [Calidad de experiencia consulte la guía](https://aka.ms/qerguide) incluye las actividades que evaluación y se proporcionan instrucciones de corrección en áreas clave que tienen el mayor impacto sobre cómo mejorar la experiencia del usuario. Las instrucciones proporcionadas en la Guía de revisión de calidad de experiencia se centra en uso CQD en línea como la principal herramienta para notificar e investigar cada área, con un enfoque en audio para maximizar la adopción y el impacto. Las optimizaciones que se realicen en la red para mejorar la experiencia de audio se traducirán directamente en mejoras de las de vídeo y escritorio compartido.

Se recomienda encarecidamente que se nombra al Campeón de calidad desde el principio. Después de que se ha designado, debe comenzar a familiarizarse con el contenido de la Guía de revisión de calidad de experiencia y materiales de formación asociados.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas de diario o semanal o mensual/según sea necesario

| Actividad | Descripción | Cadencia | Equipo asignado |
|---|---|---|---|
| Sea propietaria y formar a champion(s) de calidad | Sea propietaria y formar a un experto de calidad. | Según sea necesario | |
| Realizar la calidad de las revisiones de la experiencia (QERs) | Realizar una QER para identificar las tendencias en la calidad y la confiabilidad, revisar frente a destinos definidos e informar las partes interesadas clave en la organización. | Mensual (semanalmente durante implementaciones) | |
| Unidad de corrección | Coordinar los esfuerzos de corrección en toda la organización basándose en las evaluaciones de QER y los resultados. | Según sea necesario | |
| Actualizar los datos de creación de CQD | Actualizar o agregar nuevas definiciones de creación en CQD cuando se realizan cambios en la red (consulte la [información de creación de carga](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)). | Según sea necesario | |
| La función de la calidad de los pesos de relleno | Responsabilidad de extremo a extremo para la calidad de la organización. Esto incluye:<ul><li>Asegúrese de que el QER se llevan a cabo con regularidad.</li><li>Informe de a las partes interesadas clave en estado de calidad.</li><li>Asegúrese de los datos de creación son las definiciones de hasta la fecha.</li><li>Coordinar los esfuerzos de corrección en toda la organización para garantizar que los usuarios tengan una experiencia de alta calidad con los equipos.</li></ul> | Cada día | |

### <a name="references"></a>Referencias

[Información sobre el Panel de calidad de llamadas](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Academy?SOFTrainings=Leverage%20the%20Investigate%20Media%20Quality%20using%20CQD%20Videos)

[Información de creación de carga](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)

[Calidad de experiencia consulte la Guía](https://aka.ms/qerguide)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>Administrar los extremos

Los extremos de Microsoft Teams pueden definirse como cualquier PC, Mac, Tablet PC o dispositivo móvil (o cualquier otro) que ejecuta al cliente de los equipos. El término *extremo* engloba no sólo el dispositivo propio, pero cómo un usuario se conecta al dispositivo — por ejemplo, mediante el uso de micrófono integrado del dispositivo o altavoces, auriculares o auriculares para optimizada. Después de que estén implementados, no se deben olvidar extremos. Los extremos de los equipos requieren atención continua y mantenimiento. En las secciones siguientes se describen las áreas específicas para centrarse en.

### <a name="endpoint-requirements"></a>Requisitos del extremo

Uno de los beneficios clave de los equipos es que el cliente se mantiene actualizado automáticamente. Los clientes de PC y Mac se actualizan mediante un proceso en segundo plano que comprueba si hay nuevas compilaciones y descarga el cliente nuevo cuando la aplicación está inactiva. Los equipos de aplicaciones móviles se mantienen actuales a través de sus almacenes respectivos de aplicación.

El cliente de los equipos tiene requisitos mínimos en cuanto a la plataforma de software subyacente. Estos requisitos podrían cambiar con el tiempo y, por lo tanto, es importante que las supervise para que los cambios. Por ejemplo, el cliente de los equipos tiene una versión de iOS mínimo. Si el cliente utiliza un explorador de internet, debe mantenerse actual así como el explorador. Una lista de plataformas compatibles puede encontrarse en [obtener los clientes de equipos de Microsoft](get-clients.md).

### <a name="endpoint-firewalls"></a>Firewalls para los puntos de conexión

Los firewalls del cliente pueden repercutir de forma significativa en la experiencia de usuario.
Firewalls de cliente pueden afectar a la calidad de las llamadas e incluso impedir que una llamada desde el que se establezca. Después de que se han configurado las exclusiones adecuadas en el firewall de cliente, que necesitan para mantenerse al día en función de la información de [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://aka.ms/o365ips). Su proveedor de terceros tendrá las instrucciones específicas sobre cómo actualizar las exclusiones.

### <a name="wi-fi-drivers"></a>Controladores Wi-Fi

Controladores de Wi-Fi podrían ser un inconveniente. Por ejemplo, un controlador podría tener muy agresivos comportamientos de movilidad entre puntos de acceso que pueden provocar innecesario-punto de acceso de conmutación, lo que a la calidad de llamadas deficientes. Se puede detectar un controlador Wi-Fi bajo rendimiento a través de una revisión de calidad de experiencia (vea [Calidad de experiencia consulte la guía](https://aka.ms/qerguide) para obtener más detalles). Es esencial para implementar un proceso controlado por la calidad que supervisa nuevos controladores Wi-Fi y se asegura de que probarlos antes de que se implementan en la población general de usuario.

### <a name="endpoint-management"></a>Administración de extremo

Un catálogo de los extremos compatibles y dispositivos de interfaz (por ejemplo, auriculares con micrófono) debería estar disponibles y mantenimiento. Este catálogo incluirá una lista de los dispositivos aprobados que se han seleccionado y validado como parte de las fases de previsión e incorporado. Normalmente, se seleccionan dispositivos específicos para cada tipo de rol de la organización para satisfacer las necesidades de los atributos de dicho rol. Todos los extremos de tengan un ciclo de vida, y debe administrar los contratos de proveedores, garantía, reemplazo, distribución y reparar las directivas asociadas con estos dispositivos.

### <a name="endpoint-troubleshooting"></a>Solución de problemas de extremo

Incluso si ha seguido las instrucciones anteriores, los usuarios de su organización aún es posible que ejecute problemas con los equipos. Aunque no es posible que sea el problema con el propio extremo, los síntomas del problema normalmente se exponen a través del cliente para el usuario. Las siguientes instrucciones está pensada para proporcionar los pasos generales que puede seguir para resolver el problema; no se pretende ser una guía completa sobre la solución de problemas. Los pasos que se proporcionan en un orden concreto, pero no tiene que ser seguido de forma explícita y es posible que no sea aplicables, dependiendo de la naturaleza del problema.

1. **Validar el estado del servicio:** El problema que puede haber un usuario puede estar relacionado con un evento que afecta negativamente al servicio de los equipos o los servicios de itsdependent. Como primer paso, se recomienda que confirme que no hay ningún problema de servicio de active. Consulte [cómo comprobar el estado del servicio Office 365](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0). No olvide comprobar el estado de los servicios dependientes (por ejemplo, Exchange, SharePoint, OneDrive para la empresa). Supervisión de estado del servicio se describe con más detalle en la sección anterior, [el estado del servicio de Monitor](#monitor-service-health).

2. **Validar la conectividad de cliente:** Problemas de conectividad de producen funcionalidad o problemas de inicio de sesión en los equipos. Se recomienda (especialmente para los sitios nuevos o ubicaciones) que valide la conectividad con el servicio. Asegúrese de que se siguen las siguientes instrucciones de [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://aka.ms/o365ips) para cada sitio. Puede sacar provecho de la [Herramienta de evaluación de red de Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para realizar una prueba de conectividad para validar que los puertos de medios se han abierto correctamente para las capacidades de los equipos. Se proporcionan instrucciones detalladas acerca de cómo realizar las pruebas de conectividad en la Guía de [preparación de la red](upgrade-prepare-environment-prepare-network.md) .

3. **Compruebe la lista de problemas conocidos:** Consulte la [lista de problemas conocidos de los equipos](known-issues.md) para determinar si el usuario haya sido afectado negativamente por uno de estos problemas. Siga la solución alternativa proporcionada (si hay alguno) para resolver el problema.

4. **Visite la Comunidad de Microsoft Teams:** La [Comunidad de equipos de Microsoft](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams) ofrece espacios dedicados para los equipos. La Comunidad de equipos proporciona una lista de discusión, entradas de blog y anuncios centrados en los equipos. Puede registrar una pregunta o buscar conversaciones anteriores para soluciones para el problema.

5. **Póngase en contacto con soporte técnico de Microsoft:** Puede ponerse en contacto con Microsoft Support para problemas con los equipos en línea o por teléfono. Para obtener información, vea [contacto admite para los equipos de Microsoft](https://support.office.com/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). Para Premier a los clientes, compatibilidad con las solicitudes se pueden iniciar siguiendo las instrucciones en [póngase en contacto con soporte técnico para Microsoft Teams (Premier a los clientes)](https://support.microsoft.com/premier/contacts).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas de diario o semanal o mensual/según sea necesario

| Actividad | Descripción | Cadencia | Equipo asignado |
|---|---|---|---|
| Requisitos del extremo | Asegúrese de que los equipos de extremo continúa para cumplir todos los requisitos de software para los equipos que aparecen en [obtener los clientes de equipos de Microsoft](get-clients.md). | Cada mes | |
| Firewalls para los puntos de conexión | Mantener las exclusiones adecuadas en el firewall de extremo en función de la información de [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://aka.ms/o365ips). Su proveedor de terceros tendrá las instrucciones específicas sobre cómo mantener las exclusiones. Suscríbase a la [fuente RSS](https://support.office.com/o365ip/rss) para recibir automáticamente una notificación de cambios. | Según sea necesario | |
| Controladores Wi-Fi | Probar y actualizar los controladores de Wi-Fi en su PC. Validar los resultados mediante el uso de CQD ([Guía de revisión de calidad de experiencia](https://aka.ms/qerguide)). | Según sea necesario | |
| Administración de extremo | Mantener el catálogo de los extremos compatibles y dispositivos de interfaz (por ejemplo, auriculares con micrófono). Administrar contratos de proveedores, garantía, distribución, reemplazo y reparar las directivas. | Cada mes | |
| Solución de problemas de extremo | Solución de problemas de tareas puede incluir la comprobación de la conectividad, la lista de problemas conocidos, registro de recopilación, análisis y escalación a Microsoft Support o proveedores de terceros de consultoría. | Según sea necesario | |

### <a name="references"></a>Referencias

[Direcciones URL e intervalos de direcciones IP de Office 365](https://aka.ms/o365ips)

[Obtener clientes para Microsoft Teams](get-clients.md)

[Comunidad de Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Problemas conocidos de Microsoft Teams](known-issues.md)

[Comprobar el estado del servicio para Microsoft Teams](service-health.md)

[Póngase en contacto con el soporte de Office 365 para empresas: ayuda para administradores](https://support.office.com/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

[Soporte ampliado de contacto](https://support.microsoft.com/premier/contacts)

[Solución de problemas de vídeo de los equipos](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>Administración de equipos

Después de que se ha implementado el servicio de Microsoft Teams, debe realizar varias actividades relativas a su administración. El intervalo de las actividades de administración del servicio y los usuarios individuales a la planeación de la capacidad y el aprovisionamiento de licencia y los números telefónicos. En las secciones siguientes se tratan algunas de estas tareas habituales de administración.

### <a name="service-administration"></a>Administración del servicio

El servicio de los equipos tiene varias opciones que se pueden configurar todo el inquilino.
Los cambios realizados en la configuración de inquilino afecta a todos los usuarios que han sido habilitados para los equipos. Para obtener una lista detallada de estas configuraciones, vea [características de administración de equipos de Microsoft en su organización de Office 365](enable-features-office-365.md).

### <a name="user-administration"></a>Administración de usuarios

Para admitir usuarios, una organización puede requerir cualquier número de tareas relacionadas, las tareas específicas varían de una organización a la siguiente. En última instancia, estas tareas deben administrarse por un equipo de soporte técnico que se ha asignado a estas tareas operativas. Las siguientes tareas con frecuencia son necesarios para admitir los usuarios en los equipos.

#### <a name="general-tasks"></a>Tareas generales

[Administrar el acceso de los usuarios a Microsoft Teams](user-access.md)

### <a name="team-creation-optional"></a>Creación del equipo (opcional)

De forma predeterminada, todos los usuarios con un buzón en Exchange Online tienen permisos para crear grupos de Office 365 y, por lo tanto, un equipo en Microsoft Teams. Si desea tener un control más estricto y [restringir la creación de nuevos equipos](assign-roles-permissions.md#permissions-to-create-teams) (y, por tanto, la creación de nuevos grupos de Office 365), puede delegar la creación de grupos y derechos de administración a un conjunto de administradores. Si desea que su organización a decidirse por esta opción, vea el proceso descrito en este artículo para permitir a los usuarios enviar solicitudes que se procesan por un equipo asignados.

<!--ENDOFSECTION-->

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas de diario o semanal o mensual/según sea necesario

| Actividad | Descripción | Cadencia | Equipo asignado |
|---|---|---|---|
| Administración del servicio | Administración de configuración de los equipos de todo el inquilino. | Según sea necesario | |
| Administración de usuarios | Administración de configuración de usuario y concesión de licencias en los equipos. | Según sea necesario | |
| Administración de licencias | Planear las necesidades actuales y futuras para el usuario y basada en el consumo de licencias (planes de llamada y comunicación créditos) al aprovechar el informe [informe de uso de RTC](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) y [grupos de servidores de minutos de RTC](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) . | Cada semana | |
| Administración de números de teléfono | Administrar los números de teléfono disponibles para el crecimiento futuro y ajustar los niveles de inventario para satisfacer las necesidades de su organización. | Cada semana | |
| Creación del equipo (opcional) | Proceso de revisión y las solicitudes de creación del equipo. | Según sea necesario | |

<!--ENDOFSECTION-->
