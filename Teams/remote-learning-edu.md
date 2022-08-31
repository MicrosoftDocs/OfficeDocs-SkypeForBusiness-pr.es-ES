---
title: Introducción a Microsoft Teams para el aprendizaje remoto
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith, lakuan
description: Guía de inicio de aprendizaje remoto de Microsoft Teams para el ámbito educativo
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 231007549102b8cddc02a0d2a5d29266662b4b2f
ms.sourcegitcommit: 7a1fb6e15c21368afa34cd212865437781f721e2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466028"
---
# <a name="get-started-with-microsoft-teams-for-remote-learning"></a>Introducción a Microsoft Teams para el aprendizaje remoto

Este artículo trata sobre los pasos de administración de TI para configurar su institución educativa para el aprendizaje remoto con Microsoft Teams.

En Teams, **los profesores** pueden:

- Converse rápidamente con los alumnos.
- Compartir archivos y sitios web.
- Cree blocs de notas de clase de OneNote.
  - Organice lecciones interactivas.
  - Proporcione comentarios eficaces y oportunos.
- Distribuya y califique tareas.
- Compartir material didáctico en Comunidades profesionales de aprendizaje.

**Los administradores del sector educativo y el personal** pueden:

- Mantente al día de los eventos.
- Colabore con equipos de docentes para anuncios y conversaciones temáticas.

# <a name="accounts--licenses"></a>[Cuentas & licencias](#tab/accounts)

## <a name="user-accounts-licenses-and-identity-security"></a>Cuentas de usuario, licencias y seguridad de la identidad

Teams usa Microsoft 365 para autenticar usuarios y proporcionar servicios. Todos los usuarios deben tener establecidas identidades de Microsoft 365 para facilitar la colaboración.

Si aún no existen identidades de usuario, siga este proceso para establecerlas:

1. [Crear usuarios con School Data Sync](/microsoft-365/education/deploy/school-data-sync).
2. [Asignar licencias a usuarios](teams-edu-licensing.md).
3. [Crear grupos de Microsoft 365](Office-365-groups.md).
4. [Configurar Exchange](Exchange-Teams-interact.md).
5. [Configure SharePoint y OneDrive](SharePoint-OneDrive-interact.md).
6. [Configure los usuarios que tengan el correo electrónico de Google](/microsoft-365/education/deploy/enabling-teams-for-education-for-google-users).

Microsoft Teams se incluye en todos los planes de Microsoft 365, incluido el plan educativo gratuito A1.

Para obtener instrucciones sobre cómo implementar Microsoft 365 y configurar Teams, consulte [Crear su inquilino de Microsoft 365](/microsoft-365/education/deploy/create-your-office-365-tenant).

# <a name="set-up-teams"></a>[Configurar Teams](#tab/setup)

## <a name="easily-set-up-teams"></a>Configurar Teams fácilmente

Estas son las dos cosas que debe hacer para empezar a trabajar con Teams:

### <a name="1-allow-users-to-create-teams"></a>1. Permitir que los usuarios creen equipos

**De forma predeterminada, todos los usuarios pueden crear grupos de Microsoft 365 y Teams**, pero es posible que esta capacidad no siempre sea apropiada.

Por ejemplo, es posible que algunas escuelas quieran restringir la creación de Teams por parte de los alumnos sin supervisión. La creación de grupos y equipos de Microsoft 365 se puede [restringir a determinados grupos de seguridad](/microsoft-365/admin/create-groups/manage-creation-of-groups).

Para las instituciones de educación superior, recomendamos permitir que todos los usuarios, incluidos los estudiantes, creen equipos para clases, investigaciones, proyectos de grupo y grupos de estudio.

Para obtener un tutorial sobre cómo crear Teams, vea [Crear un equipo de clase en Microsoft Teams](https://support.office.com/article/create-a-class-team-in-microsoft-teams-preview-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b).

### <a name="2-configure-user-experiences-using-policies"></a>2. Configurar experiencias de usuario mediante directivas

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> Consulte [Mantener a los alumnos seguros en Teams para el aprendizaje a distancia](https://support.office.com/article/f00fa399-0473-4d31-ab72-644c137e11c8).
>
> Si desea ver nuestras recomendaciones de directivas educativas, consulte [Directivas y paquetes de directivas de Teams para Educación](policy-packages-edu.md).

Las directivas de Teams controlan las capacidades disponibles para usuarios o grupos específicos. Las directivas pueden definir quién debe poder usar el chat privado, las llamadas privadas, la programación de reuniones, los tipos de contenido que se pueden compartir y mucho más.

**El personal de educación superior, los educadores y los estudiantes** pueden usar las directivas predeterminadas (globales). Puede ajustar las directivas para agregar más funciones a Teams, incluidas [las capacidades de traducción](messaging-policies-in-teams.md#messaging-policy-settings) y [la transcripción automática de reuniones](meetings-policies-recording-and-transcription.md#transcription).

**Es posible que los alumnos de la escuela primaria y secundaria** necesiten funcionalidades restringidas. Se recomienda que los cambios en la directiva de los estudiantes se realicen en la directiva "Global (predeterminado para toda la organización)".

**El personal y los formadores de la escuela primaria y secundaria deben tener asignadas directivas** que concedan funcionalidades clave, como permitir la programación de reuniones y chats privados. [Asigne estas directivas de forma masiva al personal y los formadores](batch-group-policy-assignment-edu.md).

> [!IMPORTANT]
> Para las directivas de reunión asignadas a cualquier usuario, se recomienda establecer la opción **Admitir automáticamente a personas** **en Todos los usuarios de la organización**. Esto garantizará que los usuarios no autenticados deben ser admitidos desde la sala de espera antes de que puedan unirse a las reuniones de Teams.
>
> Para más información, consulte [Administrar directivas de reunión en Teams](meeting-policies-participants-and-guests.md#automatically-admit-people).

# <a name="class-teams"></a>[Equipos de clase](#tab/class-teams)

## <a name="create-class-teams-for-secure-classroom-use"></a>Creación de equipos de clase para el uso seguro del aula

Microsoft Teams para el ámbito educativo ofrece [tipos de equipos específicos](https://support.office.com/article/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67)  para uso educativo. El [tipo de equipo de clase](https://support.office.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b) está diseñado para aulas y tiene características específicas que prestan apoyo a las necesidades del aula, como:

- Asignaciones.
- Grados.
- Bloc de notas de clase de OneNote.
- [Carpeta Materiales](https://support.office.com/article/Use-folders-to-create-read-only-files-for-students-or-other-team-members-0e7791d7-8c9c-4749-9bca-984289477988)  de clase para proteger el contenido de solo lectura para los alumnos.
- [Insights](./class-insights.md) para ofrecer datos en tiempo real sobre la participación, las tareas y el bienestar de los estudiantes de cada aula.
- [El profesor primero tiene acceso](https://support.microsoft.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78) para configurar la clase antes de agregar a los alumnos.
- La capacidad de silenciar a los alumnos molestos y otros permisos especiales.

Los equipos de clase se pueden crear a través de:

- [School Data Sync (SDS).](#automatic-team-creation-using-sds)
- [Creación dirigida por un formador con grupos de clase de Microsoft 365](#educator-led-team-creation-from-microsoft-365-class-groups).
- [Scripts de PowerShell con API de Graph](#powershell-script-using-graph-apis).
- [Creación manual de equipos](#manual-team-creation).

Repasaremos varias opciones para ayudarle a elegir la ruta de acceso de implementación adecuada que se ajuste mejor a sus necesidades.

### <a name="automatic-team-creation-using-sds"></a>Creación automática de equipos con SDS

[School Data Sync (SDS)](/SchoolDataSync) lee los datos del sistema de registro de una institución, como un sistema de información de estudiantes (SIS) o un sistema de administración del aprendizaje (LMS).

SDS puede importar datos desde cualquier sistema de registro y tiene conectores integrados a muchos [proveedores de SIS](/schooldatasync/frequently-asked-questions#what-sismis-vendors-does-school-data-sync-support).  

#### <a name="benefits-of-sds"></a>Ventajas de SDS

- Crea automáticamente usuarios y aplica licencias.
- Crea y mantiene automáticamente equipos de clase.
- Se sincroniza con SIS/LMS para mantener los cambios de pertenencia de los alumnos.
- [Permite a los profesores preparar clases antes de agregar alumnos](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78).
- Puede crear automáticamente grupos de seguridad.
- Crea unidades administrativas para la delegación administrativa de ámbito.
- [Permite restablecer la contraseña del formador](/schooldatasync/how-to-enable-teacher-password-reset).
- Tiene funcionalidades integradas de limpieza para cambiar el nombre y archivar grupos y equipos.
- [Sincroniza calificaciones de Teams con SIS](/schooldatasync/grade-sync).
- [Protege los datos personales de los estudiantes](/schooldatasync/protecting-student-personal-data).
- Realiza un seguimiento y administra el consentimiento de tutores.
- Proporciona mejores datos de Insights para Educación.

#### <a name="considerations-for-sds"></a>Consideraciones para SDS

SDS crea equipos en dos pasos:

1. SDS crea un grupo de Microsoft 365 en Azure Active Directory (Azure AD).
2. SDS convierte automáticamente ese grupo en un equipo.

El segundo paso de creación de equipos es opcional en SDS. Es posible que un administrador no quiera crear automáticamente equipos en función del tiempo de implementación y el número de equipos sin usar que puedan resultar. En su lugar, vea el [método de creación de equipos dirigido por el formador](#educator-led-team-creation-from-microsoft-365-class-groups).  

#### <a name="get-started-with-sds"></a>Introducción a SDS

Para empezar, vaya a [School Data Sync (SDS)](/SchoolDataSync) y póngase en contacto con [https://aka.ms/sdssupport](https://aka.ms/sdssupport) para obtener asistencia gratuita para la implementación.  

### <a name="educator-led-team-creation-from-microsoft-365-class-groups"></a>Creación de equipos dirigidos por un formador a partir de grupos de clase de Microsoft 365

La creación de equipos dirigida por un formador facilita a los formadores la creación de las clases que necesitan.  

Este enfoque le permite usar SDS para crear grupos para cada clase (recomendado) o usar [Graph API](/graph/api/educationroot-post-classes) para crearlos por su cuenta.

Después de preparar los grupos de clase, los formadores pueden convertir sus grupos en equipos:

1. Seleccione la pestaña Equipos en Teams.
2. En la parte superior del cliente, seleccione el icono **Clases sugeridas** .

#### <a name="benefits-of-educator-led-team-creation"></a>Ventajas de la creación de equipos dirigida por un formador

- Las clases se prepararán y sugerirán, pero no se crearán, a menos que el educador desee usarlas.
- Para las instituciones con más de 500 000 equipos, este método reduce el número de equipos innecesarios.
- [Ventajas de SDS](#benefits-of-sds).
- Graph API ventajas.
  - Proporciona a los formadores el control sobre qué clases se crean.
  - No requiere integración con SDS.

#### <a name="considerations-for-educator-led-team-creation"></a>Consideraciones para la creación de equipos dirigida por un formador

- No es completamente automática y requiere algunas acciones de los profesores.
- Los profesores que no tienen permiso para crear equipos pueden [seguir creando equipos a partir de grupos existentes](https://support.office.com/article/create-a-class-team-in-microsoft-teams-preview-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b).
- Graph API requiere un alto nivel de conocimientos técnicos, tiempo para crear y ejecutar el script y tiempo para solucionar cualquier problema.

#### <a name="get-started-with-educator-led-team-creation"></a>Introducción a la creación de equipos dirigida por un formador

Para empezar a usar el método de SDS, vaya a [School Data Sync (SDS)](/SchoolDataSync) y póngase en contacto con [https://aka.ms/sdssupport](https://aka.ms/sdssupport) ellos para obtener asistencia gratuita de implementación.

- Tendrá que desactivar la creación automática de equipos en su perfil de SDS.
- Puede usar una combinación de creación de equipos automática y dirigida por el formador para los equipos de clase mediante dos perfiles de SDS.

Para usar el método de la API de Graph, consulte [API de Graph](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-1.0&preserve-view=true) y [Crear un equipo de clase](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-beta&preserve-view=true).  

### <a name="powershell-script-using-graph-apis"></a>Script de PowerShell con la API de Graph

Con PowerShell, puede escribir un script para crear equipos y canales, y configurar la configuración automáticamente.

Este método requiere que el administrador [primero cree el grupo, agregue educadores y alumnos y, después, cree el equipo](/graph/teams-create-group-and-team).

También puede usar la [Graph API de Microsoft para crear, configurar, clonar y archivar equipos](/graph/api/resources/teams-api-overview).

#### <a name="benefits-of-powershell-scripts"></a>Ventajas de los scripts de PowerShell

- Proporciona a los administradores de TI el control sobre la creación de clases.
- Opción de crear equipos con acceso anticipado para profesores o acceso inmediato de los alumnos a los equipos.
- [Sincroniza los cambios de pertenencia de los alumnos al grupo de Azure AD](/graph/api/team-post?tabs=http&view=graph-rest-beta#example-4-create-a-team-from-group&preserve-view=true).

#### <a name="considerations-for-powershell-scripts"></a>Consideraciones para scripts de PowerShell

- Requiere un alto nivel de conocimiento técnico y tiempo para crear y ejecutar el script y solucionar los problemas al crear grupos de clase.
- Sin control integrado de errores ni lógica de reintentos.
- Los cambios de pertenencia no se sincronizan con SIS.

> [!NOTE]
> Los equipos de clase requieren suscripción al grupo oculta para que solo los profesores y los alumnos de la clase puedan ver a los miembros de esa clase. Para crear un grupo de clase de Microsoft 365, vea [Crear un equipo de clase](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-beta&preserve-view=true) para cumplir los requisitos de privacidad.

### <a name="manual-team-creation"></a>Creación de equipos manual

Los usuarios pueden adaptar su experiencia de Teams al tener la capacidad de crear sus propios equipos.

Según los permisos de un usuario, puede:

- [Configure sus propios equipos e invite a usuarios, incluidos los alumnos](https://support.microsoft.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b#ID0EADAAA=Create_a_team_from_scratch).
- [Agregue manualmente usuarios al equipo](https://support.office.com/article/add-a-student-to-a-class-team-b88263bb-ace1-4702-8a48-f8a2cf4af954).
- [Compartir un código para unirse](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f).
- [Compartir un vínculo al equipo](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f).

Es mejor que los formadores agreguen sus alumnos al equipo para asegurarse de que los alumnos obtienen acceso y reciben una notificación de que se les ha agregado.

#### <a name="benefits-of-manual-team-creation"></a>Ventajas de la creación manual de equipos

- Proporciona a los formadores el control total de la creación de la clase.
- Los equipos de clase se crean inmediatamente.

#### <a name="considerations-for-manual-team-creation"></a>Consideraciones para la creación manual de equipos

- Requiere acciones y tiempo del profesor.
- La pertenencia a alumnos no se sincroniza con SIS y requiere administración manual.
- Los alumnos obtendrán acceso inmediato a los equipos de clase.

### <a name="recommended-best-practices"></a>Procedimientos recomendados

- Implementación anticipada para asegurarse de que todo funciona de forma segura y está listo el primer día de clase.

- Para los problemas con la creación automática de equipos de SDS, los formadores pueden usar el [método de creación de equipos dirigido por el formador](#educator-led-team-creation-from-microsoft-365-class-groups) para reintentar. [La creación manual de equipos](#manual-team-creation) es otra solución, pero las clases no se sincronizarán con SIS.

- El límite de equipos del espacio empresarial es 500 000 equipos. Por lo tanto, los administradores deben reducir el número de equipos sin usar para evitar alcanzar estos límites. Para obtener más información, consulte [Límites y especificaciones de Microsoft Teams](limits-specifications-teams.md).  

# <a name="educator-early-access"></a>[Acceso anticipado del formador](#tab/early-access)

## <a name="early-access-to-class-teams"></a>Acceso anticipado a los equipos de clase

Los equipos de clase con acceso anticipado permiten a los profesores acceder a sus equipos de clase antes de que los alumnos puedan verlo. Los profesores tendrán tiempo para configurar, agregar archivos y organizarse antes de conceder acceso a sus alumnos.

Cuando estén listos para que los alumnos accedan al equipo, podrán [activar la clase](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78).

### <a name="how-do-i-create-class-teams-that-allow-educators-early-access-to-set-up-a-team-before-admitting-students"></a>¿Cómo puedo crear equipos de clase que permitan acceso anticipado a los profesores para configurar un equipo antes de admitir a los alumnos?

Los equipos creados a partir de grupos (a través de SDS, dirigidos por profesor o API de Graph) crean automáticamente equipos de acceso anticipado de forma predeterminada.

Para crear sus propios equipos de acceso anticipado mediante la API de Graph, tendrá que [crear una clase](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-beta&preserve-view=true) y [crear el equipo desde un grupo](/graph/api/team-post?tabs=http&view=graph-rest-beta#example-4-create-a-team-from-group&preserve-view=true).

### <a name="how-do-i-check-if-a-class-is-activated"></a>¿Cómo puedo comprobar si una clase está activada?

En el [tipo de recurso de equipo](/graph/api/resources/team?view=graph-rest-beta&preserve-view=true), vea la [propiedadMembershipLimitedToOwners](/graph/api/resources/team?view=graph-rest-beta#properties&preserve-view=true) para ver si una clase está activada.

Use la [API de obtener equipo](/graph/api/team-get?tabs=http&view=graph-rest-beta&preserve-view=true) para consultar la ```isMembershipLimitedToOwners``` propiedad de una clase específica. Si el equipo está activado devolverá el valor de falso. Si el equipo no se ha activado, devolverá un valor de true.

### <a name="how-do-i-activate-a-class-for-an-educator"></a>¿Cómo puedo activar una clase para un profesor?

Use la [API actualizar equipo](/graph/api/team-update?tabs=http&view=graph-rest-beta&preserve-view=true) y establezca la ```isMembershipLimitedToOwners``` propiedad en false para activar el equipo en nombre del educador. Una vez activado un equipo, no se puede revertir.

### <a name="create-staff-teams-for-staff-communication-and-collaboration"></a>Crear equipos de personal para las comunicaciones y colaboraciones del mismo

[Los equipos de tipo de personal](https://support.office.com/article/create-a-staff-team-in-microsoft-teams-314ac9d5-36a9-408e-8ae4-7ef20e9f1ddf) son para que los administradores y el personal educativo compartan información y trabajen conjuntamente en iniciativas de todo el instituto.

Los administradores del ámbito educativo pueden agregar personal al equipo con el asistente para la creación de equipos, [agregando miembros después de crear el equipo](https://support.office.com/article/add-members-to-a-team-in-teams-aff2249d-b456-4bc3-81e7-52327b6b38e9) o [compartiendo un código de unión o un vínculo al equipo](https://support.office.com/article/create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f).

# <a name="meeting-scenarios"></a>[Escenarios de reunión](#tab/scenarios)

## <a name="teams-meeting-scenarios"></a>Escenarios de reuniones de equipos

### <a name="collaborative-meetings-for-virtual-classes"></a>Reuniones de colaboración para clases virtuales

[Las reuniones de Microsoft Teams](./tutorial-meetings-in-teams.yml) admiten hasta 250 asistentes simultáneos, con la capacidad de usar audio, vídeo, [compartir contenido](https://support.office.com/article/show-your-screen-during-a-meeting-90c84e5a-b6fe-4ed4-9687-5923d230d3a7), pizarras y notas.

Las reuniones pueden ser:

- [Programado en el cliente de Teams](./tutorial-meetings-in-teams.yml).
- Grabado y guardado para que los asistentes lo revisen más tarde.
- [Transcripción para encontrar fácilmente contenido](https://support.office.com/article/Microsoft-Stream-automatically-creates-closed-captions-for-videos-8d6ac353-9ff2-4e2b-bca1-329499455308).
- Se puede acceder con una cámara web, micrófono y altavoz de un portátil o teléfono móvil.
- [Optimizado para dispositivos específicos](https://products.office.com/microsoft-teams/across-devices/devices).
- Finalizó para todos los participantes para asegurarse de que los alumnos no están en una reunión sin supervisión.

### <a name="districtuniversity-events-or-updates"></a>Eventos y actualizaciones del distrito/universitarios

Algunas reuniones tienen una gran audiencia y necesidades de producción adicional. Estas reuniones suelen tener un presentador, productores, y una sección de preguntas y respuestas con moderador.

Teams es compatible con estas sesiones mediante [eventos en directo de Microsoft Teams](teams-live-events/what-are-teams-live-events.md).

Los eventos en directo se pueden usar para escenarios, como:

- Actualizaciones en todo el distrito o en toda la universidad.
- Direcciones de liderazgo.
- Instrucciones para clases grandes o grupos de alumnos.
- Ampliar a su comunidad.

Obtenga información sobre cómo realizar sesiones en directo en:

- [Planee y programe un evento en directo](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502).
- [Produzca un evento en directo](https://support.office.com/article/video-produce-a-live-event-34c89e79-ffd4-4a6a-baf6-77055e0709cb).
- [Asista a un evento en directo](https://support.office.com/article/video-attend-a-live-event-d837ad8d-ce34-44d0-9744-9beb50e943ac).
- [Moderar una&A de preguntas](https://support.office.com/article/video-moderating-a-q-a-4984e582-8c66-4ea3-aaaf-d93cf62e1b76) y preguntas.

# <a name="resources"></a>[Recursos](#tab/resources)

## <a name="support-resources"></a>Recursos de soporte técnico

Para obtener información general genérica sobre la transición al aprendizaje remoto, [empiece aquí](https://www.microsoft.com/education/remote-learning)

Si es administrador de TI, educador, estudiante o tutor, estos recursos pueden ayudarle a usar Teams:

- **Administradores de TI**
  - [Características de Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).
  - [Descargue y distribuya clientes de Teams](get-clients.md).
  - [Solución de problemas de Teams](/MicrosoftTeams/troubleshoot/teams).
  - [Teams para infraestructura de escritorio virtualizada](./teams-for-vdi.md).
  - [Supervisar y administrar la calidad de las llamadas](monitor-call-quality-qos.md).
  - [Compruebe el estado del servicio para Teams](service-health.md).
  - [Optimice el tráfico de Microsoft 365 para el personal remoto](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571).
  - [Contactos de soporte técnico para Teams](/microsoft-365/admin/contact-support-for-business-products).
  - [Teams para Educación seminarios web](https://aka.ms/TeamsEDUWebinars).

- **Formadores**
  - [Centro de ayuda para formadores](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114).
  - [Ayuda de aprendizaje remoto](https://aka.ms/RemoteLearningHelp).
  - [Descargue Teams](get-clients.md).
  - [Teams para Educación seminarios web](https://aka.ms/TeamsEDUWebinars).
  - [Curso en línea para formadores que usan Teams](https://education.microsoft.com/course/9c9f5c11/overview).
  - [Curso en línea para crear entornos de aprendizaje colaborativo con Teams](https://education.microsoft.com/course/b1e15cfc/overview).
  - [Registra una incidencia de soporte](https://www.microsoft.com/microsoft-teams/download-app) técnico.

- **Estudiantes**
  - [Centro de ayuda para alumnos](https://support.office.com/article/student-help-center-395ab230-55bf-44c6-b265-e832d729b694).
  - [Ayuda de aprendizaje remoto](https://aka.ms/RemoteLearningHelp).
  - [Descargue Teams](https://www.microsoft.com/microsoft-teams/download-app).

- **Guardianes**
  - [Ayuda de aprendizaje remoto](https://aka.ms/RemoteLearningHelp).
  - [Descargue Teams](https://www.microsoft.com/microsoft-teams/download-app).

---
