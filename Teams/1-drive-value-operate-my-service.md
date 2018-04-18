---
title: Guía de operaciones de equipos de Microsoft
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 04/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Las tareas y actividades necesarias para la administración de servicios de equipos, incluida la supervisión del estado del servicio, evaluar y garantizar el uso y la calidad de la red.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4d9b76d62457c541924c6f72eb246bf63f1fe026
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="operate-my-service"></a>Operar mi servicio

Este artículo ofrece una visión general de los requisitos para el funcionamiento con éxito servicios de nube de voz para su organización. Accionando correctamente los servicios de voz de la nube, es asegurarse de que va a proporcionar una experiencia confiable de alta calidad para su organización.

## <a name="introduction-to-the-operations-guide"></a>Introducción a la Guía de operaciones

La Guía de operaciones proporciona una visión general de todas las tareas y actividades necesarias como parte de la función de administración de servicios de Teams de Microsoft.

Administración de servicios es un tema muy amplio que abarque las operaciones diarias del servicio Teams de Microsoft después de que se ha implementado y habilitado para los usuarios. El servicio de equipos incluye Microsoft Office 365 y los componentes de infraestructura que implementan en locales (por ejemplo, redes).

El concepto de administración del servicio no es probablemente un nuevo concepto para la mayoría de las organizaciones. Puede que ya haya implementado los procesos y tareas que están asociadas con servicios existentes. Dicho esto, probablemente puede aumentar sus procesos actuales cuando se planea para la administración de servicio de hoy equipos de soporte técnico en el futuro.

Administración del servicio abarca todas las actividades y los procesos implicados en la administración integral de equipos. Como se ha indicado anteriormente, algunos de los componentes de administración de servicios, la infraestructura que comprende el propio servicio Office 365 — son responsabilidad de Microsoft, mientras que usted, el cliente, es responsables ante los usuarios para administrar los diversos aspectos de los equipos de la red y extremos que proporcionan.

Las tareas y actividades en esta guía se agrupan en ocho categorías como se muestra en el siguiente diagrama. Cada una de estas categorías se expandirá en las secciones siguientes.

![Un diagrama que representa una lista de categorías de tareas y actividades que comprendan la administración de servicios para los equipos. El diagrama muestra también que la administración de servicios es en gran medida una tarea cliente.] (media/operate-my-service-image1.png "Un diagrama que representa una lista de categorías de tareas y actividades que comprendan la administración de servicios para los equipos. El diagrama muestra también que la administración de servicios es en gran medida una tarea cliente.")


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>Decidir cómo se implementarán las operaciones para equipos.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Revise a la Guía de operaciones en su totalidad.</li><li>Implementar una estrategia de operaciones que se alinea con los objetivos de la organización para ofrecer la calidad y la fiabilidad de la nube de cargas de trabajo de voz.</li><li>Revise a la Guía de revisión de la experiencia de calidad.</li><li> Implementar una estrategia de operaciones para llevar a cabo periódicamente revisiones de la experiencia de calidad para asegurarse de que la implementación de voz de nube está funcionando a capacidades de pico.</li></ul></td></tr>
</table>


### <a name="operational-role-mapping"></a>Asignación de funciones operacionales

La planificación que llevó a cabo para operaciones durante la fase de previsión es crítica, dado que las actividades de las operaciones comienzan cuando se habilitan los primeros usuarios piloto. Esta guía muestra las actividades y tareas que deben realizarse de forma diaria, semanal, mensual o según sea necesario para mantener una implementación de equipos de alta calidad. Esta guía proporciona los conocimientos y orientación sobre cómo realizar estas tareas y actividades críticas.

Es un componente crucial de una implementación correcta garantizar que la planificación de lo anticipado en la fase de previsión incluye determinar quién será responsable de realizar actividades específicas. Cuando haya averiguado qué tareas y actividades que se aplican a su implementación, tienen que ser entendido y seguido por los grupos o individuos a los que se les asigne.

Cada equipo identificado debe revisar y acordar las tareas y responsabilidades identificadas e iniciar preparación. Esto podría incluir la formación y preparación, que proporciona actualizaciones para el personal o asegurar los proveedores externos están listos para entregar.

Las actividades y funciones definidas en esta guía deben ser válidas en la mayoría de los escenarios, pero cada implementación de equipos es única; por lo tanto, puede utilizar a esta guía como punto de partida para personalizar las actividades y roles predeterminados para satisfacer sus necesidades.

Asegúrese de que cada equipo responsable tiene una buena comprensión de las actividades que se requieren para ejecutar el servicio. Es fundamental que cada equipo acepta y aprueba su responsabilidad en la organización antes de que comience la primera prueba piloto.

Una vez un acuerdo, deben iniciar los equipos correspondientes que controle sus funciones.

<table>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td>
<td><ul><li>Utilice este documento para facilitar el ejercicio de la asignación de función de operación.</li><li>Reúnase con los equipos de apoyo respectivos para asignar nombres a cada elemento de la lista de actividades necesarias.</li><li>Obtener la aceptación o cierre la sesión en las funciones asignadas.</li><li>Asegurar que los equipos correspondientes tengan la formación adecuada, preparación y recursos para completar sus actividades necesarias.</li></ul></td></table>

### <a name="teams-service-dependencies"></a>Dependencias de servicios de equipos

Teams Microsoft reúne los recursos tecnologías de Office 365 para proporcionar un concentrador para el trabajo en equipo. Algunos ejemplos incluyen;

-   Active Directory Azure proporciona servicios de autenticación y autorización para los equipos.

-   Exchange Online proporciona funciones avanzadas como la retención legal y e-discovery.

-   SharePoint Online proporciona la capacidad de compartir archivos en canales y OneDrive para el negocio proporciona un mecanismo para compartir archivos dentro de una charla privada.

Las organizaciones también pueden aprovechar las inversiones existentes en infraestructura local. Por ejemplo, cuentas existentes de Active Directory local pueden utilizarse para la autenticación mediante el aprovechamiento de Azure Connect de AD. Ciertas versiones de Exchange Server pueden utilizarse en lugar de Exchange Online.

Estas tecnologías incluyen juntos para proporcionar una serie de comunicaciones enriquecidas, colaboración e inteligente para los usuarios. Esta estrecha integración es una ventaja clave de los equipos, pero también impulsa un requisito para la administración de servicios a través de estas tecnologías.

Esta guía abarca las áreas clave de enfoque para administrar el servicio de los equipos. Probablemente, tendrá planes de gestión de servicio en lugar de las tecnologías de apoyo que depende de los equipos. Si no, necesitará establecer planes de gestión de servicio adecuada para los componentes de la tecnología (ambos locales y en línea) también. Esto le ayudará a asegurarse de que los usuarios disfrutan de una experiencia confiable de alta calidad, con los equipos.

#### <a name="references"></a>Referencias 

[Introducción a Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-overview)

[Interacción entre Exchange y Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact)

[Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/sharepoint-onedrive-interact)

[Teams de Microsoft y Skype para la interoperabilidad de empresa](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>Actividades de la Guía de operaciones

Las secciones siguientes proporcionan una visión general de las actividades que se requieren para operar correctamente el servicio de Teams de Microsoft. Incluyen referencia a herramientas, información contextual y contenido adicional para ayudarle a comprender la actividad y ayudar en las iniciativas de preparación.

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>Monitorear el estado de servicio

Es importante que comprenda el estado general del servicio Teams de Microsoft para que puede alertar proactivamente otros usuarios de la organización de cualquier evento que afecta al servicio. Como se describió anteriormente, los equipos depende de otros servicios de Office 365 como Azure Active Directory, Exchange Online, SharePoint Online y OneDrive para el negocio. Por este motivo, es importante que supervise el estado de los servicios dependientes.

Incorporar esta actividad en el proceso de administración de incidencias para informar proactivamente a los usuarios, el departamento de soporte y los equipos de operaciones para prepararse para manejar las extensiones de usuario.

Las secciones siguientes describen las herramientas que puede aprovechar para supervisar [incidentes de servicio] (https://technet.microsoft.com/library/office-365-service-health.aspx?f=255&MSPPError=-2147217396#Service incidentes) que afecta al servicio de los equipos. En la siguiente tabla, se incluye un resumen de las ventajas de cada herramienta, y cuándo debe utilizar cada uno de ellos.

| Herramienta de supervisión                       | Beneficios                                            | Cuándo se debe utilizar                                                                                  |
|---------------------------------------|-----------------------------------------------------|----------------------------------------------------------------------------------------------|
| Portal de Office 365                     | Disponible desde cualquier dispositivo con un navegador soportado. | Se utiliza cuando no requieren notificaciones en tiempo real.                                          |
| Aplicación de administración de Office 365                  | Proporciona notificaciones de inserción a tu dispositivo móvil.  | Cuando necesite notificación de incidentes del servicio mientras está de viaje.                  |
| Microsoft System Center               | Integración con Microsoft System Center.           | Se requieren capacidades avanzadas de monitoreo y soporte de notificación.                       |
| API de comunicación de servicio de Office 365 | Acceso mediante programación al servicio de salud de Office 365.   | Requieren la integración con una herramienta de supervisión de las partes 3ª o desea crear su propia solución. |

> [!NOTE]
> Sólo los individuos que tienen asignados la función **administrador global** o **Administrador de servicio** pueden ver el estado del servicio.

### <a name="monitoring-with-the-office-365-portal"></a>Supervisar con el portal de Office 365

El [portal de Office 365](https://portal.office.com/) proporciona un [tablero de estado de servicio](https://portal.office.com/adminportal/home#/servicehealth) donde puede ver el estado actual del servicio de equipos además de los servicios dependientes.

### <a name="monitoring-with-the-mobile-app"></a>Supervisión de la aplicación móvil

La aplicación de administración de Office 365 está disponible en Apple iOS, Android y Windows (PC y mobile). La aplicación proporciona a los administradores del servicio de información sobre el estado del servicio y los próximos cambios. La aplicación es compatible con las notificaciones de inserción que le pueden alertar casi inmediatamente después de que se ha publicado un documento informativo. Esto le ayuda a mantenerse al día sobre el estado, el estado y los próximos cambios en el servicio. El soporte de notificación hace la herramienta de supervisión recomendada para administradores. Para obtener más información, consulte:

[Office 365 Mobile Admin App](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[Descargar la aplicación Mobile Admin de Office 365](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>Supervisión de Microsoft System Center

Microsoft System Center es una plataforma de administración integrada que le ayuda a administrar centros de datos, los dispositivos cliente y híbrido de nube entornos de TI. Los administradores de Office 365 que usar System Center ahora tienen la opción de importar el paquete de administración de Office 365, que les permite ver todas las comunicaciones de servicio dentro del Administrador de operaciones de System Center. Con esta herramienta le permite acceder al estado de los servicios suscritos, los incidentes de servicio activos y resueltos y las comunicaciones de centro de mensajes (próximos cambios). Para obtener más información, consulte la siguiente [entrada de blog](https://blogs.office.com/2014/07/29/new-office-365-admin-tools/?eu=true).

Si se aprovecha de System Center para supervisar el estado de servicio de los equipos (y servicios dependientes), se puede personalizar el paquete de administración para alertar o notificar a grupos específicos o las personas que han sido identificados ante los incidentes.
Estos grupos pueden incluir propietarios de servicio, asistencia, grupos de segundo nivel y tercer nivel de soporte y administradores de incidentes en la organización.

### <a name="monitoring-for-advanced-scenarios"></a>Supervisión para escenarios avanzados

Puede supervisar el estado del servicio y los próximos cambios aprovechando la API de comunicaciones de servicio de Office 365 para obtener acceso mediante programación a los cambios y el estado del servicio Office 365. Utilice esta API para crear su propia supervisión herramienta o conectar sus herramientas de monitoreo existentes para comunicaciones de servicio de Office 365, potencialmente simplificando cómo supervisar su entorno. Para obtener más información, vea [Office 365 para los desarrolladores de la empresa](https://msdn.microsoft.com/library/jj984343(v=office.15).aspx).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas diarias/semanales/mensuales/según sea necesario

| Actividad               | Descripción                                                                                                                                                                                                               | Cadence   | Equipo asignado |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Monitorear el estado de servicio | Monitorear proactivamente el estado del servicio Teams de Microsoft (y servicios dependientes) utilizando las herramientas disponibles. Servicios dependientes incluyen: Exchange Online, SharePoint Online, OneDrive para el negocio, Azure Active Directory. | En tiempo real |               |
| Notificación de incidentes  | Notificar a los participantes internos de los eventos que afectan al servicio de los equipos. Los participantes internos pueden incluir usuarios, asistencia y los administradores de incidentes.                                                                          | Según sea necesario |               |

### <a name="references"></a>Referencias 

[Cómo comprobar el estado del servicio Office 365](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[Compruebe el estado del servicio para equipos de Microsoft](https://docs.microsoft.com/microsoftteams/service-health)

[Continuidad y servicio de salud](https://technet.microsoft.com/library/office-365-service-health.aspx)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>Administrar el cambio organizativo

Teams de Microsoft es un servicio basado en cloud. Con el incluye la capacidad para proporcionar nuevas características y funcionalidad a un ritmo acelerado. Ofrece innovación constante proporciona una ventaja obvia de las organizaciones, pero estos cambios deben administrarse correctamente dentro de su organización para evitar la resistencia del usuario o delegaciones a su servicio de asistencia.

Actualizaciones de equipos se aplican automáticamente a los usuarios. Los usuarios tendrán siempre el cliente y las características disponibles en el servicio de los equipos más recientes. No es posible administrar la implementación de actualizaciones de los equipos de los usuarios, por lo tanto, es sumamente importante administrar el cambio a través de programas eficaces de comunicación, capacitación y adopción. Si los usuarios son conscientes del cambio, educar sobre los beneficios y facultada para aprovechar las nuevas capacidades de&mdash;podrá adaptarse más rápidamente y el cambio de bienvenida.

### <a name="monitoring-for-change"></a>Supervisión del cambio

El primer paso en la administración del cambio está supervisando los cambios planificados para los equipos. La mejor fuente para la supervisión de estos cambios es la [Guía básica de Office 365](https://products.office.com/business/office-365-roadmap), que muestra las características que están actualmente en desarrollo, que se está distribuyendo a los clientes, o se han iniciado completamente. Puede buscar características específicas de los equipos mediante el filtro proporcionado, o puede descargar la hoja de ruta a un archivo de Excel para su análisis posterior. Para cada característica, la guía ofrece una breve descripción, junto con la fecha de emisión previstos.

En el [blog de equipos de Microsoft](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog), puede aprender acerca de mejores prácticas, tendencias y noticias sobre actualizaciones de productos de equipos. Esperan encontrar actualizaciones de características más importantes para los equipos que se anunciarán aquí. También puede suscribirse al blog a través de una fuente RSS. A continuación, puede agregar [la fuente RSS](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog) directamente en un canal de los equipos, por lo que todas las noticias importantes es entregar directamente dentro de los equipos.

Todas las características que se han liberado se documentan en las [Notas de la versión para equipos de Microsoft](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de).
Aquí encontrará una lista de características que se publicaron para escritorio, web y dispositivos móviles. El mismo conjunto de notas de la versión también están disponibles en la ficha Notas de revisión en los [Equipos de Microsoft T-Bot](https://docs.microsoft.com/microsoftteams/t-bot).

Familiarizarse con los recursos disponibles y asegúrese de que asigna propietarios aplicables para monitorear los cambios.

### <a name="planning-for-change"></a>La planificación de cambios

Ahora que eres consciente de los próximos cambios en el servicio de los equipos, el siguiente paso es preparar y planear en consecuencia. Evaluar cada cambio para determinar los cambios que requieren una comunicación a los usuarios, campañas de sensibilización, formación de equipos de soporte técnico o usuarios o campañas de evaluación y adopción de la característica. Esta es la función principal de un equipo de administración de cambios en su organización. A continuación es un conjunto de tablas que pueden ayudar a plan cambios de muestra.

[//]: # (La extensión de columna y el tamaño de fila de esta tabla son encantadora pero no admitido en el descuento, por lo menos que el rowspan es. Esto es lo más parecido que pude obtener. Tal vez todo esto debe volver a diseñar.)

#### <a name="feature-cloud-recording-release-date-january-2018"></a>Característica: La nube de grabación (fecha de publicación: enero de 2018)

**Pista general**
| Preparación para el cambio | Estado   | Los pasos siguiente/notas | Owner |
|----|----|----|-----|
| Revisión legal   | Completado     | Esta característica es un requisito previo para la incorporación del equipo de capacitación. | Equipo del proyecto  |

**Administración de cambios técnicos**
| Preparación para el cambio | Estado   | Los pasos siguiente/notas | Owner |
|----|----|----|-----|
| Cambios en TI          | Sí                  | Administrador necesita habilitar la grabación para que sólo los usuarios identificados.      | Equipo de soporte técnico           |
| Preparación técnica completa | Sí                  |                                                                 | Equipo de soporte técnico  
         |
**Administración de cambio de usuario** 
| Preparación para el cambio | Estado   | Los pasos siguiente/notas | Owner |
|----|----|----|-----|
| Impacto en los usuarios                  | Bajo                  |                                                                 |                        |
| Preparación de usuario requerido      | Sí                  |                                                                 |                        |
| Comunicaciones listas         | No                   | Correo electrónico de comunicación se ha redactado, pendientes de revisión.            | Equipo de comunicaciones    |
| Preparado para la formación               | Sí                  | Formación aprovechará vídeo existente de Microsoft.                | Equipo de formación          |

**Seguimiento de estado**
| Preparación para el cambio | Estado   | Los pasos siguiente/notas | Owner |
|----|----|----|-----|
| Estado de publicación               | en curso          | Revisión pendiente por el patrocinador ejecutivo.               | Equipo de administración de cambios |
| Aprobación de la versión             |                      |                                                                 |                        |
| Fecha de lanzamiento                 |                      |                                                                 |                        |

Para obtener más información acerca de cómo planear los equipos de administración de cambios, vea [crear una estrategia de administración de cambios para equipos de Microsoft](https://docs.microsoft.com/microsoftteams/change-management-strategy).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas diarias/semanales/mensuales/según sea necesario

| Actividad               | Descripción                                                                                                                                                                                                                | Cadence   | Equipo asignado |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Monitor de cambios     | Monitor para los próximos cambios en el servicio de Teams de Microsoft.                                                                                                                                                                   | A diario     |               |
| La planificación de cambios    | Evaluar y planear para nuevas características y capacidades, incluyendo planes de comunicación, campañas de sensibilización y formación.                                                                                                     | Según sea necesario |               |
| Preparación del usuario             | Realizar comunicaciones dirigidas, conocimiento o campañas de formación para garantizar que los usuarios están listos para el próximo cambio.                                                                                                        | Según sea necesario |               |
| Preparación del equipo de soporte | Realizar comunicaciones dirigidas, conocimiento o campañas de capacitación para asegurarse de que el equipo de soporte está preparado. El equipo de "guante blanco", asistencia, nivel 2 o nivel 3 soporte, socios externos etc., pueden incluir equipos de soporte técnico. | Según sea necesario |               |

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>Evaluar el uso de equipos

Después de que comience la prueba piloto inicial, es muy importante establecer una cadencia regular para medir el uso real de los equipos. Esto permite su organización para obtener información sobre el uso real de cómo se alinea con el uso que previsto durante la fase de previsión. Aunque esta sección se centra en el uso de equipos, esto debe formar parte de un esfuerzo más amplio para medir y evaluar Office 365 uso general.

Revisar el uso con frecuencia antes de la implementación, le da la oportunidad de:

-   Validar si los usuarios utilizan los equipos.

-   Identificar desafíos de adopción potenciales antes de que provoquen problemas críticos en toda la organización.

-   Comprender si hay discrepancias entre los requisitos de la fase de previsión y el uso real.

Si el uso no es el esperado, puede deberse a un problema de implementación o el plan de adopción no está siendo ejecutada correctamente, o en cualquier otro problema. Dependiendo de la razón real detrás del uso bajo, el Administrador de servicios debe colaborar con los equipos relacionados para ayudar a eliminar las barreras de uso.

### <a name="measuring-usage-with-the-office-365-admin-center"></a>Medir el uso con el centro de administración de Office 365

Datos de uso de los equipos están disponibles en el panel de informes. Datos de uso de los equipos pueden encontrarse en tres informes diferentes. El primer informe proporciona una vista de producto cruzado de cómo los usuarios comunicarán y colaboran utilizando los distintos servicios de Office 365. Este informe puede encontrarse aquí: [informe de usuarios activos de Office 365](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

Los dos informes son específicos de los equipos, y que proporcionan más detalles acerca del uso de los equipos desde una perspectiva de dispositivo y de usuario. Ambos informes se pueden encontrar aquí:

[Informe de uso de dispositivos de Microsoft Teams](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-device-usage-917b3e1d-203e-4439-8539-634e80196687)

[Informe de actividad de usuario de Microsoft Teams](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-user-activity-07f67fc4-c0a4-4d3f-ad20-f40c7f6db524)

#### <a name="required-permissions"></a>Permisos necesarios

Personas que han sido asignadas a una función de **Administrador Global** o una función específica del producto admin (**Administrador de Exchange**, **Skype para el Administrador corporativo**, **SharePoint pueden tener acceso a los informes de uso en el centro de administración Administrador de**).

Además, la función de **lector de informes** está disponible para los usuarios que requieren acceso a los informes, pero no realizan tareas que requieren permisos de administrador. Asignar este rol para proporcionar informes de uso para quien es un participante, para la adopción del monitor y la unidad. Para obtener más información acerca de las diferentes funciones disponibles, vea [las funciones de administrador acerca de Office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="assessing-usage"></a>Evaluar el uso

Después de haber utilizado el tablero de mandos de informes para medir el uso, es muy importante comparar el uso medido contra cualquier indicadores clave para el éxito (KSIs) que se ha definido durante la fase de previsión del proyecto. Puede definir un KSI que podría definirse como uso activo o uno que sea uso indirectamente vinculada a activo.

Es importante identificar las variaciones entre el uso real y el planeado antes de reanudar la ejecución a otros sitios o usuarios. Probablemente podrá identificar aprendizajes organizacionales como parte de esta actividad que puede aprovechar para asegurarse de que el siguiente lote de sitios o usuarios no encuentra los mismos problemas.

En primer lugar, determinar si se trata de una adopción o un problema técnico. Empezar por investigar los elementos a continuación, en orden, para determinar dónde está el problema.

1.  Realizar una [Revisión de la experiencia de calidad](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service#quality-of-experience-review-guide)para validar la calidad.

2.  Trabaje con el equipo de asistencia técnica para comprobar que no existen problemas técnicos tendencias impedir que los usuarios tienen acceso o utilizan el servicio. Si existen tendencias de problemas, utilice la sección [solución de problemas de extremo](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service#endpoint-troubleshooting) más adelante en este artículo para intentar solucionar el problema antes de contratar el soporte técnico.

3.  Trabaje con el equipo de capacitación y adopción para recopilar los comentarios de los usuarios (consulte la [opinión del usuario valoración](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service#assess-user-sentiment) más adelante en este artículo) y para comprobar la eficacia de las actividades de sensibilización y adopción.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas diarias/semanales/mensuales/según sea necesario

| Actividad                         | Descripción                                                                                                                      | Cadence   | Equipo asignado |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Uso de medida (fase de habilitación) | Medir y evaluar el uso de equipos durante la fase de habilitación, como sitios siguen siendo onboarded. Solucionar problemas de uso según sea necesario. | Cada semana    |               |
| Uso de medida                    | Medir y evaluar el uso de equipos en la fase de valor unidad (una vez completada la implementación). Solucionar problemas de uso según sea necesario. | Bisemanal  |               |
| (fase de valor de unidad)              |                                                                                                                                  |           |               |
| Actualizar plan de adopción             | Actualización de su plan de adopción basada en el consumo medido cómo se compara con los objetivos de la planificación.                                         | Según sea necesario |               |

### <a name="references"></a>Referencias 

[Acerca del centro de administración de Office 365](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Informes de actividades en el Centro de administración de Office 365](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>Valorar la opinión de usuario

Comprender la opinión del usuario puede actuar como un indicador clave para el éxito de la implementación de equipos de medición. Comentarios de los usuarios pueden impulsar cambios en la organización; Esto puede incluir cambios en los planes de comunicación, programas de formación o la forma en que ofrecer soporte técnico a los usuarios.

Es importante obtener comentarios temprano y continuar con la evaluación de opinión de usuario en todo el ciclo de vida del proyecto y más allá. Utilice las siguientes pautas para determinar el intervalo en el que su organización buscará los votos:

-   **A partir del proyecto**: evaluando la opinión del usuario al principio del proyecto, puede obtener una vista temprano en sentimientos de los usuarios sobre su experiencia de los equipos.

-   **Después de hitos principales**: mediante la recopilación de comentarios a lo largo del ciclo de vida del proyecto, puede medir el sentimiento de usuario en forma continua y realice los cambios necesarios. Esto es especialmente útil después de hitos importantes.

-   **Conclusión del proyecto**: sentimiento de usuario al final de un proyecto de evaluación le indicará qué tan bien que ha hecho y donde trabajo queda por hacer y permiten comparar los resultados de la encuesta anterior.

-   **En curso**: continuar medir la opinión de usuario indefinidamente. Cambios en el sentimiento de usuario puede deberse a cambios en el entorno de su organización o cambios en el servicio de los equipos. Por medición sentimiento de usuario a intervalos regulares, puede entender qué tan bien están realizando los equipos de gestión de servicio y cómo responde la organización a los cambios en el servicio de los equipos.

Opinión de usuario se puede evaluar mediante muchos métodos diferentes. Estos pueden incluir encuestas de correo electrónico, en persona o entrevistas de estilo de teléfono o simplemente crear un canal de comentarios en los equipos o Yammer. Para obtener más información, vea [prácticas recomendadas para los métodos de comentarios de usuario en equipos de Microsoft](https://docs.microsoft.com/microsoftteams/best-practices-feedback).

También puede utilizar un enfoque de toda la industria para evaluar la opinión de usuario llamado net promotor puntuación (NPS), que se describe en la sección siguiente.

### <a name="nps"></a>NPS 

Puntuación del promotor neto (NPS) es una métrica de lealtad del cliente formación y un buen enfoque a utilizar para evaluar la opinión del usuario.

NPS puede calcularse mediante dos preguntas: "¿Qué probabilidades hay que recomendar equipos a un colega?", seguido de la pregunta de la forma libre, "¿por qué?"

El NPS es un índice comprendido entre -100 y 100, que mide la voluntad del cliente para recomendar el producto o servicio de una empresa. NPS se basa en una encuesta anónima que se entrega a los usuarios a través de correo electrónico u otros medios electrónicos. NPS mide la lealtad entre un proveedor y un consumidor. Consta de una única pregunta, que pide a los usuarios a evaluar su experiencia del 1 al 10, con la opción de proporcionar comentarios adicionales. Los usuarios se clasifican entonces basándose en las siguientes clasificaciones:

-   9 o 10 son promotores: fieles entusiastas que promoverá el servicio y otros de combustible.

-   7 u 8 son pasivo: satisfecho pero no entusiasta, vulnerables a otro servicio o una oferta.

-   Entre 1 y 6 son detractores: los clientes insatisfechos que pueden dañar su servicio y que impiden el crecimiento.

![Este diagrama muestra la escala NPS. Muestra que los rankings de 0-6 son detractores, son pasivo 7-8 y 9 y 10 son promotores.] (media/operate-my-service-image2.png "Este diagrama muestra la escala NPS. Muestra que los rankings de 0-6 son detractores, son pasivo 7-8 y 9 y 10 son promotores.")

Aunque el número base de NPS es útil, obtendrá el máximo valor de analizar los comentarios del usuario. Le ayudan a comprender por qué el usuario haría (o no) recomendar equipos a otras personas. Estos comentarios pueden proporcionar valiosa información para ayudar al proyecto o equipos de gestión de servicio comprender los ajustes necesarios para proporcionar un servicio de calidad.

Para proporcionar las encuestas NPS para su organización, puede aprovechar su herramienta favorita de encuesta en línea.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Diarias/semanales/mensuales/como sea necesario en las tareas

| Actividad              | Descripción                                                                                                                                                                         | Cadence   | Equipo asignado |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Valorar la opinión de usuario | Capturar y evaluar la opinión del usuario mediante encuestas o entrevistas, o a través de un canal de comentarios en los equipos o Yammer.                                                                 | Según sea necesario |               |
| Actualizar planes de adopción | Cambio de unidad de la organización basándose en los comentarios de los usuarios; Esto puede incluir cambios en los planes de comunicación, programas de formación o la forma en que ofrecer soporte técnico a los usuarios. | Según sea necesario |               |

### <a name="references"></a>Referencias 

[Puntuación del promotor neto](https://en.wikipedia.org/wiki/Net_Promoter)

[Uso de Yammer para recopilar comentarios](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[Prácticas recomendadas para comentarios de los usuarios](https://docs.microsoft.com/microsoftteams/best-practices-feedback)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>Administrar la calidad de la red

Muchos elementos de planificación principales entran en optimizar, idónea y remediar la infraestructura de red para asegurar un camino eficaz de alta calidad en el servicio de Teams de Microsoft. Se tratan las tareas y requisitos de planificación en nuestra guía de [Preparación de la red](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#network-readiness) anterior. Las redes suelen evolucionan con el tiempo debido a las actualizaciones, expansión u otros requisitos empresariales. Es importante que cuenta para sus requisitos para los equipos de la red de las actividades de planeamiento.

Aunque el diseño de la red es un aspecto fundamental de una implementación de equipos, es igualmente importante garantizar la red permanece sana y permanece actual, basándose en los cambiantes requisitos técnicos o empresariales.

Para garantizar la salud de la red, una serie de actividades de operaciones debe realizarse a intervalos regulares.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas diarias/semanales/mensuales/según sea necesario

| Actividad                                                       | Descripción                                                                                                                                                                                                                                                                                                                                                                 | Cadence                | Equipo asignado |
|----------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|---------------|
| Supervisar Office 365 IPs y direcciones URL                                | Supervisar los cambios en [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://aka.ms/o365ips) mediante el uso de la [fuente RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) proporcionado e iniciar una solicitud de cambio a los grupos de red correspondientes.                                                                                                                                | A diario                  |               |
| Actualización de la red basándose en cambios en las direcciones URL y Office 365 IPs | Realizar actualizaciones a los componentes de red aplicable (firewalls, servidores proxy, VPN, firewalls de cliente etc.) para reflejar los cambios en las [direcciones URL de Office 365 y los intervalos de direcciones IP](https://aka.ms/o365ips).                                                                                                                                                              | Según sea necesario              |               |
| Proporcionar datos del edificio                                          | Proporcionar información de subred actualizadas al experto de calidad (o partes interesadas) para asegurar que la [creación de definiciones de CQD](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) se mantienen actualizados. | Según sea necesario              |               |
| Implementar el cambio                                               | Implementar cambios en la red a los requisitos técnicos y comerciales de los equipos de soporte cambiantes. Pueden incluir elementos de red:<ul><li>Firewalls</li><li>Redes privadas virtuales</li><li>Por cable y redes Wi-Fi</li><li>Conectividad a Internet y ExpressRoute</li><li>DNS</li></ul>     | Según sea necesario              |               |
| Red monitoreo y reporting                               | Supervisar la red de extremo a extremo para las tendencias de capacidad, utilización y disponibilidad utilizando las herramientas de administración de red de terceros existentes y las capacidades disponibles en los proveedores de red. Utilizar datos de tendencias para la planificación de la capacidad.                                                                                                            | Diariamente, semanalmente, mensualmente |               |
| Planificación de la capacidad                                              | Colaborar con los propietarios de servicio de los equipos para comprender los cambiantes requerimientos empresariales y técnicas que pueden impulsar cambios de capacidad adicional. Aproveche los resultados desde el [Planificador de la red](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) para asegurarse de que suficiente ancho de banda está disponible para Microsoft Teams.                               | Según sea necesario              |               |
| Solucionar problemas de red y corrección                        | Ayudar a la asistencia de equipos, propietarios de servicio y los participantes clave para solucionar y corregir problemas relacionados con la conectividad, la confiabilidad o la calidad de los equipos. Pueden incluir elementos de red:<ul><li>Firewalls</li><li>Redes privadas virtuales</li><li>Por cable y redes Wi-Fi</li><li>Conectividad a Internet y ExpressRoute</li><li>DNS</li></ul>    | Según sea necesario              |               |
| Recuperación ante desastres y pruebas de alta disponibilidad                | Realizar regular alta disponibilidad y recuperación ante desastres pruebas en la infraestructura de red para asegurarse de que cumple los objetivos de nivel de servicio establecidos (SLO) o acuerdos de nivel de servicio (SLA) para el servicio de los equipos.                                                                                                                                                  | Cada mes                |               |


### <a name="references"></a>Referencias 

[Planeador de red](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner)

[URL de Office 365 e intervalos de direcciones IP](https://aka.ms/o365ips)

[Esquema de generación de datos](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>Evaluar y garantizar la calidad 

Todas las organizaciones necesitan un grupo o una persona sea responsable de la calidad. Esto es el papel más importante en la administración de servicios. La función de calidad experto se asigna a una persona o grupo que es un apasionado de la experiencia de sus usuarios.
Esta función requiere los conocimientos necesarios para identificar tendencias en el entorno y el patrocinio para trabajar con otros equipos de la unidad de corrección. El mejor candidato para ser experto en calidad es normalmente el propietario del servicio al cliente. Según el tamaño y la complejidad de la organización, podría tratarse de una persona o grupo con pasión para garantizar una experiencia de usuario de alta calidad.

El experto de calidad aprovecha las herramientas existentes y procesos documentados, como llamar a calidad Dashboard (CQD) y la Guía de revisión de experiencia de calidad, para controlar la experiencia del usuario, identifican tendencias de calidad y corrección de la unidad donde sea necesario.
El experto de calidad debe trabajar con los equipos correspondientes a las acciones de corrección de unidad y el informe a un Comité de dirección sobre el progreso y los problemas abiertos.

La [Calidad de la Guía de revisión de experiencia](https://aka.ms/qerguide) incluye actividades que evaluarán y proporcionan orientaciones sobre correcciones en áreas clave que tienen el mayor impacto en la mejora de la experiencia del usuario. Las instrucciones proporcionadas en la Guía de revisión de experiencia de calidad se centra en usar CQD en línea como herramienta principal para informar e investigar cada área, con énfasis en audio para maximizar la adopción e impacto. Se traducirá también directamente cualquier optimizaciones realizadas a la red para mejorar la experiencia de sonido a mejoras en el uso compartido de escritorio y vídeo.

Se recomienda encarecidamente que se nombra al Campeón de calidad desde el principio. Después de que se ha designado, deberían empezar a familiarizarse con el contenido de la Guía de revisión de experiencia de calidad y materiales de capacitación asociados.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas diarias/semanales/mensuales/según sea necesario

| Actividad                               | Descripción                                                                                                                                                                                                                                                                                                 | Cadence                             | Equipo asignado |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------|---------------|
| Designar y entrenar Campeón de calidad | Nominar y formar un Campeón de calidad.                                                                                                                                                                                                                                                                   | Según sea necesario                           |               |
| Realizar revisiones de la experiencia de calidad     | Realizar una revisión de la experiencia de calidad (QER) para identificar las tendencias en la calidad y confiabilidad, revise frente a los objetivos fijados e informar los participantes clave en la organización.                                                                                                                            | Mensual (cada semana durante las implementaciones) |               |
| Corrección de la unidad                      | Coordinar los esfuerzos de corrección en toda la organización basándose en los resultados y evaluaciones de QER.                                                                                                                                                                                                           | Según sea necesario                           |               |
| Actualizar los datos de creación de CQD            | Actualizar o agregar nuevas definiciones de edificio en CQD cuando se realizan cambios en la red (consulte la [información de generación de carga](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)). | Según sea necesario                           |               |
| Llenar el papel de calidad campeón      | Responsabilidad de end-to-end para la calidad de la organización. Esto incluye:<ul><li>Asegúrese de que el QER se llevan a cabo con regularidad.</li><li>Informe hacia fuera a los participantes clave en el estado de la calidad.</li><li>Asegurar los datos de creación definiciones están actualizadas.</li><li>Coordinar los esfuerzos de corrección en toda la organización para garantizar que los usuarios tengan una experiencia de alta calidad con los equipos.</li></ul>          | A diario                               |               |



### <a name="references"></a>Referencias 

[Obtenga información acerca de CQD](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Academy?SOFTrainings=Leverage%20the%20Investigate%20Media%20Quality%20using%20CQD%20Videos)

[Información de generación de carga](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)

[Calidad de la Guía de revisión de experiencia](https://aka.ms/qerguide)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>Administrar los extremos

Extremos de Teams de Microsoft pueden definirse como cualquier PC, Mac, Tablet PC o dispositivo móvil (o cualquier otra) que ejecuta al cliente de los equipos. El término *extremo* engloba no sólo el dispositivo sí mismo, pero ¿cómo un usuario se conecta al dispositivo, por ejemplo, mediante micrófono incorporado del dispositivo o altavoces, auriculares o un auricular optimizado. Una vez que estén implementado, no debe olvidarse extremos. Los extremos de los equipos requieren un cuidado continuo y mantenimiento. Las siguientes secciones describen áreas específicas para centrarse en.

### <a name="endpoint-requirements"></a>Requisitos de extremo

Una de las ventajas clave de los equipos es que el cliente se mantiene actualizado automáticamente. Los clientes de PC y Mac se actualizan mediante un proceso de segundo plano que comprueba si hay nuevas compilaciones y descarga al nuevo cliente cuando la aplicación está inactiva. Los equipos de aplicaciones móviles se mantienen actualizadas a través de sus almacenes respectivos de la aplicación.

El cliente de los equipos tiene los requisitos mínimos en cuanto a la plataforma de software subyacente. Estos requisitos pueden cambiar con el tiempo, y por lo tanto, es importante que las supervise para cambios. Por ejemplo, el cliente de los equipos tiene una versión de iOS mínimo. Si el cliente utiliza un explorador de internet, el explorador necesita también estar al día. Encontrará una lista de las plataformas soportadas en [Obtener los clientes de equipos de Microsoft](https://docs.microsoft.com/microsoftteams/get-clients).

### <a name="endpoint-firewalls"></a>Servidores de seguridad de extremo

Firewalls de cliente pueden tener un impacto significativo en la experiencia del usuario.
Firewalls de cliente pueden afectar a la calidad de la llamada e incluso impedir una llamada desde que se estableció. Después de haberse configuradas las exclusiones en el firewall de cliente adecuadas, deben mantenerse actualizados basándose en la información de [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://aka.ms/o365ips). El proveedor tendrá la orientación específica acerca de cómo actualizar las exclusiones.

### <a name="wi-fi-drivers"></a>Controladores de Wi-Fi

Controladores de Wi-Fi podrían ser problemáticos. Por ejemplo, un controlador puede tener muy agresivos comportamientos móviles entre puntos de acceso que pueden inducir innecesario-punto de acceso de conmutación, lo que a la calidad de sonido deficiente. Se podría descubrir un controlador Wi-Fi bajo rendimiento a través de una revisión de calidad de experiencia (consulte [Guía de revisión de calidad de experiencia](https://aka.ms/qerguide) para obtener más detalles). Es fundamental implementar un proceso controlado por la calidad que supervisa los nuevos controladores de Wi-Fi y asegura que probarlos antes de implementarlos en la población general de usuarios.

### <a name="endpoint-management"></a>Administración de extremo

Un catálogo de extremos compatibles y dispositivos de interfaz (como auriculares) debería estar disponibles y mantenimiento. Este catálogo incluirá una lista de los dispositivos aprobados que se han seleccionado y validado como parte de las fases de la fase de incorporación. Normalmente, los dispositivos específicos se seleccionan para cada tipo de persona de la organización y satisface las necesidades de los atributos de ese rol. Todos los extremos tienen un ciclo de vida, y no hay necesidad de administrar los contratos de proveedores, garantía, reemplazo, reparación y distribución de directivas asociadas con estos dispositivos.

### <a name="endpoint-troubleshooting"></a>Solución de problemas de extremo

Incluso si ha seguido las instrucciones anteriores, los usuarios de su organización todavía pueden aparecer problemas con los equipos. Aunque no puede ser el problema con el propio extremo, los síntomas del problema normalmente actúan a través del cliente para el usuario. Las siguientes instrucciones se pretenden proporcionar los pasos generales que puede seguir para resolver el problema; no se pretende ser una guía completa de la solución de problemas. Los pasos que se proporcionan en un orden concreto, pero no tiene que ser seguido de forma explícita y no sería aplicables, según la naturaleza del problema.

1.  **Validar el estado del servicio:** El problema que puede estar experimentando un usuario podría deberse a un evento que afecta de forma negativa al servicio de los equipos o sus servicios dependientes. Como primer paso, le recomendamos que confirme que no hay ningún problema de servicio activo. Consulte [cómo comprobar el estado del servicio Office 365](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0).
    No olvide comprobar el estado de los servicios dependientes (ejemplos; Exchange, SharePoint, OneDrive para el negocio). Supervisar el estado del servicio se describe con más detalle en la sección **servicio de supervisión de salud.**

2.  **Validar la conectividad de cliente:** Problemas de conectividad de causan funcionalidad o problemas de inicio de sesión en los equipos. Se recomienda (especialmente para nuevos sitios o ubicaciones) que valide la conectividad con el servicio. Asegúrese de que siguieron las instrucciones de [las direcciones URL de Office 365 e intervalos de direcciones IP](https://aka.ms/o365ips) siguiente para cada sitio. Puede aprovechar la [Herramienta de evaluación de red de Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para realizar una prueba de conectividad para validar que los puertos de medios se han abierto correctamente para capacidades de voz de la nube. Se proporcionan pasos detallados sobre cómo ejecutar las pruebas de conectividad en la Guía de [Preparación de la red](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#network-readiness) .

3.  **Comprobar la lista de problemas conocidos:** Consulte la [lista de problemas conocidos de los equipos](https://docs.microsoft.com/MicrosoftTeams/known-issues) para determinar si el usuario ha sido afectado negativamente por uno de estos problemas. Siga la solución aportada (si hay alguno) para resolver el problema.

4.  **Comunidad tecnológica de Microsoft, visite:** La [Comunidad tecnológica de equipos de Microsoft](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams) ofrece espacios dedicados para los equipos. La Comunidad de equipos proporciona una lista de discusión, blogs y anuncios centrados en los equipos. Puede exponer una pregunta o buscar discusiones anteriores de soluciones para su problema.

5.  **En contacto con soporte técnico de Microsoft:** Puede ponerse en contacto con Microsoft Support para problemas con equipos en línea o por teléfono. Para obtener información, consulte [contacto soporte para equipos de Microsoft](https://support.office.com/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).
    Para Premier clientes, soporte de solicitudes pueden iniciarse siguiendo las instrucciones proporcionadas en [Contactar con el servicio de equipos de Microsoft (clientes de Premier)](https://support.microsoft.com/premier/contacts).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas diarias/semanales/mensuales/según sea necesario

| Actividad                 | Descripción                                                                                                                                                                                                                                                                                                                                                                     | Cadence   | Equipo asignado |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Requisitos de extremo    | Asegúrese de que extremo los equipos continúa cumpliendo todos los requisitos de software para los equipos [clientes de equipos de Microsoft](https://docs.microsoft.com/microsoftteams/get-clients).                                                                                                                                                                                       | Cada mes   |               |
| Servidores de seguridad de extremo       | Mantener las exclusiones en el servidor de seguridad de extremo basándose en la información en el artículo de [Office 365 URL y los intervalos de direcciones IP](https://aka.ms/o365ips) adecuadas. El proveedor tendrá la orientación específica acerca de cómo mantener las exclusiones. Suscribirse a la [fuente RSS](https://support.office.com/en-us/o365ip/rss) para recibir automáticamente una notificación de cambios. | Según sea necesario |               |
| Controladores de Wi-Fi            | Probar y actualizar los controladores de Wi-Fi en el PC. Validar los resultados mediante CQD ([Guía de revisión de calidad de experiencia](https://aka.ms/qerguide)).                                                                                                                                                                                                                                                                   | Según sea necesario |               |
| Administración de extremo      | Mantener el catálogo de extremos compatibles y dispositivos de interfaz (como auriculares). Administrar contratos de proveedores, garantía, distribución, reemplazo y reparar las directivas.                                                                                                                                                                                                        | Cada mes   |               |
| Solución de problemas de extremo | Solucionar problemas de tareas pueden incluir; comprobación de la conectividad, consulta la lista de problemas conocidos, registro de recopilación, análisis y escalamiento a Microsoft Support o proveedores.                                                                                                                                                                                               | Según sea necesario |               |

### <a name="references"></a>Referencias 

[URL de Office 365 e intervalos de direcciones IP](https://aka.ms/o365ips)

[Obtener clientes para Microsoft Teams](https://docs.microsoft.com/microsoftteams/get-clients)

[Comunidad tecnológica de Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Problemas conocidos de equipos de Microsoft](https://docs.microsoft.com/MicrosoftTeams/known-issues)

[Compruebe el estado del servicio para equipos de Microsoft](https://docs.microsoft.com/microsoftteams/service-health)

[Póngase en contacto con el soporte de Office 365 para empresas: ayuda para administradores](https://support.office.com/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b?ui=en-US&rs=en-US&ad=US)

[Premier de contacto](https://support.microsoft.com/premier/contacts)

[Solución de problemas de los equipos de vídeo](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>Administrar equipos

Después de haber implementado el servicio de Teams de Microsoft, necesita realizar varias actividades relativas a su administración. La gama de actividades de administración del servicio y los usuarios individuales a aprovisionamiento licencias y los números telefónicos y planear la capacidad. En las secciones siguientes se tratan algunas de estas tareas de administración comunes.

### <a name="service-administration"></a>Servicio de administración

El servicio de los equipos tiene varias opciones que pueden configurar todo el arrendatario.
Los cambios realizados en la configuración de inquilinos afectan a todos los usuarios que se han habilitado para los equipos. Para obtener una lista detallada de estos valores, consulte [activar funciones de equipos de Microsoft en su organización de Office 365](https://docs.microsoft.com/microsoftteams/enable-features-office-365).

### <a name="user-administration"></a>Administración de usuarios

Para admitir usuarios, una organización puede requerir cualquier número de tareas relacionadas, las tareas específicas varían de una organización a otra. En última instancia, estas tareas deben ser administrados por un equipo de soporte que se ha asignado a estas tareas operativas. Las siguientes tareas normalmente son necesarios para soportar usuarios en los equipos.

#### <a name="general-tasks"></a>Tareas generales

[Gestionar acceso de los usuarios a Microsoft Teams](https://docs.microsoft.com/microsoftteams/user-access)

#### <a name="common-tasks-for-phone-system"></a>Tareas comunes para el sistema de teléfono

[Asignar, cambiar o quitar un número de teléfono para un usuario](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/assign-change-or-remove-a-phone-number-for-a-user)

[Asignar o cambiar una dirección de emergencia para un usuario](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user)

[Agregar, cambiar o quitar una ubicación de emergencia para su organización](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/add-change-or-remove-an-emergency-location-for-your-organization)

[Crear y administrar planes de marcado](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/create-and-manage-dial-plans)

#### <a name="common-tasks-for-audio-conferencing"></a>Tareas comunes para conferencias de Audio

[Cambiar la configuración de un puente de Audioconferencia](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/change-the-settings-for-an-audio-conferencing-bridge)

[Cambiar los números de teléfono de su puente de Audioconferencia](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge)

[Administrar la configuración de Audioconferencia para un usuario](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/manage-the-audio-conferencing-settings-for-a-user)

[Restablecer el PIN de Audioconferencia para un usuario](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/reset-the-audio-conferencing-pin-for-a-user)

### <a name="license-management"></a>Administración de licencias

Que su organización crezca o contratos, es importante que planee licencias para las necesidades actuales y futuras. No hay una licencia básica de equipos, además de licencias para las capacidades de voz de nube ([Sistema de teléfono](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system?ui=en-US&rs=en-US&ad=US) y [Conferencias de Audio](https://products.office.com/skype-for-business/audio-conferencing)).

Para los equipos, licencias del sistema de teléfono requieren licencias de [Plan de llamadas](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365) asociadas. Llamar a Plan de licencias permite realizar y recibir llamadas nacionales o internacionales. Estos planes están basados en el uso y minutos grupos asociados a ellas. Provisioning [Créditos de comunicaciones](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) se asegurará de que nunca se quede sin servicio.

Conferencias de audio permite conferencia telefónica de peaje y servicios de conferencia nacional de acceso telefónico de salida. Conferencia de acceso telefónico gratuito o escenarios de acceso telefónico de salida no domésticos pueden provocar que incurrir en gastos adicionales para los [Créditos de comunicaciones](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) son necesarios.

Créditos de comunicaciones pueden complementar licencias de Plan de llamadas y conferencias de Audio. Plan de llamadas licencias y créditos de comunicación están basada en el uso y, por tanto, necesitan ser supervisados y provisioning correspondiente para.

Puede aprovechar el [informe de uso de RTC](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) para ayudarle a supervisar el uso de Plan de llamadas minutos y créditos de comunicaciones. Basándose en los resultados de esta actividad, se puede ajustar en consecuencia la concesión de licencias. Próximamente, ofreceremos un informe del [grupo de minuto PSTN](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) para ayudar más eficazmente con esta tarea.

### <a name="telephone-number-management"></a>Gestión de números de teléfono

Existen dos métodos para adquirir números en equipos: puede trasladar los números de teléfono de otro proveedor, o pueden aprovisionar los números directamente del inventario número de Microsoft. Ambos métodos se describen en la [obtención de números de teléfono de los usuarios](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users).

Hay un límite para la cantidad de números de teléfono que pueden aprovisionar del inventario número de Microsoft. Los límites se determinan mediante una serie de factores que se detallan en [cuántos números de teléfono puede obtener](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get).
Los límites dependen del tipo de números: sin cargo servicio números, números de teléfono de servicio y números de suscriptor (usuario). Cada uno tiene sus propios límites y debe administrarse de forma independiente. Si se encuentra cerca del límite (o ha alcanzado el límite), puede aplicar un incremento en el límite. Este proceso se describe en el artículo anterior.

Puede haber ocasiones cuando un número no está disponible para hacer provisioning en una región donde el servicio está disponible. Para obtener información sobre el proceso de solicitud de números, vea [administrar números de teléfono para su organización](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).

### <a name="team-creation-optional"></a>Creación del equipo (opcional)

De forma predeterminada, todos los usuarios con un buzón en Exchange Online tienen permisos para crear grupos de Office 365 y, por tanto, un equipo de Microsoft Teams. Si desea tener un control más estricto y [restringir la creación de nuevos equipos](https://docs.microsoft.com/MicrosoftTeams/assign-roles-permissions#permissions-to-create-teams) (y, por tanto, la creación de nuevos grupos de Office 365), puede delegar la creación de grupos y derechos de administración a un conjunto de administradores. Si su organización desea ejercer esta opción, vea el proceso descrito en este artículo para permitir que los usuarios envíen solicitudes procesadas por un equipo asignados.

<!--ENDOFSECTION-->

## <a name="dailyweeklymonthlyas-needed-tasks"></a>Tareas diarias/semanales/mensuales/según sea necesario

| Actividad                    | Descripción                                                                                                                                                                                                                                                                                                                                                                                                             | Cadence   | Equipo asignado |
|-----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Servicio de administración      | Administración de la configuración de equipos de todo el arrendatario.                                                                                                                                                                                                                                                                                                                                                                           | Según sea necesario |               |
| Administración de usuarios         | Administración de la configuración de usuario y licencias en los equipos.                                                                                                                                                                                                                                                                                                                                                           | Según sea necesario |               |
| Administración de licencias          | Planear las necesidades actuales y futuras para el usuario y basado en el consumo de licencias (planes de llamada y comunicación créditos) aprovechando el informe [informe de uso PSTN](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) y [grupo minuto PSTN](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) . | Cada semana    |               |
| Gestión de números de teléfono | Administrar los números de teléfono disponibles para el crecimiento futuro y ajustar los niveles de inventario para satisfacer las necesidades de su organización.                                                                                                                                                                                                                                                                                                | Cada semana    |               |
| Creación del equipo (opcional)    | Proceso de revisión y solicitudes de creación del equipo.                                                                                                                                                                                                                                                                                                                                                                          | Según sea necesario |               |

<!--ENDOFSECTION-->

## <a name="quality-of-experience-review-guide"></a>Calidad de la Guía de revisión de experiencia
La Guía de revisión de calidad de experiencia tiene un conjunto de actividades que evaluar y proporcionar orientaciones sobre correcciones en áreas clave que tienen el mayor impacto para mejorar la experiencia del usuario, como se muestra en la figura siguiente.

![Revisión de las áreas clave para examinar durante una calidad experimentan: audio, confiabilidad y resultados de la encuesta.] (media/plan-my-service-management-image2.png "Revisión de las áreas clave para examinar durante una calidad experimentan: audio, confiabilidad y resultados de la encuesta.")

Continuamente evaluar y remediar las zonas descritas en este documento, podrá reducir su potencial de afectar negativamente a la experiencia del usuario. Problemas de experiencia de usuario más encontrados en una implementación pueden agruparse en las siguientes categorías:

-   Configuración de firewall o proxy incompleto

-   Mala cobertura Wi-Fi

-   No hay suficiente ancho de banda

-   VPN

-   Uso de dispositivos de audio integrados o no optimizados

-   Subredes problemáticas o dispositivos de red

Las instrucciones proporcionadas en la Guía de revisión de experiencia de calidad se centra en usar Online llame calidad Dashboard (CQD) como herramienta principal para informar e investigar cada área descrita, con énfasis en audio para maximizar la adopción y el impacto. Se traducirá también directamente cualquier optimizaciones realizadas a la red para mejorar la experiencia de sonido a mejoras en el uso compartido de escritorio y vídeo.

Recomendamos encarecidamente que se nombra al Campeón de calidad desde el principio. Después de que se ha designado, deberían empezar a familiarizarse con el contenido de la [Guía de revisión de experiencia de calidad](https://aka.ms/qerguide).

<!--ENDOFSECTION-->