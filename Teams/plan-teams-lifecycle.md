---
title: Planear la administración del ciclo de vida
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: En este artículo descubrirá cómo se debe planificar la implementación de las funcionalidades de administración del ciclo de vida en Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 44be1d139fe37a34cad620cb449ac8bfe10eb99b
ms.sourcegitcommit: 43823358e7e1c1cece72a69a2ceb4eff86d3f927
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "48416916"
---
# <a name="plan-for-lifecycle-management-in-teams"></a>Plan para la administración del ciclo de vida en Teams

Teams ofrece un amplio conjunto de herramientas que se utiliza para implementar los procesos de administración del ciclo de vida de colaboración para su organización. En este artículo, los profesionales de TI recorren las preguntas adecuadas que les llevarán a determinar sus requisitos de administración del ciclo de vida y las herramientas que deben usar para cumplirlos. 

Planear la administración del ciclo de vida es muy importante, puesto que implica crear un plan para poder realizar tareas de forma efectiva. La mayoría de los proyectos constan de un principio, una parte intermedia y un final. Teams también, pero se puede construir y usar de tantas formas que no siempre está claro en qué etapa de su ciclo de vida está. Tener un plan para administrar el ciclo de vida le ayudará a llevar un seguimiento de los proyectos de su organización conforme van avanzando por estas etapas.

> [!Tip]
> Vea la siguiente sesión para aprender más cosas sobre el ciclo de vida en Microsoft Teams: [gobierno, administración y ciclo de vida en Microsoft Teams](https://aka.ms/teams-governance)


## <a name="lifecycle-concepts"></a>Conceptos del ciclo de vida

Los siguientes conceptos y definiciones influyen en las decisiones que tome para la administración del ciclo de vida.

**Teams**

Un _equipo_ es una colección de personas, contenido y herramientas que facilitan la colaboración. Un equipo define quiénes son sus miembros, y los permisos y directivas que se les aplica. Los equipos se construyen sobre Grupos de Microsoft 365 y los cambios que se realicen en la pertenencia a grupos de Microsoft 365 se sincronizarán con el equipo. Al igual que sucede con otros grupos de Microsoft 365, los equipos vienen aprovisionados automáticamente con un buzón de correo de Exchange, un sitio de SharePoint, un bloc de notas de OneNote y otros activos de Microsoft 365 u Office 365. [Más información sobre Grupos de Microsoft 365](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)

**Canales**

Los canales son los espacios de colaboración dentro de un equipo donde se realiza el trabajo real. Cada canal representa un tema distinto o una serie de tareas dentro del equipo general. Para cada canal, se crea una carpeta automáticamente en el sitio de SharePoint donde se almacenarán todos los archivos que se hayan compartido en ese canal, de manera que los usuarios pueden encontrarlos y trabajar en los documentos que necesiten. Los canales también se pueden ampliar con aplicaciones que sean relevantes para esa serie de tareas en particular; por ejemplo, puede agregar un panel de Power BI a un canal para comprobar si un aspecto concreto del proyecto se desarrolla correctamente.

**Tipos de acceso a los equipos**

Determinan quién puede unirse al equipo:

-   Los equipos _privados_ están restringidos a los miembros del equipo que han aprobado los propietarios del equipo. Es la configuración típica en equipos de proyecto y equipos virtuales de una organización de gran tamaño.
-   Los equipos _públicos_ están abiertos para que todos los miembros de la organización puedan unirse directamente. Es muy útil para que personas de distintos departamentos que trabajan en diferentes proyectos puedan colaborar en temas de interés general. Suele ser una configuración predeterminada para organizaciones más pequeñas.

**Funciones de administrador y tipos de usuario de los equipos** 

Los tipos de usuario de los equipos determinan la cantidad de control que tiene un miembro del equipo:

-   El *creador del equipo* tiene permisos para crear un grupo o un equipo en el directorio. El administrador puede limitar este tipo de usuario a un subconjunto de administradores o usuarios. Si desea más información, consulte [Administrar quién puede crear Grupos de Microsoft 365](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618). Los creadores del equipo se convierten automáticamente en propietarios del equipo.
-   El *propietario del equipo* administra la pertenencia y la configuración del equipo. Puede haber hasta 100 propietarios de equipo en un equipo.
-   El *miembro del equipo* es un miembro de su organización que participa en un equipo.
-   El *invitado* es un usuario que no pertenece a la organización. A cualquier persona que tenga una dirección de correo electrónico se le puede invitar como invitado, siempre que la organización tenga habilitado el [acceso de invitado](guest-access.md).

> [!Note]
> Puede obtener más información sobre las funcionalidades del propietario de equipo y el miembro del equipo en el artículo [Asignar roles y permisos en Microsoft Teams](assign-roles-permissions.md).

Los roles de administrador de Teams determinan qué funcionalidades tiene cada titular de rol de administrador. Se describen en la siguiente tabla.

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
    <td valign="top">Administre el servicio de Teams, y cree y administre Grupos de Microsoft 365</td>
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
<td valign="top">Acceder a la página del perfil de usuario para solucionar problemas relacionados con las llamadas en Análisis de llamada. Solo se puede ver la información de usuario del usuario concreto que se está buscando.<sup>3</sup></td>
</tr>
<tr>
<td valign="top" colspan="2">Ingeniero de soporte en comunicaciones de Teams</td>
<td valign="top">Solucione los problemas relacionados con las comunicaciones dentro de Teams mediante herramientas avanzadas</td>
<td valign="top">Acceder a la página del perfil de usuario para solucionar problemas relacionados con las llamadas en Análisis de llamada. Se puede ver toda la información del registro de llamada.<sup>3</sup></td>
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

Antes de desplegar Teams en su organización, implemente las directivas de control que la organización haya decidido que son necesarias. Pueden incluir elementos como las convenciones de nomenclatura, las directivas de expiración, las directivas de retención, etc. Por lo general, es mucho más sencillo implementar estos requisitos antes de escalar la implementación por toda la organización.

Si desea más información, consulte [Plan para el control en Teams](plan-teams-governance.md).

## <a name="teams-lifecycle-stages"></a>Fases del ciclo de vida de Teams

Hablando en términos generales, un equipo tiene un propósito que está alineado con un proyecto o que persigue un objetivo. Incluso si un equipo se formó tomando como base un interés compartido, la pertenencia al equipo cambiará a lo largo del tiempo y el debate podría llegar a quedarse anticuado; solo para resurgir de nuevo de una forma algo diferente en un equipo distinto.

Cada equipo tiene un principio: cuando el equipo se crea y los canales se configuran; una parte central: cuando el equipo se utiliza y se produce la colaboración para ajustarse al ritmo del flujo de trabajo; y, en ocasiones, un final: cuando el equipo ha completado su propósito y ha llegado al final de su vida útil. 

Para obtener más información, consulte [Administrar equipos en el Centro de administración de Microsoft Teams](manage-teams-in-modern-portal.md).

### <a name="stage-1-beginning"></a>Fase 1: Inicio

#### <a name="create-the-team"></a>Crear el equipo

El primer paso consiste en definir el objetivo del equipo (este puede variar entre procesos empresariales, estructura de la organización y proyectos, o bien puede ser el de crear un lugar común de colaboración, abierto y sin estructurar). La definición del objetivo del equipo va de la mano con la identificación de los miembros adecuados. Siempre que sea posible, es una buena idea fomentar la colaboración abierta y tratar de incorporar una gran cantidad de miembros. 

Los propietarios de equipo invitan a los miembros del equipo, definen la imagen del equipo y su descripción, y establecen los permisos para cada uno de los miembros. 

> [!Tip]
>  Lo ideal es identificar al menos dos miembros del equipo para poder responder ante una ausencia o reasignación.

#### <a name="team-origins"></a>Orígenes del equipo

Los equipos pueden formarse a partir de una gran variedad de métodos; entre ellos:

-   Agregue a los miembros mediante nombres de usuario o alias de correo electrónico individuales, o bien amplíe una lista de distribución.
-   Cree el equipo a partir de un equipo existente y use como plantilla su configuración de canales y de cualquier otra aplicación. Además, también puede usar su lista de pertenencia.
-   Agregue un equipo a un grupo de Microsoft 365 actual, que también le dé acceso al equipo al buzón de correo y el sitio de SharePoint.
-   Las API pueden crear equipos mediante programación que se basen en los atributos de la libreta de direcciones global (como la región o el departamento) o los procesos empresariales (las interacciones con clientes o las listas de participantes de clase, por ejemplo).

Utilice estos vínculos para obtener más información sobre cómo se organizan los equipos:

-   [Procedimientos recomendados para organizar los equipos en Teams](best-practices-organizing.md)
-   [Implementar chat, equipos, canales y aplicaciones](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
-   [Implementar reuniones y conferencias](deploy-meetings-microsoft-teams-landing-page.md)
-   [Implementar voz en la nube](cloud-voice-landing-page.md)


|    |     |
|-----------|------------|
| ![Un icono que representa los puntos de decisión](media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>¿Cuál es el propósito del equipo?</li><li>¿Quién pertenece al equipo?</li><li>¿El equipo será privado o público?</li><li>¿Los miembros nuevos pueden agregarse a sí mismos o lo hacen los propietarios de equipo?</li><li>¿Quién tendrá permisos para crear canales o agregar fichas, bots y conectores?</li></ul> |
| ![Un icono que representa los siguientes pasos](media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Crear el equipo.</li><li>Planificar los canales.</li></ul>|


#### <a name="set-up-channels"></a>Configurar los canales

Cualquier miembro o propietario de equipo que tenga los permisos adecuados podrá crear canales en un equipo. Es muy importante tener en cuenta el objetivo de cada canal: las opciones incluyen la colaboración en torno a proyectos, discusiones de temas o áreas de interés común. De forma predeterminada, cada equipo incluye un canal General. En la mayoría de equipos se necesitarán algunos más y los miembros crearán canales adicionales. Es probable que el conjunto de canales crezca de manera orgánica conforme vayan surgiendo nuevos temas o proyectos, y los debates pueden aumentar en mayor medida que el canal en el que empezaron.

Para despertar el interés, el propietario del canal puede publicar un mensaje de bienvenida, cargar documentos relevantes en la ficha **Archivos** o agregar fichas o conectores al canal. El propietario también establece la descripción del canal y puede marcar automáticamente como favoritos los canales importantes para que aparezcan de forma predeterminada para todos los miembros del equipo.

Considere la posibilidad de usar nombres de canal antes de crearlos, ya que cambiar el nombre de un canal en el equipo no cambiará el nombre de la carpeta correspondiente de la biblioteca de documentos de SharePoint, lo que puede resultar confuso para el usuario final. 

|    |     |
|-----------|------------|
| ![Un icono que representa los puntos de decisión](media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>¿Qué canales iniciales se agregarán al equipo?</li><li>¿Qué instrucciones, en caso de haber alguna, se ofrecerán para agregar nuevos canales? (¿Se configurarán según el proyecto, el tema, etc.?)</li></ul> |
| ![Un icono que representa los siguientes pasos](media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Crear canales iniciales.</li><li>Publicar un mensaje de bienvenida.</li><li>Empezar a colaborar.</li></ul>|

### <a name="stage-2-middle"></a>Fase 2: Parte central

Una vez comienza el trabajo en equipo, la pertenencia al equipo comenzará con toda seguridad a evolucionar también, junto con la jerarquía del canal. A menos que el equipo necesite estar controlado y bloqueado de forma estricta, es una buena idea animar a que se explore, incluso si esto conduce a un callejón sin salida. Conforme los usuarios se vayan sintiendo más cómodos, podrán experimentar con \@menciones de equipo, cómo marcar canales como favoritos y usar el canal General para publicar de forma cómoda. Cada equipo es diferente, por lo que debemos dejar que sea el uso el que guíe la evolución del diseño. Supervise el uso y el estado del equipo a través de las funcionalidades de creación de informes de Teams.

La confianza, la tolerancia y un espíritu de colaboración aumentan de forma orgánica a medida que las comunicaciones de grupo principales se inician y se mantienen a lo largo del tiempo en Teams. Los miembros de los equipos ven la utilidad de las conversaciones de grupo en los chats uno a uno. Cada equipo tiende a desarrollar su propia personalidad, con la ayuda de características como los Giphy y los adhesivos. Al mismo tiempo, es importante que se disuadan comportamientos superficiales o el acceso no autorizado cada vez que sucedan.

Como los equipos son organismos vivos, precisan que se les revise y se les atienda de vez en cuando. Estas son las prácticas recomendadas:

- Use expertos para mantener el nivel de uso si este empieza a caer, así como para descubrir y propagar nuevos comportamientos. 
- Administre a los invitados con buen juicio y asegúrese de que su acceso termina cuando termine la necesidad de la empresa.
- Anime a los miembros a usar conversaciones encadenadas con líneas de asunto para mejorar la visibilidad y la atención al desplazarse por un canal.
- Deje que los canales evolucionen a la par que las necesidades del negocio, añada nuevos canales según sea necesario y permita que los antiguos vayan desapareciendo (o considere la opción de archivarlos o eliminarlos si contienen datos confidenciales o efímeros, según sean los requisitos de retención).
- Forje nuevos equipos cuando surjan grupos más grandes o áreas basadas en un tema de interés.
- Pruebe con diferentes colaboraciones de canal, como las reuniones de canal o las conversaciones en ficha sobre documentos.
- Use la aplicación móvil de Microsoft Teams para aumentar la participación.

|    |     |
|-----------|------------|
| ![Un icono que representa los puntos de decisión](media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>¿Quién supervisará el uso para identificar los problemas?</li><li>¿Qué métricas se usarán para determinar si un equipo está en buen estado?</li><li>Identifique qué equipos han llegado al final de su vida útil.</li><li>Identifique los equipos que no están bien y que siguen teniendo un propósito, pero necesitan revitalizarse.</li></ul> |
| ![Un icono que representa el siguiente paso](media/audio_conferencing_image9.png)<br/>Paso siguiente|<ul><li>Implemente un proceso que supervise el estado de cada equipo.</li></ul>|

### <a name="stage-3-end"></a>Fase 3: Final

Cuando el trabajo de un equipo llega a su fin, es importante reconocer formalmente que ha terminado. De este modo, el equipo se queda con una sensación de cierre y se evita que alguien más acceda a información obsoleta. Podrá usar el equipo para llevar a cabo los rituales de cierre, como análisis finales y resúmenes ejecutivos.

Puede borrar los equipos que sabe que no necesita (por ejemplo, un equipo creado estrictamente para realizar pruebas o un equipo que contiene datos confidenciales). De hecho, los equipos se eliminan con una “eliminación temporal” que el departamento de TI puede revertir hasta en un máximo de 21 días (30 días para los Grupos de Microsoft 365). El hecho de eliminar equipos no afecta a los chats ni al contenido que se haya conservado según las directivas de cumplimiento. Los canales también tienen una "eliminación temporal" y se pueden invertir hasta veintiún días después de la eliminación. Al eliminar un canal, no se eliminará la carpeta ni su contenido de la biblioteca de documentos de SharePoint.

También se pueden usar las directivas de expiración y retención, además de las funcionalidades de archivado, para reducir la exposición de los equipos que ya no están activos o cuyos miembros han dejado la organización.

Puede que las directivas de retención aplicadas a Teams o a servicios asociados, como SharePoint, prohíban la eliminación de equipos. Además, tenga en cuenta que el contenido de un equipo a menudo constituye algo más que archivos de la biblioteca de documentos de SharePoint; también incluye las conversaciones, placas de Planner, wikis, resultados de Forms, reuniones grabadas, blocs de notas de OneNote y otros.

Para obtener información sobre cómo se configuran las directivas de expiración y retención, consulte [Información general de seguridad y cumplimiento en Microsoft Teams](security-compliance-overview.md).

|    |     |
|-----------|------------|
| ![Un icono que representa los puntos de decisión](media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Defina cómo es el final de la vida de un equipo.</li><li>Decida si desea mantener disponible el contenido de un equipo y durante cuánto tiempo.</li></ul> |
| ![Un icono que representa los siguientes pasos](media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Documentar las prácticas recomendadas y las lecciones aprendidas.</li><li>Archivar los datos, en caso necesario.</li></ul>|

## <a name="related-topics"></a>Temas relacionados

[Inicio rápido de gobierno para Teams](teams-adoption-governance-quick-start.md)
