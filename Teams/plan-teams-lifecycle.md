---
title: Plan para la administración del ciclo de vida en Teams - Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 09/26/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
description: Descubra cómo se debe planificar la implementación de las funcionalidades de administración del ciclo de vida en Teams.
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b5686ec27495c8bbefbd07701031ddc179244986
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2019
ms.locfileid: "30641362"
---
# <a name="plan-for-lifecycle-management-in-teams"></a>Plan para la administración del ciclo de vida en Teams

Teams ofrece un amplio conjunto de herramientas que se utiliza para implementar los procesos de administración del ciclo de vida de colaboración para su organización. En este artículo, los profesionales de TI recorren las preguntas adecuadas que les llevarán a determinar sus requisitos de administración del ciclo de vida y las herramientas que deben usar para cumplirlos. 

Planificar la administración del ciclo de vida es muy importante, puesto que implica crear un plan para poder realizar tareas de forma efectiva. La mayoría de proyectos constan de un principio, una parte intermedia y un final, Teams también, pero se puede construir y usar de tantas formas que no siempre está claro en qué etapa de su ciclo de vida está. Tener un plan para administrar el ciclo de vida le ayudará a llevar un seguimiento de los proyectos de su organización conforme van avanzando por estas etapas.

> [!Tip]
> Vea la siguiente sesión para aprender más cosas sobre el ciclo de vida en Microsoft Teams: [gobierno, administración y ciclo de vida en Microsoft Teams](https://aka.ms/teams-governance)


## <a name="lifecycle-concepts"></a>Conceptos del ciclo de vida

Los siguientes conceptos y definiciones influyen en las decisiones que tome para la administración del ciclo de vida.

**Teams**

A _team_ is a collection of people, content, and tools that facilitate collaboration. A team defines who its members are, and the permissions and policies that apply to those members. Teams are built on Office 365 Groups, and changes to Office 365 group membership sync to the team. Like other Office 365 Groups, Teams come auto-provisioned with an Exchange mailbox, a SharePoint site, a OneNote notebook, and other assets within Office 365. [Learn more about Office 365 Groups](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

**Canales**

Channels are the collaboration spaces within a team where the actual work is done. Each channel represents a different topic or workstream within the overall team. For each channel, a folder is automatically created on the SharePoint site to store all files shared to that channel, making it easy for users to find and work on the documents they care about. Channels can also be extended with apps that are relevant to the particular workstream—for example, you can add a Power BI dashboard to a channel to track the success of one aspect of your project.

**Tipos de acceso a los equipos**

Determinan quién puede unirse al equipo:

-   _Private_ teams are restricted to team members approved by the team owner(s). This is a typical setting for project teams and virtual teams in a large organization.
-   _Public_ teams are open for anyone in the organization to join directly. This is useful for collaboration on topics of general interest to people in different departments working on different projects. This is a good default setting for smaller organizations.

**Funciones de administrador y tipos de usuario de los equipos** 

Los tipos de usuario de los equipos determinan la cantidad de control que tiene un miembro del equipo:

-   _Team creator_ has permissions to create a group or team in the directory. The admin can constrain this user type to a subset of admins or users. For more information, see [Manage who can create Office 365 Groups](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618). 
-   _Team owner_ manages membership and settings for the team. There can be as many as 10 team owners per team.
-   El _miembro del equipo_ es un miembro de su organización que participa en un equipo.
-   _Guest_ is a user who’s external to your organization. Anyone with an email address can be invited as a guest if your organization has enabled [guest access](guest-access.md).

> [!Note]
> Puede obtener más información sobre las funcionalidades del propietario de equipo y el miembro del equipo en el artículo [Asignar roles y permisos en Microsoft Teams](assign-roles-permissions.md).

Teams admin roles determine what capabilities each admin role holder has. These are described in the following table.

<table>
 <thead>
  <tr>
    <th width="0.5%"></th>
    <th width="15.5%">Rol&nbsp;&nbsp;</th>
    <th width="25%">Descripción</th>
    <th width="60%">Puede hacer las siguientes tareas, con las herramientas indicadas</th>
  </tr>
</thead>
<tbody>
   <tr>
    <td valign="top" colspan="2">Administrador de servicios de Teams</td>
    <td valign="top">Administre el servicio de Teams, y cree y administre grupos de Office 365</td>
    <td valign="top">Administrar reuniones, incluidas las directivas de reunión, configuraciones y puentes de conferencia<sup>1</sup><br><br>Administrar la voz, incluidas las directivas de llamada, la asignación y el inventario de los números de teléfono, las colas de llamada y los operadores automáticos<sup>1</sup><br><br>Administrar los mensajes, incluidas las directivas de mensajería<sup>1</sup><br><br>Administrar la configuración de toda la organización, incluida la federación, la actualización de Teams y la configuración de cliente de Teams<sup>1</sup><br><br>Administrar los equipos de la organización y su configuración asociada, incluida la pertenencia<sup>2</sup><br><br>Ver la página del perfil de usuario y solucionar los problemas relacionados con la calidad de llamada de los usuarios mediante un conjunto de herramientas avanzado de solución de problemas<sup>3</sup></td>
</tr>
<tr>
<td valign="top" colspan="2">Administrador de comunicaciones de Teams</td>
<td valign="top">Administre las características de reuniones y llamadas dentro del servicio de Microsoft Teams</td>
<td valign="top">Administrar reuniones, incluidas las directivas de reunión, configuraciones y puentes de conferencia<sup>1</sup><br><br>Administrar la voz, incluidas las directivas de llamada, la asignación y el inventario de los números de teléfono, las colas de llamada y los operadores automáticos<sup>1</sup><br><br>Ver la página del perfil de usuario y solucionar los problemas relacionados con la calidad de llamada de los usuarios mediante un conjunto de herramientas avanzado de solución de problemas<sup>1</sup></td>
</tr>
<tr>
<td valign="top" colspan="2">Especialista en comunicaciones de Teams</td>
<td valign="top">Solucione los problemas relacionados con las comunicaciones dentro de Teams mediante herramientas básicas</td>
<td valign="top">Access to the user profile page for troubleshooting calls in Call Analytics. Can only view user information for the specific user being searched for.<sup>3</sup></td>
</tr>
<tr>
<td valign="top" colspan="2">Ingeniero de soporte en comunicaciones de Teams</td>
<td valign="top">Solucione los problemas relacionados con las comunicaciones dentro de Teams mediante herramientas avanzadas</td>
<td valign="top">Access to the user profile page for troubleshooting calls in Call Analytics. Can view the full call record information.<sup>3</sup></td>
</tr>
<tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3"><a href="https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell
">Módulo PowerShell — Skype Empresarial</a> o <a href="https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center">Centro de administración de Microsoft Teams</a></td></tr>
<tr><td align="right"><sup>2</sup></td><td colspan="3"><a href="https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3">Módulo PowerShell — Microsoft Teams</a> o <a href="https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center">Centro de administración de Microsoft Teams</a></td></tr>
<tr><td align="right"><sup>3</sup></td><td colspan="3">Solo el <a href="https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center">Centro de administración de Microsoft Teams</a></td>
</tr>
</tfoot>
</table>


## <a name="it-decisions-to-make-before-getting-started"></a>Decisiones de TI que se deben tomar antes de empezar

Before you roll Teams out to your organization, implement any governance policies that your organization has decided it requires. These can include items like naming conventions, expiration policies, retention policies, and more. Generally speaking, it’s much easier to implement these requirements prior to scaling your deployment across your organization.

Si desea más información, consulte [Plan para el control en Teams](plan-teams-governance.md).

## <a name="teams-lifecycle-stages"></a>Fases del ciclo de vida de Teams

Generally speaking, a team has a purpose that’s aligned with a project or accomplishing a goal. Even if a team was formed based on a shared interest, the team membership will probably change over time and the discussion might grow stale—only to surface again in a slightly different way in a different team.

Cada equipo tiene un principio: cuando el equipo se crea y los canales se configuran; una parte central: cuando el equipo se utiliza y se produce la colaboración para ajustarse al ritmo del flujo de trabajo; y, en ocasiones, un final: cuando el equipo ha completado su propósito y ha llegado al final de su vida útil. 

Para obtener más información, consulte [Administrar equipos en el Centro de administración de Microsoft Teams](manage-teams-in-modern-portal.md).

### <a name="stage-1-beginning"></a>Fase 1: Inicio

#### <a name="create-the-team"></a>Crear el equipo

The first step is to define the goal of the team (which can range from business processes to org structure to projects, or simply creating an open, unstructured collaboration hub). Defining the team goal goes hand in hand with identifying the right people. As far as practicable, it’s a good idea to foster open collaboration by aiming for broad membership. 

Los propietarios de equipo invitan a los miembros del equipo, definen la imagen del equipo y su descripción, y establecen los permisos para cada uno de los miembros. 

> [!Tip]
>  Lo ideal es identificar al menos dos miembros del equipo para poder responder ante una ausencia o reasignación.

#### <a name="team-origins"></a>Orígenes del equipo

Los equipos pueden formarse a partir de una gran variedad de métodos; entre ellos:

-   Agregue a los miembros mediante nombres de usuario o alias de correo electrónico individuales, o bien amplíe una lista de distribución.
-   Create the team from an existing team, and use its channel configuration and any app configuration as a template. You can optionally also use its membership list.
-   Agregue un equipo a un grupo de Office 365 actual, que también le dé acceso al equipo al buzón de correo y el sitio de SharePoint.
-   Las API pueden crear equipos mediante programación que se basen en los atributos de la libreta de direcciones global (como la región o el departamento) o los procesos empresariales (las interacciones con clientes o las listas de participantes de clase, por ejemplo).

Utilice estos vínculos para obtener más información sobre cómo se organizan los equipos:

-   [Procedimientos recomendados para organizar los equipos en Teams](best-practices-organizing.md)
-   [Implementar chat, equipos, canales y aplicaciones](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
-   [Implementar reuniones y conferencias](deploy-meetings-microsoft-teams-landing-page.md)
-   [Implementar voz en la nube](cloud-voice-landing-page.md)


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>¿Cuál es el propósito del equipo?</li><li>¿Quién está en el equipo?</li><li>¿El equipo será privado o público?</li><li>¿Los miembros nuevos pueden agregarse a sí mismos o lo hacen los propietarios de equipo?</li><li>¿Quién tendrá permisos para crear canales o agregar fichas, bots y conectores?</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Crear el equipo.</li><li>Planificar los canales.</li></ul>|


#### <a name="set-up-channels"></a>Configurar los canales

Cualquier miembro o propietario de equipo que tenga los permisos adecuados podrá crear canales en un equipo. Es muy importante tener en cuenta el objetivo de cada canal: las opciones incluyen la colaboración en torno a proyectos, discusiones de temas o áreas de interés común. De forma predeterminada, cada equipo incluye un canal General. En la mayoría de equipos se necesitarán algunos más y los miembros crearán canales adicionales. Es probable que el conjunto de canales crezca de manera orgánica conforme vayan surgiendo nuevos temas o proyectos, y los debates pueden aumentar en mayor medida que el canal en el que empezaron.

Para despertar el interés, el propietario del canal puede publicar un mensaje de bienvenida, cargar documentos relevantes en la ficha **Archivos** o agregar fichas o conectores al canal. El propietario también establece la descripción del canal y puede marcar automáticamente como favoritos los canales importantes para que aparezcan de forma predeterminada para todos los miembros del equipo.

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>¿Qué canales iniciales se agregarán al equipo?</li><li>¿Qué instrucciones, en caso de haber alguna, se ofrecerán para agregar nuevos canales? (¿Se configurarán según el proyecto, el tema, etc.?)</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Crear canales iniciales.</li><li>Publicar un mensaje de bienvenida.</li><li>Empezar a colaborar.</li></ul>|

### <a name="stage-2-middle"></a>Fase 2: Parte central

Una vez comienza el trabajo en equipo, la pertenencia al equipo comenzará con toda seguridad a evolucionar también, junto con la jerarquía del canal. A menos que el equipo necesite estar controlado y bloqueado de forma estricta, es una buena idea animar a que se explore, incluso si esto conduce a un callejón sin salida. Conforme los usuarios se vayan sintiendo más cómodos, podrán experimentar con \@menciones de equipo, cómo marcar canales como favoritos y usar el canal General para publicar de forma cómoda. Cada equipo es diferente, por lo que debemos dejar que sea el uso el que guíe la evolución del diseño. Supervise el uso y el estado del equipo a través de las funcionalidades de creación de informes de Teams.

La confianza, la tolerancia y un espíritu de colaboración aumentan de forma orgánica a medida que las comunicaciones de grupo principales se inician y se mantienen a lo largo del tiempo en Teams. Los miembros de los equipos ven la utilidad de las conversaciones de grupo en los chats uno a uno. Cada equipo tiende a desarrollar su propia personalidad, con la ayuda de características como los Giphy y los adhesivos. Al mismo tiempo, es importante que se disuadan comportamientos superficiales o el acceso no autorizado cada vez que sucedan.

Como los equipos son organismos vivos, precisan que se les revise y se les atienda de vez en cuando. Estas son las prácticas recomendadas:

-   Use expertos para mantener el nivel de uso si este empieza a caer, así como para descubrir y propagar nuevos comportamientos. 
-   Administre a los invitados con buen juicio y asegúrese de que su acceso termina cuando termine la necesidad de la empresa.
-   Deje que los canales evolucionen a la par que las necesidades del negocio, añada nuevos canales según sea necesario y permita que los antiguos vayan desapareciendo (o considere la opción de archivarlos o eliminarlos si contienen datos confidenciales o efímeros, según sean los requisitos de retención).
-   Forje nuevos equipos cuando surjan grupos más grandes o áreas basadas en un tema de interés.
-   Pruebe con diferentes colaboraciones de canal, como las reuniones de canal o las conversaciones en ficha sobre documentos.

Si un equipo empieza a estancarse, considere las siguientes opciones:

-   Impulse las comunicaciones en los equipos en lugar de hacerlo por correo electrónico.
-   Use las aplicaciones móviles para aumentar el nivel de interacción.
-   Recorte el número de canales.

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>¿Quién supervisará el uso para identificar los problemas?</li><li>¿Qué métricas se usarán para determinar si un equipo está en buen estado?</li><li>Identifique qué equipos han llegado al final de su vida útil.</li><li>Identifique los equipos que no están bien y que siguen teniendo un propósito, pero necesitan revitalizarse.</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Siguiente paso|<ul><li>Implemente un proceso que supervise el estado de cada equipo.</li></ul>|

### <a name="stage-3-end"></a>Fase 3: Final

Cuando el trabajo de un equipo llega a su fin, es importante reconocer formalmente que ha terminado. De este modo, el equipo se queda con una sensación de cierre y se evita que alguien más acceda a información obsoleta. Podrá usar el equipo para llevar a cabo los rituales de cierre, como análisis finales y resúmenes ejecutivos.

Puede borrar los equipos que sabe que no necesita (por ejemplo, un equipo creado estrictamente para realizar pruebas o un equipo que contiene datos confidenciales). De hecho, los equipos se eliminan con una “eliminación temporal” que el departamento de TI puede revertir hasta en un máximo de 21 días (30 días para los grupos de Office 365). El hecho de eliminar los equipos no afecta a los chats ni al contenido que se haya conservado según las directivas de cumplimiento normativo.

También se pueden usar las directivas de expiración y retención, además de las funcionalidades de archivado, para reducir la exposición de los equipos que ya no están activos o cuyos miembros han dejado la organización.

Para obtener información sobre cómo se configuran las directivas de expiración y retención, consulte [Información general de seguridad y cumplimiento en Microsoft Teams](security-compliance-overview.md).

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Defina cómo es el final de la vida de un equipo.</li><li>Decida si desea mantener disponible el contenido de un equipo y durante cuánto tiempo.</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Documentar las prácticas recomendadas y las lecciones aprendidas.</li><li>Archivar los datos, en caso necesario.</li></ul>|

