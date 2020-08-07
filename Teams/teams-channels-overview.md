---
title: Información general de los equipos y canales en Microsoft Teams
author: SerdarSoysal
ms.author: serdars
ms.reviewer: ''
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Obtenga información sobre los diferentes equipos, canales y aplicaciones disponibles para una gran variedad de requisitos, como los servicios financieros, la planificación de eventos, las ventas y mucho más.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: okr_smb
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 36c29eaba8a16bde44e9f3537eee9950c53d2715
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581831"
---
# <a name="overview-of-teams-and-channels-in-microsoft-teams"></a>Información general de los equipos y canales en Microsoft Teams

> [!NOTE]
> Revise la información siguiente para familiarizarse con los chats, equipos, canales y aplicaciones en Teams. Luego, vaya a [Chat, equipos, canales y aplicaciones en Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md) para explorar una lista de decisiones importantes para la implementación de Teams.

Para empezar, veamos cómo Microsoft Teams permite que los equipos individuales puedan organizarse a sí mismos y puedan colaborar en distintos escenarios empresariales:

- Los **equipos** son recopilaciones de personas, contenido y herramientas alrededor de varios proyectos y tareas dentro de una organización.

    - Los equipos pueden crearse para ser privados, solo para los usuarios invitados.
    - Los equipos también se pueden crear de forma pública y abrir y cualquier persona dentro de la organización puede unirse (hasta 10.000 miembros).
    
    Los equipos están diseñados para reunir grupos de personas que trabajen juntos para lograr sus objetivos. Los equipos pueden ser dinámicos para el trabajo basado en proyectos (por ejemplo, iniciar un producto o crear un centro de operaciones digital) o continuos para reflejar la estructura interna de su organización (por ejemplo, departamentos y ubicaciones de oficinas). Los miembros del equipo serán los únicos que podrán ver las conversaciones, los archivos y las notas de los canales del equipo.

- Los **canales** son secciones dedicadas dentro de un equipo para mantener las conversaciones organizadas por temas, disciplinas o proyectos específicos, es decir, lo que le sea más conveniente al equipo. Los archivos que se comparten en un canal (en la pestaña archivos) se almacenan en SharePoint. Para obtener mas información, lea [Cómo SharePoint Online y OneDrive para la Empresa interactúan con Teams](SharePoint-OneDrive-interact.md).

    - Los canales son lugares donde ocurre la conversación y en los que se lleva a cabo el trabajo. Los canales pueden estar abiertos a todos los miembros del equipo o, si necesita un público más seleccionado, pueden ser privados. Los canales estándares son para las conversaciones en las que todos los miembros de un equipo pueden participar y los [canales privados](private-channels.md) limitan la comunicación a un subconjunto de personas en un equipo.
    - Los canales son mucho más útiles cuando se amplían con aplicaciones que incluyen fichas, conectores y bots que aumentan su valor para los miembros del equipo. Para obtener más información, vea [Aplicaciones, bots y conectores en Teams](deploy-apps-microsoft-teams-landing-page.md).
    
Para obtener ayuda con el uso de equipos y canales, consulte [Equipos y canales](https://support.office.com/article/teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499).

Vea este vídeo breve para obtener más información sobre los procedimientos recomendados para crear equipos y canales.

   > [!VIDEO https://www.youtube.com/embed/WkAVgNKn0hs]

<a name="membership-roles-and-settings"></a>Miembros, funciones y configuración
------------------------------

**Membresía de equipo**

Cuando Microsoft Teams se activa para toda la organización, los propietarios de equipo designados tienen la capacidad de invitar a cualquier empleado con el que trabajen para que se una al equipo. Con Microsoft Teams, los propietarios de equipo pueden agregar con facilidad personas de la organización por su nombre. En función de cuál sea la configuración de su organización, podrá agregar a sus equipos los invitados que sean miembros del equipo, pero que no pertenezcan a la organización. Vea [Acceso de invitado a Microsoft Teams](guest-access.md) para obtener más información. 

Los propietarios de equipos también pueden crear un equipo basado en un grupo de Microsoft 365 existente. Cualquier cambio que se realice en el grupo se sincronizarán con Microsoft Teams automáticamente. Crear un equipo basado en un grupo de Microsoft 365 existente no solo simplifica el proceso de invitar y administrar miembros, sino que también sincroniza los archivos de grupo dentro de Microsoft Teams.

**Roles de equipo**

Hay dos roles principales en Microsoft Teams: 

- **Propietario del equipo**: es la persona que crea el equipo. Los propietarios de equipo pueden convertir en copropietario a cualquier miembro del equipo cuando le inviten o en cualquier otro momento después de haberse unido al equipo. Tener varios propietarios de equipo, le permite compartir las responsabilidades en la administración de las configuraciones y membresías, incluidas las invitaciones.
- **Miembros del equipo**: son las personas a las que los propietarios invitaron para unirse a su equipo.

Además, si se configura la moderación, los propietarios y miembros del equipo pueden tener funciones de moderador para un canal. Los moderadores pueden iniciar nuevas publicaciones en el canal y controlar si los miembros del equipo pueden responder a los mensajes de canal existentes. Los propietarios del equipo pueden asignar moderadores en un canal. (De forma predeterminada, los propietarios del equipo tienen funciones de moderador). Los moderadores de un canal pueden agregar o quitar otros moderadores de ese canal. Parara más información, consulte[Configurar y administrar la moderación de canales en Microsoft Teams](manage-channel-moderation-in-teams.md).

**Configuración del equipo** 

Los propietarios del equipo pueden administrar la configuración de todo el equipo directamente en Microsoft Teams. En la configuración se incluye la capacidad de agregar una imagen del equipo, establecer permisos en todos los miembros del equipo para crear canales estándares y [canales privados](private-channels.md), agregar fichas y conectores, @mencionar a todo el equipo o el canal, y usar archivos GIF, adhesivos y memes.

Tómese 3 minutos para ver esta guía en vídeo para propietarios de equipos:

   > [!VIDEO https://www.youtube.com/embed/kalV4dG-oFo]

Si es un administrador de Microsoft Teams en Microsoft 365 u Office 365, tiene acceso a la configuración de todo el sistema en el centro de administración de Microsoft Teams. Esta configuración puede influir en las opciones y la configuración predeterminada que los propietarios ven en la configuración del equipo. Por ejemplo, puede habilitar un canal predeterminado, "General", para los anuncios, los debates y los recursos de todo el equipo, que aparecerá en todos los equipos.

De manera predeterminada, todos los usuarios tienen permisos para crear un equipo en Microsoft Teams (para modificarlo, consulte [Asignar roles y permisos en Microsoft Teams](assign-roles-permissions.md)). Los usuarios de un grupo de Microsoft 365 existente también pueden mejorar sus permisos con la funcionalidad de Teams.

Una actividad clave de planificación inicial para animar a los usuarios a utilizar Microsoft Teams consiste en ayudarles a pensar y comprender el modo en que Teams puede mejorar la colaboración en sus actividades diarias. Hable con las personas y ayúdeles a seleccionar situaciones empresariales en las que estén colaborando en este momento de forma segmentada. Tráigalos a un canal con las fichas relevantes que les ayuden a realizar el trabajo que necesitan. Uno de los casos de uso más influyente de Teams es cualquier proceso organizativo. 

<a name="example-teams"></a>Equipos de ejemplo
--------------

A continuación se muestran algunos ejemplos funcionales de cómo diferentes tipos de usuarios pueden enfocar la configuración de sus equipos, canales y aplicaciones (fichas/conectores/bots). Esto puede ser útil para ayudar a iniciar una conversación acerca de Microsoft Teams con la comunidad de usuarios. Al planear la implementación de Microsoft Teams en la organización, recuerde que puede proporcionar instrucciones sobre cómo estructurar sus equipos; sin embargo, los usuarios controlan cómo se pueden organizar automáticamente. Estos son solo ejemplos para empezar a ayudar a los equipos a pensar a través de las posibilidades.

Microsoft Teams es perfecta para eliminar la idea de los silos de la organización y promocionar equipos para varias funciones. Por lo tanto, deberá animar a los usuarios para que piensen en equipos funcionales en vez de barreras organizacionales.

|Tipos de equipos  |Canales potenciales  |Aplicaciones (fichas) ![Un ícono que representa una carpeta con una pestaña](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image2.png)/Conectores ![Un icono que representa los bloques de conexión](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image3.png)/Bots ![Un icono que representa un robot pequeño](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image4.png))  |
|---------|---------|---------|
|Ventas     |Reunión anual de ventas<br></br> Revisión empresarial trimestral<br></br> Revisión del proceso de ventas mensual<br></br> Guía de tácticas de ventas |Power BI<br></br>Trello<br></br>CRM<br></br>Bot de resúmenes         |
|Relaciones públicas     |Comunicados de prensa<br></br>Noticias y actualizaciones<br></br>Verificación de datos         |fuente RSS<br></br>Twitter         |
|Planificación de eventos     |Marketing<br></br>Logística y planificación<br></br>Lugar<br></br>Budget         |Twitter<br></br>Facebook<br></br>Planner<br></br>PDF         |
|Marketing/Comercialización   |Estudio de mercado<br></br>Pilares de mensajes<br></br>Plan de comunicaciones<br></br>Lista de materiales de marketing        |YouTube<br></br>Microsoft Stream<br></br>Twitter<br></br>MailChimp         |
|Operaciones técnicas    |Administración de incidentes<br></br>Planificación de Sprint<br></br>Elementos de trabajo<br></br>Infraestructura y operaciones         |Servicios de equipo<br></br>Jira<br></br>AzureBot         |
|Equipo de producto      |Estrategia<br></br>Marketing<br></br>Ventas<br></br>Operations<br></br>Información<br></br>Servicios y soporte técnico         |Power BI<br></br>Servicios de equipos         |
|Finanzas    |Fiscal actual<br></br>Planificación del año fiscal<br></br>Previsión<br></br>Cuentas por cobrar<br></br>Cuentas por pagar         |Power BI<br></br>Google Analytics         |
|Logística     |Operaciones de almacenes<br></br>Mantenimiento de vehículos<br></br>Listas de conductores         |Servicio meteorológico<br></br>Cortes en carreteras y viajes<br></br>Planner<br></br>Tubot<br></br>UPS Bot         |
|RR. HH.     |Administración de talento<br></br>Contratación<br></br>Planificación de revisión del rendimiento<br></br>Moral         |Herramientas de recursos humanos<br></br>Sitios de publicación de trabajos externos<br></br>Growbot         |
|Organizativo <br></br>Equipo virtual |Estrategia<br></br>Desarrollo de la mano de obra<br></br>Competencia e investigación         |Power BI<br></br>Microsoft Stream         |

Es posible crear equipos que se alineen con la estructura de la organización. Esto es especialmente usado para líderes que quieren levantar la moral, realizar revisiones de equipo específicas, aclarar procesos de incorporación de empleados, discutir planes de recursos y aumentar la visibilidad en una cantidad de recursos diversos.  

![Diagrama de jerarquía de equipos y canales organizados en Microsoft Teams.](media/overview-of-teams-and-channels-image1.png)

## <a name="org-wide-teams"></a>Equipos de toda la organización

Si su organización no tiene más de 5 000 usuarios, puede crear un equipo de toda la organización. Los equipos de toda la organización proporcionan una forma automática para que todos los usuarios de la organización puedan formar parte de un único equipo y facilitar la colaboración. Para obtener más información, como los procedimientos recomendados para crear y administrar un equipo de toda la organización, consulte [Crear un equipo que abarque toda la organización en Microsoft Teams](create-an-org-wide-team.md).
