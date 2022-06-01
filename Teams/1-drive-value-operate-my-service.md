---
title: Guía de operaciones para Microsoft Teams
author: rmw2890
ms.author: Rowille
audience: admin
manager: serdars
ms.date: 06/11/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Tareas y actividades necesarias para Teams administración del servicio, incluida la supervisión del estado del servicio y la evaluación y la garantía de la calidad y el uso de la red.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 614b3a16a5c0d59a63f06d1328c68f42e3497af5
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823425"
---
# <a name="operate-my-service"></a>Ejecutar mis servicios

En este artículo se ofrece información general sobre los requisitos para operar correctamente los servicios de voz en la nube para su organización. Al operar correctamente los servicios de voz en la nube, puede estar seguro de que está proporcionando una experiencia confiable y de alta calidad para su organización.

## <a name="introduction-to-the-operations-guide"></a>Introducción a la guía de operaciones

La Guía de operaciones proporciona información general de todas las tareas y actividades necesarias como parte de la función de administración de servicios para Microsoft Teams.

La administración de servicios es un tema muy amplio que cubre las operaciones del día a día del servicio de Microsoft Teams una vez que se ha implementado y habilitado para los usuarios. El servicio Teams abarca Microsoft 365 o Office 365 y los componentes de infraestructura que se implementan localmente (por ejemplo, redes).

Seguramente, el concepto de "administración de servicios" no es nuevo para la mayoría de organizaciones. Es posible que ya haya implementado procesos y tareas asociados con servicios existentes. Dicho esto, es probable que pueda aumentar sus procesos actuales cuando planee la administración de servicios hoy para admitir Teams en el futuro.

La gestión de servicios abarca todas las actividades y procesos implicados en la administración de Teams de un extremo a otro. Como se ha indicado anteriormente, algunos componentes de la administración de servicios (la infraestructura que comprende el propio servicio Microsoft 365 o Office 365) son responsabilidad de Microsoft, mientras que usted, el cliente, es responsable ante los usuarios de administrar los distintos aspectos de Teams, la red y los puntos de conexión que proporciona.

Las tareas y actividades de esta guía se agrupan en ocho categorías, como se muestra en el siguiente diagrama. Cada una de estas categorías se expandirá en las siguientes secciones.

![Diagrama que muestra una lista de categorías de tareas y actividades.](media/operate-my-service-image1.png "Diagrama que muestra una lista de categorías de tareas y actividades que comprende la administración de servicios para Teams. El diagrama también muestra que la administración de servicios es en gran parte una tarea del cliente.")


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Puntos de decisión</td><td><ul><li>Decida cómo se implementarán las operaciones para Teams.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Pasos siguientes</td><td><ul><li>Revise la Guía de operaciones en su totalidad.</li><li>Implemente una estrategia de operaciones que se alinee con los objetivos de su organización para ofrecer la calidad y confiabilidad de las cargas de trabajo de voz en la nube.</li><li>Revisar [la calidad de la llamada del monitor](monitor-call-quality-qos.md).</li><li> Implemente una estrategia de operaciones para realizar periódicamente revisiones de la calidad de la experiencia para asegurarse de que la implementación de voz en la nube está funcionando con sus capacidades máximas.</li></ul></td></tr>
</table>


### <a name="operational-role-mapping"></a>Asignación de roles operativos

La planificación que ha emprendido para las operaciones durante la fase de visualización es crítica, ya que las actividades de las operaciones comienzan cuando se habilitan los primeros usuarios piloto. En esta guía se enumeran las actividades y tareas que se deben realizar de forma diaria, semanal, mensual o según sea necesario para mantener una implementación de Teams de alta calidad. Esta guía proporciona conocimientos e instrucciones sobre cómo llevar a cabo estas tareas y actividades críticas.

Un componente crucial de una implementación correcta es asegurarse de que la planeación que realice al principio de la fase de visualización incluya determinar quién será responsable de realizar actividades específicas. Una vez que haya descubierto qué tareas y actividades se aplican a la implementación, deben entenderse y seguirse por los grupos o personas que les asigne.

Cada equipo que identifique debe revisar y acordar las tareas y responsabilidades identificadas y comenzar la preparación. Esto puede incluir formación y preparación, proporcionar actualizaciones al plan de personal o asegurarse de que los proveedores externos estén listos para ofrecer.

Las actividades y roles definidos en esta guía deben ser válidos en la mayoría de los escenarios, pero cada Teams implementación es única; por lo tanto, puede usar esta guía como punto de partida para personalizar las actividades y los roles predeterminados para satisfacer sus necesidades.

Asegúrese de que cada equipo responsable tenga una buena comprensión de las actividades necesarias para ejecutar el servicio. Es fundamental que cada equipo acepte y señale su responsabilidad en su organización antes de que comience el primer piloto.

Una vez que se haya alcanzado un acuerdo, los equipos correspondientes deberían comenzar a poner en funcionamiento sus roles.

<table>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Pasos siguientes</td>
<td><ul><li>Utilice este documento para facilitar el ejercicio de asignación de funciones operativas.</li><li>Reúnase con los respectivos equipos de soporte técnico para asignar nombres a cada elemento en la lista de actividades necesarias.</li><li>Obtenga la aceptación o la aprobación de los roles asignados.</li><li>Asegúrese de que los equipos correspondientes tengan la formación, la preparación y los recursos adecuados para completar las actividades necesarias.</li></ul></td></table>

### <a name="teams-service-dependencies"></a>dependencias del servicio Teams

Microsoft Teams reúne tecnologías en Microsoft 365 o Office 365 para proporcionar un centro para el trabajo en equipo. Algunos ejemplos son:

-   Azure Active Directory (Azure AD) proporciona servicios de autenticación y autorización para Teams.

-   Exchange Online proporciona características avanzadas, como la retención legal y el e-discovery.

-   SharePoint Online proporciona la capacidad de compartir archivos en canales y OneDrive para la Empresa proporciona un mecanismo para compartir archivos en un chat privado.

Las organizaciones también pueden aprovechar las inversiones existentes en infraestructura local. Por ejemplo, las cuentas de Active Directory local existentes se pueden usar para la autenticación aprovechando la Conectar de Azure AD. Algunas versiones de Exchange Server pueden usarse en lugar de Exchange Online.

Estas tecnologías se unen para proporcionar un conjunto de comunicaciones enriquecida, colaborativa e inteligente para los usuarios. Esta estrecha integración es un beneficio clave de Teams, pero también impulsa un requisito para la administración de servicios en estas tecnologías.

Esta guía cubre las áreas clave de enfoque para administrar el servicio de Teams. Lo más probable es que tenga planes de administración de servicios para las tecnologías auxiliares de las que Teams depende. Si no es así, deberá establecer planes de administración de servicios adecuados para esos componentes tecnológicos (tanto en local como en línea). Esto ayudará a garantizar que los usuarios disfruten de una experiencia confiable y de alta calidad con Teams.

#### <a name="references"></a>Referencias 

[Información general sobre Microsoft Teams](teams-overview.md)

[Interacción entre Exchange y Microsoft Teams](exchange-teams-interact.md)

[Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams](sharepoint-onedrive-interact.md)

[Microsoft Teams y Skype Empresarial coexistencia e interoperabilidad](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>Actividades de la Guía de operaciones

En las siguientes secciones se ofrece información general de las actividades necesarias para operar correctamente el servicio de Microsoft Teams. Incluyen referencia a herramientas, información contextual y contenido adicional para ayudarle a comprender la actividad y ayudar en las iniciativas de preparación.

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>Supervisar el estado del servicio

Es importante que comprenda el estado general del servicio de Microsoft Teams para poder alertar de forma proactiva a los demás usuarios de su organización de cualquier evento que afecte al servicio. Como se ha descrito anteriormente, Teams depende de otros servicios Microsoft 365 o Office 365, como Azure Active Directory, Exchange Online, SharePoint Online y OneDrive para la Empresa. Por este motivo, es igualmente importante que supervise el estado de los servicios dependientes.

Incorpore esta actividad a su proceso de administración de incidentes para informar de forma proactiva a los usuarios, al departamento de soporte técnico y a los equipos de operaciones para prepararse para controlar las escalaciones de usuarios.

En las siguientes secciones se describen las herramientas que puede usar para supervisar [los incidentes del servicio](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity#Anchor_1) que afectan a la Teams servicio. En la tabla siguiente se incluye un resumen de las ventajas de cada herramienta y cuándo debería usar cada una de ellas.

| Herramienta de supervisión                       | Ventajas                                            | Cuándo usar                                                                                  |
|---------------------------------------|-----------------------------------------------------|----------------------------------------------------------------------------------------------|
| Centro de administración de Microsoft 365                     | Disponible desde cualquier dispositivo con un explorador compatible. | Se usa cuando no necesite notificaciones en tiempo real.                                          |
| aplicación Microsoft 365 o Office 365 Admin                  | Proporciona notificaciones push a su dispositivo móvil.  | Úseelo cuando necesite recibir notificaciones de incidentes de servicio mientras está de viaje.                  |
| Microsoft System Center               | Integración con Microsoft System Center.           | Úsalo cuando necesites funcionalidades avanzadas de supervisión y soporte de notificaciones.                       |
| API de comunicaciones de servicio de Microsoft 365 o Office 365 | Acceso mediante programación al estado del servicio Microsoft 365 o Office 365.   | Se usa cuando necesite integración con una herramienta de supervisión de terceros o desee crear su propia solución. |

> [!NOTE]
> Solo las personas que tienen asignado el rol **de administrador de** **servicios** o administrador global pueden ver el estado del servicio.

### <a name="monitoring-with-the-microsoft-365-admin-center"></a>Supervisión con el Centro de administración de Microsoft 365

La [Centro de administración de Microsoft 365](https://portal.office.com/) proporciona un panel estado del [servicio](https://portal.office.com/adminportal/home#/servicehealth) donde puede ver el estado actual del servicio de Teams además de los servicios dependientes.

### <a name="monitoring-with-the-mobile-app"></a>Supervisión con la aplicación móvil

La aplicación Microsoft 365 o Office 365 Admin está disponible en Apple iOS, Android y Windows (pc y móvil). La aplicación proporciona a los administradores del servicio información sobre el estado del servicio y los próximos cambios. La aplicación admite notificaciones push que pueden alertarle casi inmediatamente después de publicar un aviso. Esto le ayuda a mantenerse al día sobre el estado, el estado y los próximos cambios en el servicio. El soporte de notificaciones lo convierte en la herramienta de supervisión recomendada para los administradores. Para obtener más información, vea:

[aplicación móvil de Office 365 Admin](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[Descargar la aplicación móvil de Office 365 Admin](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>Supervisión con Microsoft System Center

Microsoft System Center es una plataforma de administración integrada que le ayuda a administrar centros de datos, dispositivos cliente y entornos de TI en la nube híbrida. Office 365 los administradores que usan System Center ahora tienen la opción de importar el módulo de administración de Office 365, lo que les permite ver todas las comunicaciones de servicio de Operations Manager en System Center. Esta herramienta le proporciona acceso al estado de los servicios suscritos, a los incidentes de servicio activos y resueltos y a las comunicaciones del Centro de mensajes (próximos cambios). Para obtener más información, consulte la siguiente [entrada de blog](https://blogs.office.com/2014/07/29/new-office-365-admin-tools/?eu=true).

Si aprovecha System Center para supervisar Teams estado del servicio (y los servicios dependientes), puede personalizar aún más el módulo de administración para alertar o notificar a grupos o individuos específicos que se han identificado para reaccionar a incidentes.
Estos grupos pueden incluir propietarios de servicios, departamento de soporte técnico, grupos de soporte técnico de segundo y tercer nivel, y administradores de incidentes de su organización.

### <a name="monitoring-for-advanced-scenarios"></a>Supervisión de escenarios avanzados

Puede supervisar el estado del servicio y los próximos cambios aprovechando la API de comunicaciones de servicio de Office 365 para acceder al estado del servicio y los cambios de Office 365 mediante programación. Use esta API para crear su propia herramienta de supervisión o conectar las herramientas de supervisión existentes para Office 365 comunicaciones del servicio, lo que podría simplificar la manera de supervisar su entorno. Para obtener más información, consulta [Office 365 para desarrolladores de Enterprise](https://developer.microsoft.com/office).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas diarias/semanales/mensuales/según sea necesario

| Actividad               | Descripción                                                                                                                                                                                                               | Cadencia   | Equipo asignado |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Supervisar el estado del servicio | Supervise de forma proactiva Microsoft Teams estado del servicio (y los servicios dependientes) mediante las herramientas disponibles. Entre los servicios dependientes se incluyen: Exchange Online, SharePoint Online, OneDrive para la Empresa Azure Active Directory. | En tiempo real |               |
| Notificación de incidencia  | Notifique a las partes interesadas internas sobre los eventos que afectan al servicio de Teams. Las partes interesadas internas pueden incluir usuarios, departamento de soporte técnico y administradores de incidentes.                                                                          | Según sea necesario |               |

### <a name="references"></a>Referencias 

[Cómo comprobar Office 365 estado del servicio](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[Comprobar el estado del servicio para Microsoft Teams](service-health.md)

[Mantenimiento y continuidad del servicio](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>Administrar el cambio de organización

Microsoft Teams es un servicio basado en la nube. Con eso viene la capacidad de proporcionar nuevas características y funcionalidades a un ritmo rápido. Ofrecer innovación continua proporciona un beneficio obvio a las organizaciones, pero estos cambios deben administrarse adecuadamente dentro de su organización para evitar la resistencia del usuario o escalaciones a su departamento de soporte técnico.

Las actualizaciones de Teams se implementan automáticamente para los usuarios. Los usuarios siempre tendrán el cliente y las características más recientes disponibles en el servicio de Teams. No es posible administrar la implementación de las actualizaciones de Teams a los usuarios, por lo que es muy importante administrar el cambio a través de programas eficaces de comunicación, aprendizaje y adopción. Si los usuarios son conscientes del cambio, tienen conocimiento de las ventajas y están facultados para aprovechar las nuevas capacidades&mdash;, podrán adaptarse más rápidamente y acoger con satisfacción el cambio.

### <a name="monitoring-for-change"></a>Supervisión de cambios

El primer paso en la administración de cambios es supervisar los cambios que se planean para Teams. La mejor fuente para supervisar estos cambios es la [Office 365 Plan](https://products.office.com/business/office-365-roadmap) de desarrollo, que enumera las características que se están desarrollando actualmente, que se están implementando a los clientes o que se han lanzado por completo. Puede buscar características específicas de Teams mediante el filtro proporcionado, o puede descargar la hoja de ruta en un archivo Excel para realizar un análisis más exhaustivo. Para cada característica, el plan de desarrollo proporciona una breve descripción, junto con la fecha de lanzamiento prevista.

En el [blog de Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog), puede obtener información sobre procedimientos recomendados, tendencias y noticias sobre Teams actualizaciones de productos. Espera a encontrar las actualizaciones de características principales que Teams anunciar aquí. También puede suscribirse al blog a través de una fuente RSS. A continuación, puede agregar [la fuente RSS](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog) directamente a un canal de Teams para que todas las noticias importantes se entreguen directamente en Teams.

Todas las características que se publican se documentan en las [Notas de la versión para Microsoft Teams](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de).
Aquí encontrará una lista de las características que se publicaron para el escritorio, la web y los dispositivos móviles. El mismo conjunto de notas de la versión también está disponible en la pestaña **Novedades de** la [Ayuda](get-help-in-microsoft-teams.md).

Familiarícese con los recursos disponibles y asegúrese de asignar propietarios aplicables para supervisar los cambios.

### <a name="planning-for-change"></a>Planificación de cambios

Ahora que ya conoce los próximos cambios en el servicio de Teams, el siguiente paso es preparar y planificar en consecuencia. Evalúe cada cambio para determinar qué cambios requieren comunicación con los usuarios, campañas de concienciación, aprendizaje para equipos de soporte técnico o usuarios, o campañas de adopción y evaluación de características. Este es el rol principal de un equipo de administración de cambios de su organización. A continuación se muestra una colección de tablas de ejemplo que pueden ayudarle a planear el cambio.

#### <a name="feature-cloud-recording-release-date-january-2018"></a>Característica: Grabación en la nube (fecha de lanzamiento: enero de 2018)

**Seguimiento general**

| Cambiar la preparación | Estado   | Notas/pasos siguientes | Propietario |
|----|----|----|-----|
| Revisión legal   | Completado     | Esta característica es un requisito previo para incorporar al equipo de aprendizaje. | Project equipo  |

**Administración de cambios técnicos**

|       Cambiar la preparación       | Estado |                      Notas/pasos siguientes                      |    Propietario     |
|------------------------------|--------|------------------------------------------------------------|--------------|
|     Cambios de TI necesarios      |  Sí   | Administración solo es necesario habilitar la grabación para los usuarios identificados. | Equipo de soporte técnico |
| Preparación técnica completa |  Sí   |                                                            | Equipo de soporte técnico |
|                              |        |                                                            |              |

**Administración de cambios de usuario** 

| Cambiar la preparación | Estado   | Notas/pasos siguientes | Propietario |
|----|----|----|-----|
| Impacto del usuario                  | Bajo                  |                                                                 |                        |
| Preparación necesaria para el usuario      | Sí                  |                                                                 |                        |
| Comunicaciones listas         | No                   | El correo electrónico de comunicación ha sido redactado, pendiente de revisión.            | Equipo de comunicaciones    |
| Aprendizaje listo               | Sí                  | El aprendizaje aprovechará el vídeo de Microsoft existente.                | Equipo de aprendizaje          |

**Seguimiento de estado**

| Cambiar la preparación | Estado   | Notas/pasos siguientes | Propietario |
|----|----|----|-----|
| Estado de lanzamiento               | en curso          | Pendiente de revisión por el patrocinador ejecutivo.               | Equipo de administración de cambios |
| Firma de lanzamiento             |                      |                                                                 |                        |
| Fecha de lanzamiento                 |                      |                                                                 |                        |

Para obtener más información sobre la planeación de la administración de cambios con Teams, vea [Crear una estrategia de administración de cambios para Microsoft Teams](change-management-strategy.md).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas diarias/semanales/mensuales/según sea necesario

| Actividad               | Descripción                                                                                                                                                                                                                | Cadencia   | Equipo asignado |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Supervisar los cambios     | Supervisar los próximos cambios en Microsoft Teams servicio.                                                                                                                                                                   | Cada día     |               |
| Planificación de cambios    | Evalúa y planea nuevas funciones y funcionalidades, incluidos planes de comunicación, campañas de concienciación y formación.                                                                                                     | Según sea necesario |               |
| Preparación del usuario             | Realice campañas de comunicación, concienciación o aprendizaje dirigidas para asegurarse de que los usuarios estén listos para el próximo cambio.                                                                                                        | Según sea necesario |               |
| Disponibilidad del equipo de soporte técnico | Realice campañas específicas de comunicación, conciencia o aprendizaje para asegurarse de que el equipo de soporte está listo. Los equipos de soporte pueden incluir el equipo de "guante blanco", los servicios de asistencia, el soporte técnico de nivel 2 o nivel 3, los socios externos, etc. | Según sea necesario |               |

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>Evaluar el uso de Teams

Después de que comience el piloto inicial, es fundamental establecer una cadencia regular para medir el uso Teams real. Esto permite a su organización obtener información sobre cómo se alinea el uso real con el uso pronosticado durante la fase de visualización. Aunque esta sección se centra en Teams uso, esto debería formar parte de un esfuerzo más amplio para medir y evaluar Office 365 uso en general.

Revisar el uso con frecuencia en las primeras etapas de la implementación le da la oportunidad de:

-   Valide si los usuarios usan Teams.

-   Identifique los posibles desafíos de adopción antes de crear problemas críticos en toda la organización.

-   Comprenda si hay discrepancias entre los requisitos de la fase de visualización y el uso real.

Si el uso no es lo que espera, puede deberse a un problema de implementación, a que el plan de adopción no se está ejecutando correctamente o a algún otro problema. Según el motivo real que hay detrás del bajo uso, el administrador del servicio debe colaborar con los equipos relacionados para ayudar a eliminar las barreras de uso.

### <a name="measuring-usage-with-the-microsoft-365-admin-center"></a>Medición del uso con el Centro de administración de Microsoft 365

Los datos de uso de Teams están disponibles en el panel Informes. Teams datos de uso pueden encontrarse en tres informes diferentes. El primer informe proporciona una vista multiproducto de cómo se comunican y colaboran los usuarios mediante los distintos servicios de Office 365. Este informe puede encontrarse aquí: [Office 365 informe de usuarios activos](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

Los otros dos informes son Teams específicos y proporcionan más detalles sobre el uso de Teams desde la perspectiva del usuario y del dispositivo. Ambos informes pueden encontrarse aquí:

[Informe de uso de dispositivos de Microsoft Teams](/microsoftteams/teams-analytics-and-reports/device-usage-report)

[Informe de actividad de usuario de Microsoft Teams](/microsoftteams/teams-analytics-and-reports/user-activity-report)

#### <a name="required-permissions"></a>Permisos necesarios

Los usuarios a los que se les haya asignado un rol de **Administrador global** o un rol de administrador específico del producto pueden acceder a los informes de uso del centro de administración (**Exchange administrador**, **Skype Empresarial administrador** **SharePoint administrador**).

Además, el rol **de lector Informes** está disponible para los usuarios que requieren acceso a los informes, pero no realizan ninguna tarea que requiera permisos de administrador. Asigne este rol para proporcionar informes de uso a cualquier persona que sea parte interesada, para supervisar e impulsar la adopción. Para obtener más información sobre los distintos roles disponibles, vea [Acerca de Office 365 roles de administrador](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="assessing-usage"></a>Evaluar el uso

Después de usar el panel Informes para medir el uso, es importante comparar el uso medido con cualquier indicador clave de éxito (KSI) que definió durante la fase de visualización del proyecto. Puede definir un KSI que pueda definirse como uso activo o uno que esté indirectamente vinculado al uso activo.

Es importante identificar las variaciones entre el uso real y planeado antes de reanudar la implementación a otros sitios o usuarios. Probablemente identificará los aprendizajes de la organización como parte de esta actividad que puede aprovechar para asegurarse de que el siguiente lote de sitios o usuarios no se encuentre con los mismos problemas.

En primer lugar, identifique si se trata de un problema técnico o de adopción. Para empezar, investigue los elementos siguientes, con el fin de determinar dónde está el problema.

1.  Validar la calidad realizando una Revisión de calidad de la experiencia (consulte [Mejorar y supervisar la calidad de las llamadas para obtener Teams](monitor-call-quality-qos.md) para obtener más detalles).

2.  Trabaje con el equipo del departamento de soporte técnico para comprobar que no hay ningún problema técnico que impida que los usuarios puedan acceder al servicio o usarlo. Si existen tendencias de problemas, use la sección [solución de problemas del punto de conexión](#endpoint-troubleshooting) que aparece más adelante en este artículo para intentar resolver el problema antes de recurrir al soporte técnico.

3.  Trabaje con el equipo de aprendizaje y adopción para recopilar comentarios directos de los usuarios (vea [Evaluar la opinión](#assess-user-sentiment) de los usuarios más adelante en este artículo) y para comprobar la eficacia de las actividades de concienciación y adopción.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas diarias/semanales/mensuales/según sea necesario

| Actividad                         | Descripción                                                                                                                      | Cadencia   | Equipo asignado |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Medir el uso (fase de habilitación) | Mida y evalúe Teams uso a medida que los sitios sigan incorporando durante la fase de habilitación. Solucione los problemas de uso según sea necesario. | Cada semana    |               |
| Medir el uso (fase de valor de unidad)                           | Mida y evalúe el uso de Teams en la fase de valor de unidad (una vez completada la implementación). Solucione los problemas de uso según sea necesario. | Quincenal  |               |
| Actualizar plan de adopción             | Actualice el plan de adopción en función del uso medido en comparación con los objetivos de planificación.                                         | Según sea necesario |               |

### <a name="references"></a>Referencias 

[Acerca de la Centro de administración de Microsoft 365](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Informes de actividad en el Centro de administración de Microsoft 365](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>Evaluar la opinión de los usuarios

Comprender la opinión de los usuarios puede actuar como un indicador clave para medir el éxito de la implementación de Teams. Los comentarios de los usuarios pueden impulsar los cambios en su organización; esto puede incluir cambios en los planes de comunicación, programas de aprendizaje o la forma en que ofrece soporte técnico a los usuarios.

Es importante recibir comentarios de forma anticipada y continuar evaluando la opinión de los usuarios durante todo el ciclo de vida del proyecto y más allá. Use las siguientes instrucciones para determinar el intervalo en el que su organización buscará comentarios:

-   **Comienzo del proyecto**: Al evaluar la opinión de los usuarios al principio del proyecto, puede obtener una vista previa de cómo se sienten los usuarios sobre su experiencia Teams.

-   **Tras hitos importantes**: al recopilar comentarios durante todo el ciclo de vida del proyecto, puede medir la opinión de los usuarios de forma continua y realizar cambios según sea necesario. Esto es especialmente útil después de hitos importantes.

-   **Project conclusión**: evaluar la opinión de los usuarios al final de un proyecto le indicará lo bien que ha hecho y dónde hay que hacer el trabajo, y le permitirá comparar los resultados con la encuesta anterior.

-   **En curso**: Siga miden indefinidamente la opinión de los usuarios. Los cambios en la opinión de los usuarios pueden deberse a cambios en el entorno de su organización o a cambios en el servicio de Teams. Al medir la opinión de los usuarios a intervalos regulares, puede comprender el rendimiento de sus equipos de administración de servicios y cómo responde su organización a los cambios en el servicio Teams.

La opinión de los usuarios se puede evaluar a través de muchos métodos diferentes. Estos pueden incluir encuestas por correo electrónico, entrevistas en persona o por teléfono, o simplemente crear un canal de comentarios en Teams o Yammer. Para obtener más información, vea [Procedimientos recomendados para los métodos de comentarios de los usuarios en Microsoft Teams](best-practices-feedback.md).

También puede usar un enfoque de todo el sector para evaluar la opinión de los usuarios denominada puntuación neta promotor (NPS), que se describe en la siguiente sección.

### <a name="nps"></a>NPS 

Net promoter score (NPS) es una métrica de fidelización de clientes en todo el sector y un buen enfoque para evaluar la opinión de los usuarios. NPS se puede calcular haciendo dos preguntas: "¿Qué probabilidad hay de que recomiendes Teams a un compañero?", seguido de la pregunta de forma libre"¿Por qué?"

NPS es un índice, comprendido entre -100 y 100, que mide la disposición de un cliente de recomendar el producto o servicio de una empresa. NPS se basa en una encuesta anónima que se entrega a los usuarios a través del correo electrónico u otros medios electrónicos. NPS mide la fidelidad entre un proveedor y un consumidor. Consta de una sola pregunta, que pide a los usuarios valorar su experiencia de 1 a 10, con la opción de proporcionar comentarios adicionales. Los usuarios se clasifican en función de las siguientes clasificaciones:

-   9 o 10 son promotores: entusiastas leales que promoverán su servicio y alimentarán a otros.

-   7 u 8 son pasivos: satisfechos pero nohusiastic, vulnerables a otro servicio u oferta.

-   Del 1 al 6 son detractores: clientes infelices que pueden dañar su servicio y obstaculizar el crecimiento.

![Diagrama que muestra la escala NPS.](media/operate-my-service-image2.png "En este diagrama se muestra la escala NPS. Muestra que los rankings del 0 al 6 son detractores, 7 a 8 son pasivos, y 9 a 10 son promotores.")

Aunque el número base NPS es útil, obtendrá el máximo valor del análisis de comentarios de los usuarios. Le ayudarán a comprender por qué el usuario recomienda (o no) Teams a otros usuarios. Estos comentarios pueden proporcionar comentarios valiosos para ayudar a los equipos de administración de proyectos o servicios a comprender los ajustes necesarios para proporcionar un servicio de calidad.

Para proporcionar encuestas NPS a tu organización, puedes aprovechar tu herramienta de encuestas en línea favorita.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas diarias/semanales/mensuales/según sea necesario

| Actividad              | Descripción                                                                                                                                                                         | Cadencia   | Equipo asignado |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Evaluar la opinión de los usuarios | Capture y evalúe la opinión de los usuarios mediante encuestas o entrevistas, o a través de un canal de comentarios en Teams o Yammer.                                                                 | Según sea necesario |               |
| Actualizar planes de adopción | Realizar cambios en la organización en función de los comentarios de los usuarios; esto puede incluir cambios en sus planes de comunicación, programas de aprendizaje o la forma en que ofrece soporte técnico a los usuarios. | Según sea necesario |               |

### <a name="references"></a>Referencias 

[Net Promoter Score](https://en.wikipedia.org/wiki/Net_Promoter)

[Uso de Yammer para recopilar comentarios](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[Procedimientos recomendados para los comentarios de los usuarios](best-practices-feedback.md)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>Administrar la calidad de la red

Muchos de los elementos principales de planificación pasan a optimizar, cambiar el tamaño correcto y corregir la infraestructura de red para garantizar una ruta de acceso eficiente y de alta calidad al servicio Microsoft Teams. Las tareas y los requisitos de planificación están cubiertos en nuestra [guía de preparación de red](3-envision-evaluate-my-environment.md#network-readiness) . Las redes a menudo evolucionan con el tiempo debido a actualizaciones, expansión u otros requisitos empresariales. Es importante que tenga en cuenta los requisitos de Teams en las actividades de planificación de red.

Aunque la planificación de red es un aspecto crítico de una implementación de Teams, es igualmente importante asegurarse de que la red se mantenga en buen estado y se mantenga actualizada, en función de los cambiantes requisitos empresariales o técnicos.

Para garantizar el estado de su red, es necesario realizar una serie de actividades de operaciones a intervalos regulares.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas diarias/semanales/mensuales/según sea necesario

| Actividad                                                       | Descripción                                                                                                                                                                                                                                                                                                                                                                 | Cadencia                | Equipo asignado |
|----------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|---------------|
| Supervisar direcciones IP y URL de Office 365                                | Supervise los cambios [realizados en la Office 365 direcciones URL e intervalos de direcciones IP](/microsoft-365/enterprise/urls-and-ip-address-ranges) mediante la [fuente RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) proporcionada e inicie una solicitud de cambio a los grupos de red aplicables.                                                                                                                                | Cada día                  |               |
| Actualizar la red en función de los cambios realizados en Office 365 direcciones IP y URL | Realice actualizaciones a los componentes de red aplicables (firewalls, servidores proxy, VPN, firewalls del lado cliente, etc.) para reflejar los cambios en las [direcciones URL de Office 365 y los intervalos de direcciones IP](/microsoft-365/enterprise/urls-and-ip-address-ranges).                                                                                                                                                              | Según sea necesario              |               |
| Proporcionar datos de creación                                          | Proporcione información actualizada de subred al experto en calidad (o a las partes interesadas relevantes) para asegurarse de que las [definiciones de compilación del CQD](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) se mantengan actualizadas. | Según sea necesario              |               |
| Implementar cambios                                               | Implemente cambios en la red para admitir el cambio Teams requisitos técnicos y empresariales. Los elementos de red pueden incluir:<ul><li>Firewalls</li><li>Vpns</li><li>Redes cableadas y Wi-Fi</li><li>Conectividad a Internet y ExpressRoute</li><li>DNS</li></ul>     | Según sea necesario              |               |
| Supervisión e informes de red                               | Supervise las tendencias de disponibilidad, utilización y capacidad de la red de un extremo a otro utilizando las herramientas de administración de red de terceros y las capacidades de creación de informes disponibles de sus proveedores de red. Use datos de tendencia para la planificación de capacidad de red.                                                                                                            | Diaria, semanal, mensual |               |
| Planificación de la capacidad                                              | Colabore con los propietarios del servicio Teams para comprender los requisitos técnicos y empresariales cambiantes que podrían impulsar cambios adicionales de capacidad.                                | Según sea necesario              |               |
| Solución de problemas y corrección de red                        | Ayude a los Teams al departamento de soporte técnico, a los propietarios del servicio y a las partes interesadas clave a solucionar y solucionar problemas relacionados con la conectividad, la confiabilidad o la calidad de Teams. Los elementos de red pueden incluir:<ul><li>Firewalls</li><li>Vpns</li><li>Redes cableadas y Wi-Fi</li><li>Conectividad a Internet y ExpressRoute</li><li>DNS</li></ul>    | Según sea necesario              |               |
| Pruebas de recuperación ante desastres y alta disponibilidad                | Realice pruebas periódicas de alta disponibilidad y recuperación ante desastres en la infraestructura de red para asegurarse de que cumple los objetivos de nivel de servicio (SLOs) establecidos o los acuerdos de nivel de servicio (SLA) para el servicio de Teams.                                                                                                                                                  | Cada mes                |               |


### <a name="references"></a>Referencias 

[Direcciones URL e intervalos de direcciones IP de Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[Crear esquema de datos](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>Evaluar y garantizar la calidad 

Todas las organizaciones necesitan que un grupo o individuo sea responsable de la calidad. Es, sin duda, el rol más importante en la administración de servicios. El rol de experto en calidad se asigna a una persona o grupo que es apasionado de la experiencia de los usuarios.
y requiere las habilidades adecuadas para identificar tendencias del entorno y el respaldo necesario para poder trabajar con otros equipos y dirigir las correcciones que corresponda. El mejor candidato para ser experto en calidad es normalmente el propietario del servicio al cliente. Dependiendo del tamaño y la complejidad de la organización, podría tratarse de cualquier persona o grupo con pasión por garantizar una experiencia de usuario de alta calidad.

El experto en calidad aprovecha las herramientas existentes y los procesos documentados, como el panel de calidad de llamadas, para supervisar la experiencia del usuario, identificar tendencias de calidad e impulsar la corrección cuando sea necesario.
El experto en calidad debe trabajar con los respectivos equipos para dirigir acciones de corrección e informar a un comité de dirección sobre el progreso y cualquier problema abierto.

Lea [Mejorar y supervisar la calidad de las llamadas para Teams](monitor-call-quality-qos.md), que describe actividades que evalúan y proporcionan orientación de corrección en áreas clave que tienen el mayor impacto en la mejora de la experiencia del usuario. La orientación proporcionada en este artículo se centra en usar el CQD como herramienta principal para informar e investigar cada área, con un foco en el audio para maximizar la adopción y el impacto. Las optimizaciones que se realicen en la red para mejorar la experiencia de audio se traducirán directamente en mejoras de las de vídeo y escritorio compartido.

Te recomendamos encarecidamente que nominas al campeón de calidad al principio. Después de ser nominados, deberían empezar a familiarizarse con [el contenido de calidad de la llamada Monitor](monitor-call-quality-qos.md) y los materiales de capacitación asociados.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas diarias/semanales/mensuales/según sea necesario

| Actividad                               | Descripción                                                                                                                                                                                                                                                                                                 | Cadencia                             | Equipo asignado |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------|---------------|
| Nominar y entrenar a los expertos en calidad | Nominar y entrenar a un experto en calidad.                                                                                                                                                                                                                                                                   | Según sea necesario                           |               |
| Realizar revisiones de calidad de la experiencia (QERs)     | Realice un QER para identificar tendencias en calidad y confiabilidad, revisar objetivos definidos e informar a las partes interesadas clave de la organización.                                                                                                                            | Mensual (semanalmente durante las implementaciones) |               |
| Corrección de unidades                      | Coordine los esfuerzos de corrección en toda la organización en función de las evaluaciones y los hallazgos de QER.                                                                                                                                                                                                           | Según sea necesario                           |               |
| Actualizar los datos de compilación en el CQD            | Actualice o agregue nuevas definiciones de compilación en el CQD cuando se realicen cambios en la red (vea [Upload información de compilación](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)). | Según sea necesario                           |               |
| Completar el rol de campeón de calidad      | Responsabilidad integral de la calidad en la organización. Esto incluye:<ul><li>Asegúrese de que el QER se lleva a cabo periódicamente.</li><li>Informe a las partes interesadas clave sobre el estado de la calidad.</li><li>Asegúrese de que las definiciones de datos de compilación estén actualizadas.</li><li>Coordine los esfuerzos de corrección en toda la organización para garantizar que los usuarios tengan una experiencia de alta calidad con Teams.</li></ul>          | Cada día                               |               |



### <a name="references"></a>Referencias 


[Upload inquilino y creación de datos en el CQD](CQD-upload-tenant-building-data.md)

[Mejorar y supervisar la calidad de las llamadas para Teams](monitor-call-quality-qos.md)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>Administrar puntos de conexión

Microsoft Teams puntos de conexión se pueden definir como cualquier equipo PC, Mac, tableta o dispositivo móvil (o cualquier otro) que ejecute el cliente de Teams. El término *punto final* no solo abarca el propio dispositivo, sino también la forma en que un usuario se conecta al dispositivo( por ejemplo, mediante el uso del micrófono o altavoz integrado del dispositivo, auriculares o auriculares optimizados. Una vez implementados, los puntos de conexión no se deben olvidar. Los puntos de conexión de Teams requieren un mantenimiento y una atención continuada. En las siguientes secciones se describen áreas específicas en las que centrarse.

### <a name="endpoint-requirements"></a>Requisitos del punto de conexión

Una de las principales ventajas de Teams es que el cliente se mantiene actualizado automáticamente. Los clientes de PC y Mac se actualizan mediante un proceso en segundo plano que comprueba si hay nuevas compilaciones y descarga el cliente nuevo cuando la aplicación está inactiva. Las Teams aplicaciones móviles se mantienen actualizadas a través de sus respectivas tiendas de aplicaciones.

El cliente de Teams tiene requisitos mínimos en términos de la plataforma de software subyacente. Estos requisitos pueden cambiar con el tiempo y, por lo tanto, es importante que los supervise para ver si hay cambios. Por ejemplo, el cliente de Teams tiene una versión iOS mínima. Si el cliente usa un explorador de Internet, el explorador también debe mantenerse actualizado. Encontrará una lista de las plataformas compatibles en [Obtener clientes para Microsoft Teams](get-clients.md).

### <a name="endpoint-firewalls"></a>Firewalls para los puntos de conexión

Los firewalls del cliente pueden repercutir de forma significativa en la experiencia de usuario.
Los firewalls del lado cliente pueden afectar a la calidad de la llamada e incluso impedir que se establezca una llamada. Una vez configuradas las exclusiones adecuadas en el firewall del cliente, es necesario mantenerlas actualizadas en función de la información de [Office 365 direcciones URL e intervalos de direcciones IP](/microsoft-365/enterprise/urls-and-ip-address-ranges). El proveedor de terceros tendrá instrucciones específicas sobre cómo actualizar las exclusiones.

### <a name="wi-fi-drivers"></a>Controladores Wi-Fi

Wi-Fi controladores podrían ser problemáticos. Por ejemplo, un controlador podría tener comportamientos de itinerancia muy agresivos entre puntos de acceso que pueden inducir el cambio de punto de acceso innecesario, llevando a una calidad de llamada deficiente. Es posible que se detecte un controlador de Wi-Fi con un rendimiento deficiente a través de una Revisión de calidad de la experiencia (consulta [Mejorar y supervisar la calidad de las llamadas para obtener Teams](monitor-call-quality-qos.md) para obtener más detalles). Es esencial implementar un proceso basado en la calidad que supervise los nuevos controladores de Wi-Fi y se asegure de que se prueban antes de implementarse a la población general de usuarios.

### <a name="endpoint-management"></a>Administración de puntos de conexión

Es necesario disponer y mantener un catálogo de los puntos de conexión y los dispositivos de interfaz admitidos (como auriculares). Este catálogo incluirá una lista de dispositivos aprobados que se seleccionaron y validaron como parte de las fases Envision e Onboard. Normalmente, se seleccionan dispositivos específicos para cada tipo de rol de la organización para satisfacer las necesidades de los atributos de esa persona. Todos los puntos de conexión tienen un ciclo de vida y necesita administrar las directivas de contratos, garantía, sustitución, distribución y reparación de proveedores asociadas con estos dispositivos.

### <a name="endpoint-troubleshooting"></a>Solución de problemas del punto de conexión

Incluso si ha seguido las instrucciones anteriores, los usuarios de su organización pueden tener problemas con Teams. Aunque es posible que el problema no esté relacionado con el propio punto de conexión, los síntomas del problema suelen mostrarse al usuario a través del cliente. Las siguientes instrucciones están pensadas para proporcionar pasos generales que puede realizar para resolver el problema; no está pensado para ser una guía completa de solución de problemas. Los pasos se proporcionan en un orden específico, pero no es necesario que se sigan explícitamente y es posible que no sean aplicables, en función de la naturaleza del problema.

1.  **Validar el estado del servicio:** El problema que puede estar experimentando un usuario puede estar relacionado con un evento que afecta negativamente a la Teams servicio o a sus servicios dependientes. Como primer paso, le recomendamos que confirme que no hay ningún problema de servicio activo. Consulte [Cómo comprobar Office 365 estado del servicio](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0).
    Recuerde comprobar el estado de los servicios dependientes (por ejemplo, Exchange, SharePoint OneDrive para la Empresa). La supervisión del estado del servicio se analiza con más detalle en la sección anterior, [Supervisar el estado del servicio](#monitor-service-health).

2.  **Validar la conectividad de cliente:** Los problemas de conectividad provocan problemas de funcionalidad o de inicio de sesión en Teams. Le recomendamos (especialmente para sitios o ubicaciones nuevos) que valide la conectividad con el servicio. Asegúrese de que se siguen las siguientes [instrucciones Office 365 direcciones URL e intervalos de direcciones IP](/microsoft-365/enterprise/urls-and-ip-address-ranges) para cada sitio. Puede usar la [Herramienta de evaluación de red de Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para realizar una prueba de conectividad y validar que los puertos multimedia se han abierto correctamente para las capacidades de voz en la nube. Los pasos detallados sobre cómo ejecutar las pruebas de conectividad se proporcionan en la guía de [preparación de red](3-envision-evaluate-my-environment.md#network-readiness) .

3.  **Comprueba la lista de problemas conocidos:** Consulte [Teams Solución de problemas](/MicrosoftTeams/troubleshoot/teams) para determinar si uno de estos problemas ha afectado negativamente al usuario. Siga la solución alternativa proporcionada (si hay una) para resolver el problema.

4.  **Visite la comunidad Microsoft Teams:** La [comunidad Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams) ofrece espacios dedicados para Teams. La comunidad Teams proporciona una lista de discusión, entradas de blog y anuncios centrados en Teams. Puedes publicar una pregunta o buscar soluciones a tu problema en discusiones anteriores.

5.  **Soporte técnico de Microsoft** de contacto: puedes ponerte en contacto con Soporte técnico de Microsoft si tienes problemas con Teams en línea o por teléfono. Para obtener más información, consulte [Ponerse en contacto con el soporte técnico para productos empresariales](/microsoft-365/admin/contact-support-for-business-products).
    Para los clientes Premier, las solicitudes de soporte técnico se pueden iniciar siguiendo las instrucciones de [Ponerse en contacto con el servicio de soporte técnico para Microsoft Teams (clientes Premier).](https://support.microsoft.com/premier/contacts)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas diarias/semanales/mensuales/según sea necesario

| Actividad                 | Descripción                                                                                                                                                                                                                                                                                                                                                                     | Cadencia   | Equipo asignado |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Requisitos del punto de conexión    | Asegúrese de que el punto de conexión de Teams sigue cumpliendo todos los requisitos de software para Teams enumerados en [Obtener clientes para Microsoft Teams](get-clients.md).                                                                                                                                                                                       | Cada mes   |               |
| Firewalls para los puntos de conexión       | Mantenga las exclusiones adecuadas en el firewall del punto de conexión en función de la información de [Office 365 direcciones URL e intervalos de direcciones IP](/microsoft-365/enterprise/urls-and-ip-address-ranges). Su proveedor de terceros tendrá instrucciones específicas sobre cómo mantener las exclusiones. Suscríbase a la [fuente RSS](https://support.office.com/o365ip/rss) para recibir notificaciones automáticamente de los cambios. | Según sea necesario |               |
| Controladores Wi-Fi            | Prueba y actualiza los controladores de Wi-Fi en el equipo. Valide los resultados con el CQD ([mejorar y supervisar la calidad de las llamadas para Teams](monitor-call-quality-qos.md)).                                                                                                                                                                                                                                                                   | Según sea necesario |               |
| Administración de puntos de conexión      | Mantenga el catálogo de puntos de conexión y dispositivos de interfaz admitidos (como auriculares). Administre contratos de proveedores, garantías, distribución, reemplazos y directivas de reparación.                                                                                                                                                                                                        | Cada mes   |               |
| Solución de problemas del punto de conexión | Las tareas de solución de problemas pueden incluir la comprobación de conectividad, la consulta de la lista de problemas conocidos, la recopilación de registros, el análisis y la ampliación a Soporte técnico de Microsoft o a proveedores de terceros.                                                                                                                                                                                               | Según sea necesario |               |

### <a name="references"></a>Referencias 

[Direcciones URL e intervalos de direcciones IP de Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[Obtener clientes para Microsoft Teams](get-clients.md)

[comunidad Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Solución de problemas de Teams](/MicrosoftTeams/troubleshoot/teams)

[Comprobar el estado del servicio para Microsoft Teams](service-health.md)

[Contactar con el soporte técnico para productos empresariales: ayuda para administradores](/microsoft-365/admin/contact-support-for-business-products)

[Ponerse en contacto con el soporte técnico Premier](https://support.microsoft.com/premier/contacts)

[Solución de problemas de vídeo Teams](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>Administrar Teams

Una vez implementado el servicio Microsoft Teams, tendrá que realizar varias actividades relacionadas con su administración. Las actividades van desde la administración del servicio y los usuarios individuales hasta la planificación de capacidad y el aprovisionamiento de números de teléfono y licencias. En las siguientes secciones se describen algunas de estas tareas de administración comunes.

### <a name="service-administration"></a>Administración de servicios

El servicio Teams tiene varias opciones de configuración que se pueden configurar en todo el espacio empresarial.
Los cambios realizados en la configuración del inquilino afectan a todos los usuarios que se han habilitado para Teams. Para obtener una lista detallada de estas opciones de configuración, consulte [Administrar la configuración de Microsoft Teams de su organización](enable-features-office-365.md).

### <a name="user-administration"></a>Administración de usuarios

Para dar soporte a los usuarios, una organización puede requerir cualquier número de tareas relacionadas( las tareas específicas varían de una organización a la siguiente. En última instancia, estas tareas deben ser administradas por un equipo de soporte técnico al que se le hayan asignado estas tareas operativas. Las siguientes tareas suelen ser necesarias para admitir usuarios en Teams.

#### <a name="general-tasks"></a>Tareas generales

[Administrar el acceso de los usuarios a Microsoft Teams](user-access.md)

#### <a name="common-tasks-for-phone-system"></a>Tareas comunes para Sistema telefónico

[Asignar, cambiar o quitar un teléfono móvil de un usuario](./assign-change-or-remove-a-phone-number-for-a-user.md)

[Asignar o cambiar una dirección de emergencia para un usuario](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user)

[Agregar, cambiar o quitar una ubicación de emergencia para su organización](/skypeforbusiness/what-are-calling-plans-in-office-365/add-change-or-remove-an-emergency-location-for-your-organization)

[Crear y administrar planes de marcado](create-and-manage-dial-plans.md)

#### <a name="common-tasks-for-audio-conferencing"></a>Tareas comunes para Audioconferencia

[Cambiar la configuración de un puente de Audioconferencias](change-the-settings-for-an-audio-conferencing-bridge.md).

[Cambiar los números de teléfono de su puente de Audioconferencia](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

[Administrar la configuración de Audioconferencia para un usuario](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

[Restablecer el PIN de Audioconferencia](reset-the-audio-conferencing-pin-in-teams.md)

### <a name="license-management"></a>Administración de licencias

A medida que su organización crece o contrata, es importante que planee licencias para necesidades actuales y futuras. Hay una licencia de Teams base, además de licencias para funcionalidades de voz en la nube [Sistema telefónico](here-s-what-you-get-with-phone-system.md) y [Audioconferencia](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing#requirements-for-audio-conferencing).

Para Teams, las licencias de Sistema telefónico requieren licencias de [planes de llamadas](calling-plan-landing-page.md) asociadas. Las licencias de Planes de llamadas le permiten realizar y recibir llamadas telefónicas nacionales o internacionales. Estos planes se basan en el uso y tienen grupos de minutos asociados con ellos. Los [créditos de aprovisionamiento de comunicaciones](what-are-communications-credits.md) garantizarán que nunca se quede sin servicio.

Audioconferencia permite las conferencias de acceso telefónico local de pago y los servicios de conferencias de acceso telefónico local. Las conferencias de acceso telefónico local gratuitas o los escenarios de llamadas entrantes no nacionales pueden provocar que incurra en cargos adicionales para los que se requieran [créditos de comunicaciones](what-are-communications-credits.md) .

Créditos de comunicaciones puede complementar las licencias de Plan de llamadas y Audioconferencia. Tanto las licencias del plan de llamadas como los créditos de comunicación se basan en el uso y, por lo tanto, deben supervisarse y aprovisionarse en consecuencia.

Puede usar el [informe uso de RTC](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) para ayudarle a supervisar el uso de minutos del plan de llamadas y créditos de comunicaciones. En función de los resultados de esta actividad, puede ajustar su licencia en consecuencia. Próximamente, ofreceremos un informe de [grupos de minutos RTC](/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) para ayudar de forma más eficaz con esta tarea.

### <a name="telephone-number-management"></a>Administración de números de teléfono

Existen dos métodos para adquirir números en Teams: puede transferir números de teléfono de otro proveedor o puede aprovisionar los números directamente desde el inventario de números de Microsoft. Ambos métodos se describen en [Obtener números de teléfono para los usuarios](getting-phone-numbers-for-your-users.md).

Hay un límite en el número de números de teléfono que puede aprovisionar en el inventario de números de Microsoft. Los límites se determinan según una serie de factores detallados en [¿Cuántos números de teléfono puede obtener?](how-many-phone-numbers-can-you-get.md).
Los límites dependen del tipo de números: números de servicio gratuitos, números de servicio de pago y números de suscriptor (usuario). Cada uno tiene sus propios límites y debe administrarse de forma independiente. Si te acercas al límite (o has alcanzado el límite), puedes aplicar un incremento al límite. Este proceso se describe en el artículo del párrafo anterior.

Puede haber ocasiones en las que un número no está disponible para ser aprovisionado en una región donde el servicio está disponible. Para obtener información sobre el proceso de solicitud de números, vea [Administrar números de teléfono para su organización](/skypeforbusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).

### <a name="team-creation-optional"></a>Creación de equipos (opcional)

De forma predeterminada, todos los usuarios con un buzón en Exchange Online tienen permisos para crear grupos de Microsoft 365 y, por lo tanto, un equipo de Microsoft Teams. Si desea tener un control más estricto y [restringir la creación de nuevos equipos](assign-roles-permissions.md#permissions-to-create-teams) (y, por lo tanto, la creación de nuevos grupos de Microsoft 365), puede delegar los derechos de creación y administración de grupos a un conjunto de administradores. Si su organización quiere aplicar esta opción, consulte el proceso descrito en este artículo para permitir que los usuarios envíen solicitudes que sean procesadas por un equipo asignado.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas diarias/semanales/mensuales/según sea necesario

| Actividad                    | Descripción                                                                                                                                                                                                                                                                                                                                                                                                             | Cadencia   | Equipo asignado |
|-----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Administración de servicios      | Administración de la configuración de Teams para todos los inquilinos.                                                                                                                                                                                                                                                                                                                                                                           | Según sea necesario |               |
| Administración de usuarios         | Administración de la configuración basada en el usuario y las licencias en Teams.                                                                                                                                                                                                                                                                                                                                                           | Según sea necesario |               |
| Administración de licencias          | Planee las necesidades actuales y futuras de las licencias basadas en el consumo y en el usuario (planes de llamadas y créditos de comunicación) aprovechando el [informe de uso de RTC](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) y el informe de [grupos de minutos rtc](/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) . | Cada semana    |               |
| Administración de números de teléfono | Administre los números de teléfono disponibles para un crecimiento futuro y ajuste los niveles de inventario para satisfacer las necesidades de su organización.                                                                                                                                                                                                                                                                                                | Cada semana    |               |
| Creación de equipos (opcional)    | Revise y procese las solicitudes para la creación de equipos.                                                                                                                                                                                                                                                                                                                                                                          | Según sea necesario |               |

<!--ENDOFSECTION-->

## <a name="improve-and-monitor-call-quality"></a>Mejorar y supervisar la calidad de las llamadas

[Mejorar y supervisar la calidad de las llamadas para Teams](monitor-call-quality-qos.md) incluye un conjunto de actividades que evalúan y proporcionan orientación de corrección en áreas clave que tienen un mayor impacto en la mejora de la experiencia del usuario, como se muestra a continuación.

![Diagrama de las áreas que se examinarán durante una Revisión de calidad de la experiencia.](media/plan-my-service-management-image2.png "Las áreas clave a examinar durante una revisión de calidad de la experiencia: audio, confiabilidad y resultados de encuestas de usuario.")

Si evalúa y corrige continuamente las áreas descritas en la guía, puede reducir su potencial para afectar negativamente a la experiencia del usuario. La mayoría de problemas que se encuentran en la experiencia de usuario de una implementación se pueden agrupar en las siguientes categorías:

-   Una configuración de proxy o firewall incompleta

-   Una cobertura Wi-Fi insuficiente

-   Un ancho de banda insuficiente

-   VPN

-   El uso de dispositivos de audio integrados o no optimizados

-   Dispositivos de red o subred problemáticos

La guía proporcionada en [Mejorar y supervisar la calidad de las llamadas para Teams](monitor-call-quality-qos.md) se centra en usar el Panel de calidad de llamadas (CQD) En línea como herramienta principal para informar e investigar cada área descrita, con un foco en el audio para maximizar la adopción y el impacto. Las optimizaciones que se realicen en la red para mejorar la experiencia de audio se traducirán directamente en mejoras de las de vídeo y escritorio compartido.

Te recomendamos encarecidamente que nominas al campeón de calidad al principio. Después de ser nominados, deberían empezar a familiarizarse con el contenido de [Mejorar y supervisar la calidad de la llamada para Teams](monitor-call-quality-qos.md).

<!--ENDOFSECTION-->