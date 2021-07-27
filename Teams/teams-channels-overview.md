---
title: Información general de los equipos y canales en Microsoft Teams
author: MikePlumleyMSFT
ms.author: mikeplum
ms.reviewer: ''
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Obtenga información sobre los diferentes equipos, canales y aplicaciones disponibles para una gran variedad de requisitos, como los servicios financieros, la planificación de eventos, las ventas y mucho más.
localization_priority: Priority
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.msteamsfiles
- ms.teamsadmincenter.dashboard.helparticle.teamsandchannels
- ms.teamsadmincenter.teamschannel.overview
- ms.teamsadmincenter.teamssettings.overview
- okr_smb
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 08b5c68c302f8fe830e5b5fcfcd37a76bde44a03
ms.sourcegitcommit: d34dbdc2f71f3d024cb7f1856fc0f8bbc701f66d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2021
ms.locfileid: "53506359"
---
# <a name="overview-of-teams-and-channels-in-microsoft-teams"></a>Información general de los equipos y canales en Microsoft Teams

Para empezar, veamos cómo Microsoft Teams permite que los equipos individuales puedan organizarse a sí mismos y puedan colaborar en distintos escenarios empresariales:

- Los **equipos** son recopilaciones de personas, contenido y herramientas alrededor de varios proyectos y tareas dentro de una organización.

    - Los equipos pueden crearse para ser privados, solo para los usuarios invitados.
    - Los equipos también pueden crearse para que sean públicos y abiertos, de modo que todos los integrantes de la organización puedan unirse (hasta 10 000 miembros).
    
    Los equipos están diseñados para reunir grupos de personas que trabajen juntos para lograr sus objetivos. Los equipos pueden ser dinámicos para el trabajo basado en proyectos (por ejemplo, iniciar un producto o crear un centro de operaciones digital) o continuos para reflejar la estructura interna de su organización (por ejemplo, departamentos y ubicaciones de oficinas). Los miembros del equipo serán los únicos que podrán ver las conversaciones, los archivos y las notas de los canales del equipo.

- Los **canales** son secciones dedicadas dentro de un equipo para mantener las conversaciones organizadas por temas, disciplinas o proyectos específicos, es decir, lo que le sea más conveniente al equipo. Los archivos que se comparten en un canal (en la pestaña archivos) se almacenan en SharePoint. Para obtener mas información, lea [Cómo SharePoint Online y OneDrive para la Empresa interactúan con Teams](SharePoint-OneDrive-interact.md).

    - Los canales son lugares donde ocurre la conversación y en los que se lleva a cabo el trabajo. Los canales pueden estar abiertos a todos los miembros del equipo o, si necesita un público más seleccionado, pueden ser privados. Los canales estándares son para las conversaciones en las que todos los miembros de un equipo pueden participar y los [canales privados](private-channels.md) limitan la comunicación a un subconjunto de personas en un equipo.
    - Los canales son mucho más útiles cuando se amplían con aplicaciones que incluyen fichas, conectores y bots que aumentan su valor para los miembros del equipo. Para obtener más información, vea [Aplicaciones, bots y conectores en Teams](deploy-apps-microsoft-teams-landing-page.md).
    
Para obtener ayuda con el uso de equipos y canales, consulte [Equipos y canales](https://support.office.com/article/teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499).

Vea este vídeo breve para obtener más información sobre los procedimientos recomendados para crear equipos y canales:

- [TechTip: Instrucciones para crear equipos y canales, incluidos los canales privados en Microsoft Teams](https://youtu.be/WkAVgNKn0hs) (21:08 min)

## <a name="membership-roles-and-settings"></a>Miembros, funciones y configuración

**Membresía de equipo**

Cuando Teams se activa para toda la organización, los propietarios de equipo tienen la capacidad de invitar a cualquier persona con la que trabajen en la organización a que se una al equipo. Con Teams, los propietarios de equipo pueden agregar con facilidad a personas de la organización por su nombre. En función de la configuración de su organización, las personas de fuera de la organización se pueden agregar a sus equipos como invitados. Vea [Acceso de invitado a Microsoft Teams](guest-access.md) para obtener más información. 

Los propietarios de equipos también pueden crear un equipo basado en un grupo de Microsoft 365 existente. Cualquier cambio que se realice en la suscripción de grupo se sincronizará con Teams automáticamente.

**Roles de equipo**

Hay dos roles principales en Teams: 

- **Propietario del equipo**: es la persona que crea el equipo. Los propietarios de equipo pueden convertir en copropietario a cualquier miembro del equipo cuando le inviten o en cualquier otro momento después de haberse unido al equipo. Tener varios propietarios de equipo, le permite compartir las responsabilidades en la administración de las configuraciones y membresías, incluidas las invitaciones.
- **Miembros del equipo**: son las personas a las que los propietarios invitaron para unirse a su equipo.

Además, si se configura la moderación, los propietarios y miembros del equipo pueden tener funciones de moderador para un canal. Los moderadores pueden iniciar nuevas publicaciones en el canal y controlar si los miembros del equipo pueden responder a los mensajes de canal existentes. Los propietarios del equipo pueden asignar moderadores en un canal. (De forma predeterminada, los propietarios del equipo tienen funciones de moderador). Los moderadores de un canal pueden agregar o quitar otros moderadores de ese canal. Parara más información, consulte[Configurar y administrar la moderación de canales en Microsoft Teams](manage-channel-moderation-in-teams.md).

> [!NOTE]
> Cuando agrega a un propietario de equipo, también lo agrega como miembro, excepto cuando el equipo se crea en el Centro de administración de Teams o cuando se agrega un equipo a un grupo de Microsoft 365 nuevo o existente.

**Configuración del equipo** 

Los propietarios del equipo pueden administrar la configuración de todo el equipo directamente en Teams. En la configuración se incluye la capacidad de agregar una imagen del equipo, establecer permisos en todos los miembros del equipo para crear canales estándares y [canales privados](private-channels.md), agregar fichas y conectores, @mencionar a todo el equipo o el canal, y usar archivos GIF, adhesivos y memes.

Si es administrador de Teams en Microsoft 365, tiene acceso a la configuración de todo el sistema en el Centro de administración de Teams. Esta configuración puede influir en las opciones y la configuración predeterminada que los propietarios ven en la configuración del equipo. Por ejemplo, puede habilitar un canal predeterminado, "General", para los anuncios, los debates y los recursos de todo el equipo, que aparecerá en todos los equipos.

De forma predeterminada, todos los usuarios tienen permisos para crear un equipo. Para cambiar esto, vea [Asignar roles y permisos en Teams](assign-roles-permissions.md).

Una actividad clave de planificación inicial para animar a los usuarios a utilizar Teams consiste en ayudarles a comprender el modo en que Teams puede mejorar la colaboración en sus actividades diarias. Hable con las personas y ayúdeles a seleccionar situaciones empresariales en las que estén colaborando en este momento de forma segmentada. Tráigalos a un canal con las fichas relevantes que les ayuden a realizar el trabajo que necesitan. Uno de los casos de uso más influyente de Teams es cualquier proceso organizativo. 

## <a name="example-teams"></a>Equipos de ejemplo

A continuación puede ver algunos ejemplos de cómo los distintos tipos de usuarios pueden abordar la configuración de sus equipos, canales y aplicaciones (pestañas/conectores/bots). Le pueden ser útiles para hablar de Teams con su comunidad de usuarios. A medida que planifique la implementación de Teams en su organización, recuerde que puede proporcionar instrucciones sobre cómo estructurar los equipos. Sin embargo, los usuarios son los que tienen el control de su propia organización. Estos son simplemente algunos ejemplos para que sus equipos reflexionen sobre lo que pueden llegar a hacer en Teams.

Teams es ideal para combatir el aislamiento comunicativo de los departamentos en su organización y fomentar equipos multidisciplinares. Anime a sus usuarios a que trabajen con la idea de equipos funcionales en mente y a que eviten las barreras organizacionales.

|Tipos de equipos  |Canales potenciales  |Aplicaciones (fichas) ![Un ícono que representa una carpeta con una pestaña](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image2.png)/Conectores ![Un icono que representa los bloques de conexión](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image3.png)/Bots ![Un icono que representa un robot pequeño](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image4.png))  |
|---------|---------|---------|
|Ventas     |Reunión anual de ventas<br></br> Revisión empresarial trimestral<br></br> Revisión del proceso de ventas mensual<br></br> Guía de tácticas de ventas |Power BI<br></br>Trello<br></br>CRM<br></br>Bot de resúmenes         |
|Relaciones públicas     |Comunicados de prensa<br></br>Noticias y actualizaciones<br></br>Verificación de datos         |fuente RSS<br></br>Twitter         |
|Planificación de eventos     |Marketing<br></br>Logística y planificación<br></br>Lugar<br></br>Budget         |Twitter<br></br>Facebook<br></br>Planner<br></br>PDF         |
|Marketing/Comercialización   |Estudio de mercado<br></br>Pilares de mensajes<br></br>Plan de comunicaciones<br></br>Lista de materiales de marketing        |YouTube<br></br>Microsoft Stream<br></br>Twitter<br></br>MailChimp         |
|Operaciones técnicas    |Administración de incidentes<br></br>Planificación de Sprint<br></br>Elementos de trabajo<br></br>Infraestructura y operaciones         |Servicios de equipos<br></br>Jira<br></br>AzureBot         |
|Equipo de producto      |Estrategia<br></br>Marketing<br></br>Ventas<br></br>Operaciones<br></br>Información<br></br>Servicios y soporte técnico         |Power BI<br></br>Servicios de equipos         |
|Finanzas    |Fiscal actual<br></br>Planificación del año fiscal<br></br>Previsión<br></br>Cuentas por cobrar<br></br>Cuentas por pagar         |Power BI<br></br>Google Analytics         |
|Logística     |Operaciones de almacenes<br></br>Mantenimiento de vehículos<br></br>Listas de conductores         |Servicio meteorológico<br></br>Cortes en carreteras y viajes<br></br>Planner<br></br>UPS Bot         |
|RR. HH.     |Administración de talento<br></br>Contratación<br></br>Planificación de revisión del rendimiento<br></br>Moral         |Herramientas de recursos humanos<br></br>Sitios de publicación de trabajos externos<br></br>Growbot         |
|Organizativo <br></br>Equipo virtual |Estrategia<br></br>Desarrollo de la mano de obra<br></br>Competencia e investigación         |Power BI<br></br>Microsoft Stream         |

Es posible crear equipos que se alineen con la estructura de la organización. Esto es especialmente usado para líderes que quieren levantar la moral, realizar revisiones de equipo específicas, aclarar procesos de incorporación de empleados, discutir planes de recursos y aumentar la visibilidad en una cantidad de recursos diversos.  

![Diagrama de jerarquía de equipos y canales organizados en Microsoft Teams.](media/overview-of-teams-and-channels-image1.png)

## <a name="org-wide-teams"></a>Equipos de toda la organización

Si su organización no tiene más de 5 000 usuarios, puede crear un equipo de toda la organización. Los equipos de toda la organización proporcionan una forma automática para que todos los usuarios de la organización puedan formar parte de un único equipo y facilitar la colaboración. Para obtener más información, como los procedimientos recomendados para crear y administrar un equipo de toda la organización, consulte [Crear un equipo que abarque toda la organización en Microsoft Teams](create-an-org-wide-team.md).

## <a name="next-steps"></a>Pasos siguientes

Consulte [Chat, equipos, canales y aplicaciones en Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md) para explorar una lista de decisiones importantes para la implementación de Teams.
