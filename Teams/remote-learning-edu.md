---
title: Recursos de Microsoft Teams para administradores de educación
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.reviewer: karsmith
ms.topic: reference
ms.service: msteams
audience: admin
description: Guía de inicio de aprendizaje remoto de Microsoft Teams para EDU.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 87d9e36578227c8f27acfdfd07abfa0cadbe69b7
ms.sourcegitcommit: f23c428043bb0b37c9a8600e64691bc2a1f2e874
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2020
ms.locfileid: "42403846"
---
# <a name="get-started-with-microsoft-teams-for-remote-learning"></a>Introducción a Microsoft Teams para aprendizaje remoto

Microsoft Teams es una plataforma que ofrece a las conversaciones, el contenido, las asignaciones y las aplicaciones en un solo lugar. Cree clases de colaboración, conéctese en comunidades profesionales de aprendizaje y póngase en contacto con colegas desde una sola experiencia.

Use los procedimientos recomendados de este artículo para empezar a usar Microsoft Teams para sus necesidades educativas para habilitar capacidades de aprendizaje remoto. Microsoft Teams se puede usar para habilitar la colaboración de clase con alumnos en conversaciones, proporcionar una plataforma virtual de reuniones y distribuir tareas. Los administradores y el personal de la escuela pueden mantenerse al día y colaborar con los equipos de anuncios y conversaciones temáticas. Los educadores pueden compartir material de instrucciones usando comunidades profesionales de aprendizaje.

Microsoft Teams tiene [clientes](get-clients.md) disponibles para equipos de escritorio (Windows, Mac y Linux), Web y móviles (Android e iOS) para asegurarse de que todo el personal y los alumnos puedan estar conectados.

Obtenga más información sobre los escenarios de uso de Microsoft Teams en la [serie de webinars de Teams para el ámbito educativo](https://aka.ms/TeamsEDUWebinars).

## <a name="user-accounts-licenses-and-identity-security"></a>Cuentas de usuario, licencias y seguridad de identidad

Microsoft Teams aprovecha las capacidades de Microsoft 365 para autenticar usuarios y proporcionar servicios. El personal, los instructores y los alumnos deben tener identidades establecidas para facilitar la colaboración. Si las identidades aún no existen, siga este proceso para establecerlas.

Las [licencias de Teams deben habilitarse para los usuarios antes de](user-access.md) que puedan empezar a usar las funciones de Teams. Teams se basa en capacidades adicionales de Microsoft 365 como [Office 365 Groups](Office-365-groups.md), [Exchange](Exchange-Teams-interact.md), [SharePoint y OneDrive](SharePoint-OneDrive-interact.md) para habilitar escenarios de colaboración. Los usuarios obtienen la mejor experiencia de los equipos si todos estos servicios también están habilitados. [Teams es compatible con los usuarios que tienen correo electrónico hospedado por Google](https://docs.microsoft.com/microsoft-365/education/deploy/enabling-teams-for-education-for-google-users).

## <a name="easily-set-up-microsoft-teams"></a>Configurar fácilmente Microsoft Teams

Estas son las dos cosas que debe hacer para empezar a trabajar con Teams:

### <a name="1-allow-users-to-create-teams"></a>1. permitir que los usuarios creen equipos

Los estudiantes y los educadores podrán sacar el máximo partido a los equipos cuando puedan usarlo con las barreras mínimas y disponer de la flexibilidad para adaptarlos a sus necesidades. Una de las formas en que los usuarios pueden personalizar la experiencia de su equipo es tener la capacidad de crear equipos que se ajusten a sus necesidades. De **forma predeterminada, todos pueden crear grupos y equipos de Office 365**. Hay ocasiones en las que esta capacidad puede no ser adecuada; por ejemplo, es posible que algunos clientes deseen restringir la creación de equipos a los alumnos principales. Si es necesario, la creación de equipos y grupos de Office 365 se puede [restringir a determinados grupos de seguridad](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups) dentro de su entorno.

Los clientes de educación superior se benefician cuando permite a todos los usuarios, incluidos estudiantes, crear equipos para clases, investigaciones, proyectos de grupo y grupos de estudio. Las escuelas primarias y secundarias pueden impedir que los estudiantes creen equipos para asegurarse de que todas las comunicaciones entre los estudiantes se encuentren en un foro que incluya a un adulto. En este caso, la creación del equipo y el grupo de Office 365 se puede restringir a todos los educadores y el personal.

### <a name="2-configure-user-experiences-using-policies"></a>2. configurar las experiencias del usuario mediante directivas

[Las directivas de Teams](teams-policies.md) proporcionan la capacidad de controlar las opciones disponibles para usuarios específicos o grupos de usuarios. Se pueden aplicar directivas para definir a quién se le debe permitir el uso de chats privados, llamadas privadas, programación de reuniones, tipos de contenido que pueden compartirse y mucho más.

El **personal educativo, los educadores y los estudiantes** se benefician de las capacidades incluidas en las directivas predeterminadas (globales). Algunas opciones de directiva adicionales se pueden habilitar para agregar más funciones a Microsoft Teams, entre las que se incluyen [la habilitación de funciones de traducción en la Directiva de mensajería](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams#messaging-policy-settings) y la transcripción de reuniones automática en la Directiva de la reunión.

Es posible que **los estudiantes principales y secundarios de la escuela** necesiten capacidades restringidas para los alumnos. Las directivas establecen límites sobre lo que pueden hacer los alumnos. Puesto que la población de alumnos suele ser el mayor conjunto de usuarios y, a menudo, recibe la configuración más restrictiva, se recomienda que se realicen cambios en la política del estudiante en las directivas "globales (valor de toda la organización)".

Aquí tiene un conjunto de configuraciones comunes de directivas no predeterminadas que se asignarán a los alumnos principales y secundarios para limitar la comunicación no moderada entre alumnos:

#### <a name="messaging-policy"></a>Directiva de mensajería

- Conjunto de cambios en "deshabilitado"
- La clasificación de contenido de Giphy establecida en ' STRICT '
- Traducir mensajes establecidos en ' activado '
- Enviar mensajes urgentes con las notificaciones prioritarias establecidas en ' OFF '
- Quitar usuarios de los chats grupales establecidos en ' OFF '

#### <a name="meeting-policy"></a>Política de reuniones

- Permitir reunirse ahora en los canales establecidos en ' OFF '
- Permitir el conjunto de complementos de Outlook como ' OFF '
- Permitir programación de reuniones de canal establecida en ' deshabilitado '
- Permitir la programación de reuniones privadas establecer en ' deshabilitado '
- Permitir reunirse ahora en reuniones privadas establecer en ' deshabilitado '

#### <a name="live-events-policy"></a>Directiva de eventos en directo

- Permitir la programación establecida en ' deshabilitado '

#### <a name="calling-policy"></a>Directiva de llamadas

- Establecer llamadas privadas en "desactivado"

#### <a name="teams-policy"></a>Directiva de Teams

- Crear canales privados establecidos en ' OFF '

Los **educadores y el personal de la escuela principal** deberían tener directivas que otorguen las capacidades básicas que se pueden restringir a los alumnos. Crear nuevas directivas que permitan la programación de reuniones y chats privados (la configuración predeterminada de una nueva directiva). [Asigne estas directivas a su personal y educadores a través de la pertenencia a grupos de seguridad](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group).

## <a name="start-using-teams"></a>Empezar a usar Teams

### <a name="create-class-teams-for-secure-classroom-use"></a>Crear equipos de clase para el uso seguro del aula

Microsoft Teams para el ámbito educativo ofrece [tipos de equipo específicos](https://support.office.com/article/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67) para uso educativo. El [tipo de equipo de clase](https://support.office.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b) está diseñado para aulas con características específicas, entre las que se incluyen tareas, un bloc de notas de clase por OneNote, una [carpeta de materiales](https://support.office.com/article/Use-folders-to-create-read-only-files-for-students-or-other-team-members-0e7791d7-8c9c-4749-9bca-984289477988) para proteger el contenido de solo lectura de los alumnos y la capacidad de silenciar a estudiantes molestos. Hay un par de formas en las que se puede implementar un equipo de clase:

1. La **configuración**de [School Data Sync](https://sds.microsoft.com/) (SDS) puede configurarla, lo que permite crear equipos de clase para todas las clases en función de la información del sistema de información de la escuela. Este proceso propondrá a Teams para cada sección y mantendrá sincronizadas las listas del instructor y los estudiantes. [Los educadores tendrán la posibilidad de preparar su equipo](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78) antes de que los alumnos admitan. Como alternativa, si un educador no usa el equipo, los estudiantes no se admitirán en el equipo porque el educador nunca hace clic en "activar". SDS es compatible con más de 80 diferentes sistemas de información académica (sistemas SIS) para la importación de datos, y el [equipo de soporte de SDS](https://aka.ms/SDSSupport) está listo para ayudarle en la planificación y la configuración.
1. Los **formadores configuraron** su propio equipo de tipo de clase e invitan a alumnos. Los educadores pueden hacerlo a través de [la adición de alumnos al equipo](https://support.office.com/article/add-a-student-to-a-class-team-b88263bb-ace1-4702-8a48-f8a2cf4af954), de [compartir un código de participación](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)o de [compartir un vínculo al equipo](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f). Si es posible, es mejor que los formadores agreguen sus alumnos al equipo para asegurarse de que tengan acceso a los alumnos y que se les notifique que han sido añadidos a un equipo.

Después de la configuración de equipo, [los propietarios del equipo pueden personalizar la configuración de su equipo](https://support.office.com/article/find-your-class-team-s-settings-in-microsoft-teams-2592d4de-581d-4952-9028-02317880c158) , como agregar una [imagen de equipo](https://support.office.com/article/change-your-team-picture-02ea2af6-b49d-4de8-9551-1a5e472993c0), [crear canales](https://support.office.com/article/create-student-project-groups-channels-in-microsoft-teams-f85b3c07-fb87-4b94-883b-9be55f4b1e45?ui=en-US&rs=en-US&ad=US) para temas de clase o áreas de colaboración de grupo, [Agregar una aplicación](https://support.office.com/article/add-an-app-to-teams-b2217706-f7ed-4e64-8e96-c413afd02f77) como Quizlet/Flipgrid/Kahoot para exponer contenido educativo existente y [mencionar su primer mensaje](https://support.office.com/article/using-the-conversation-tab-in-microsoft-teams-53d1c530-3797-4a6f-9892-6760f8763df2) para notificar a todos e iniciar la conversación.

### <a name="create-staff-teams-for-staff-communication-and-collaboration"></a>Crear equipos de personal para la comunicación y colaboración de personal

Los [equipos del tipo de personal](https://support.office.com/article/create-a-staff-team-in-microsoft-teams-314ac9d5-36a9-408e-8ae4-7ef20e9f1ddf) están diseñados para que los administradores escolares y el personal puedan compartir información y trabajar conjuntamente en iniciativas para toda la escuela, incluidos anuncios, la configuración de reuniones, el uso compartido de contenido y la incorporación de aplicaciones externas, como [Planner para el seguimiento de tareas](https://support.office.com/article/create-a-plan-with-planner-d000976a-7490-4ddf-b9af-09ee764891e2). Los administradores escolares pueden agregar miembros del personal escolar al equipo mediante el Asistente para la creación de equipos, [Agregar miembros después de crear el equipo](https://support.office.com/article/add-members-to-a-team-in-teams-aff2249d-b456-4bc3-81e7-52327b6b38e9)o [compartir un código de participación o vincular al equipo](https://support.office.com/article/create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f). La [creación de canales](https://support.office.com/article/create-a-channel-in-teams-fda0b75e-5b90-4fb8-8857-7e102b014525) es una excelente manera de organizar la conversación y los archivos por secuencia de presentación o tema. [La guía de ir a para propietarios de equipos](https://support.office.com/article/go-to-guide-for-team-owners-75f9669b-bd8f-457d-b60b-ac2ac9c8ead4?ui=en-US&rs=en-US&ad=US) es un lugar excelente para obtener información sobre las funciones y capacidades del propietario del equipo.

## <a name="teams-meeting-scenarios"></a>Escenarios de reunión de Teams

### <a name="collaborative-meetings-for-virtual-classes"></a>Reuniones de colaboración para clases virtuales

Las [reuniones de Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/tutorial-meetings-in-teams) admiten hasta 250 asistentes, incluida la capacidad de tener audio, vídeo, [uso compartido de contenido](https://support.office.com/article/show-your-screen-during-a-meeting-90c84e5a-b6fe-4ed4-9687-5923d230d3a7), pizarras y notas compartidas. Las reuniones se pueden programar en el cliente de Microsoft Teams para su [reunión en un espacio privado o dentro de un canal de equipo](https://docs.microsoft.com/MicrosoftTeams/tutorial-meetings-in-teams), de modo que todos los miembros del equipo lo sepan. Las reuniones se pueden grabar y guardar para que los asistentes las revisen más adelante. Estas grabaciones también se pueden [transcribir para encontrar fácilmente el contenido](https://support.office.com/article/Microsoft-Stream-automatically-creates-closed-captions-for-videos-8d6ac353-9ff2-4e2b-bca1-329499455308) que se había tratado. Para las reuniones se puede usar una cámara web, un micrófono y un altavoz de un portátil o un teléfono móvil, y puede obtener una calidad de audio/video Premium de los [dispositivos optimizados de Microsoft Teams](https://products.office.com/microsoft-teams/across-devices/devices).

### <a name="districtuniversity-events-or-updates"></a>Actualizaciones o eventos de distrito o universitarios

Algunas instrucciones necesitan mayores audiencias y capacidades de producción adicionales. Estas reuniones suelen tener moderadores, productores y moderadores Q&A. Microsoft Teams es compatible con estas sesiones mediante [eventos de Microsoft Teams Live](teams-live-events/what-are-teams-live-events.md). Los eventos en directo se pueden usar para escenarios, como el distrito o las actualizaciones de todo el mundo, las direcciones de liderazgo, y para obtener instrucciones a clases o grupos de alumnos grandes, o para extenderse a su comunidad. Obtenga más información sobre cómo realizar sesiones en vivo en: [planear y programar un evento](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502)en directo, [producir un evento en directo](https://support.office.com/article/video-produce-a-live-event-34c89e79-ffd4-4a6a-baf6-77055e0709cb), [asistir a un evento en directo](https://support.office.com/article/video-attend-a-live-event-d837ad8d-ce34-44d0-9744-9beb50e943ac)y [moderar un Q&a](https://support.office.com/article/video-moderating-a-q-a-4984e582-8c66-4ea3-aaaf-d93cf62e1b76).

## <a name="recommended-tips--tricks"></a>Sugerencias recomendadas & trucos

Puede obtener más información sobre cómo se usa Microsoft Teams en el ámbito educativo en: [Microsoft Teams para el ámbito educativo](https://support.office.com/article/Teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114).

> [!NOTE]
> Algunas características clave de Microsoft Teams no son específicas de la formación. Puede encontrar sugerencias y trucos para las capacidades básicas de Teams en: [ayuda y aprendizaje de Microsoft Teams](https://support.office.com/teams).

## <a name="adoption-content"></a>Contenido de la adopción

Microsoft ha desarrollado una guía de [contenido](https://support.office.com/article/video-moderating-a-q-a-4984e582-8c66-4ea3-aaaf-d93cf62e1b76) y estrategias para implementar Microsoft Teams. La [Guía de adopción de Microsoft Teams](https://teamworktools.azurewebsites.net/tft/index.html) proporciona una buena descripción general del contenido disponible y el kit de éxito de los [clientes de Teams](https://download.microsoft.com/download/A/E/9/AE984CD4-CF4B-41E7-9ABD-6735E3F01897/MicrosoftTeamsCustomerSuccessKit.zip) proporciona muchas plantillas que pueden usarse para la conciencia de los equipos. El centro de educadores de Microsoft ofrece formación específica para la educación sobre cómo se usan [Microsoft Teams](https://education.microsoft.com/learningPath/18793af1) y [OneNote](https://education.microsoft.com/learningPath/b6e3b5f2) en el aula.

Entre los recursos de adopción adicionales, se incluyen:

- ["Puede encontrarse en: 90" vídeos de sugerencias rápidas](https://www.youtube.com/playlist?list=PLiluTszfwwMKx-yVe7ekBX6gsLIHf1Z8k)
- [Lista de reproducción de vídeo de Microsoft Teams para el ámbito educativo](https://www.youtube.com/playlist?list=PLiluTszfwwMKicAo6agloFALEB5WvYNYs)
- [BLOG: vea cómo el Colegio usa Teams para el aprendizaje por distancia](https://www.wellingtoncollege.cn/tianjin-international/teaching-and-learning-update/)

## <a name="support-readiness"></a>Compatibilidad con la preparación

Los profesionales de ti y el personal de soporte técnico pueden ponerse al día con la arquitectura de Teams y el uso subyacente de las capacidades de Microsoft 365 con los pósteres de arquitectura de ti y el aprendizaje técnico de administración de Microsoft Teams.

Otros recursos de soporte técnico incluyen:

- [Solución de problemas de instalación y actualización de Microsoft Teams](troubleshoot-installation.md)
- [Supervisar y administrar la calidad de las llamadas](monitor-call-quality-qos.md)
- [Comprobar el estado del servicio para Microsoft Teams](service-health.md)
- [Recursos de soporte técnico para Teams](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)
- [Supervisar y administrar la calidad de las llamadas](monitor-call-quality-qos.md)
- [Comprobar el estado del servicio para Microsoft Teams](service-health.md)
- [Recursos de soporte técnico para Teams](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)
- [Centro de ayuda de Microsoft Teams](https://support.office.com/en-us/teams)
