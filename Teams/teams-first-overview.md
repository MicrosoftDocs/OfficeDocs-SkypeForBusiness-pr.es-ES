---
title: Implementación de Microsoft Teams primero
author: LaszloSomi
ms.author: lsomi
manager: swerth
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: lsomi
localization_priority: Normal
search.appverid: MET150
description: Use esta guía para realizar Microsoft Teams como su primera carga de trabajo de Microsoft 365 u Office 365.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: a30d5bed9443df3077ab7384cd8266d2f049148d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909484"
---
# <a name="roll-out-microsoft-teams-first"></a>Implementación de Microsoft Teams primero

Microsoft Teams puede ayudar a sus empleados a mantenerse conectados y colaborar entre ellos, especialmente en el momento de las vistas en las que el trabajo remoto es una realidad de los empleados de todo el mundo. Poder chatear, realizar reuniones de vídeo y colaborar en documentos de Office en Teams puede ayudar a las empresas a seguir siendo productivas. Tanto si es una pequeña empresa, una organización sin ánimo de lucro o una organización grande, puede empezar con Teams como la primera carga de trabajo en el conjunto de aplicaciones de Microsoft 365 u Office 365 antes de implementar cualquier otra aplicación o servicio de Office.

En este artículo se detallan las consideraciones que debe tomar con el enfoque de "Teams primero".

> [!IMPORTANT]
> Aunque Teams puede ser la primera carga de trabajo implementada en la nube de su organización, la implementación de Teams debe formar parte de la estrategia general de implementación en la nube.

Si ya ha lanzado otros servicios de Microsoft 365 u Office 365 y Teams es su próxima carga de trabajo para su implementación (en lugar de la primera), comience con Cómo lanzamiento [teams.](How-to-roll-out-teams.md)

## <a name="start-here"></a>Empiece aquí

Para empezar con la implementación de Teams First deberá cumplir como mínimo algunos requisitos previos. La siguiente lista mostrará lo que debe tener para su organización antes de que se pueda habilitar Teams:

1.  Una organización de Microsoft 365 u Office 365 configurada con su nombre de dominio

2.  Conectividad de Azure Active Directory (conexión AAD) o una solución de sincronización de identidades en la nube similar, con todos los atributos necesarios sincronizados con tu inquilino  
    Para comprender los atributos sincronizados con la sincronización de AAD, lea Sincronización de Azure AD Connect: Atributos [sincronizados con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

3.  Licencias de usuario adecuadas asignadas para Teams  
    Para comprender las licencias de Teams, lea la [descripción del servicio Microsoft Teams.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

4.  Red de la organización preparada para Teams  
    Para comprender la preparación de la red, [lea Preparar la red de su organización para Teams.](prepare-network.md)

5.  Permitir el acceso de red a Exchange, SharePoint y OneDrive para la Empresa en Microsoft 365 u Office 365: direcciones URL e intervalos de direcciones IP de [Office 365.](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)

> [!NOTE]
> Los inquilinos creados después del 1 de septiembre de 2019 se aprovisionan solo en modo Teams.
> 
> [!IMPORTANT]
> Si tiene implementado Skype Empresarial Server y su espacio empresarial se aprovisionó después del 1 de septiembre de 2019, póngase en contacto con el soporte técnico para habilitar las capacidades de coexistencia de Teams. Asegúrese de que la "directiva de actualización para toda la organización" esté establecida en "Modo <span class="underline">isla"</span> antes de asignar licencias de Teams a un usuario.

## <a name="migration-starting-points"></a>Puntos iniciales de la migración

Su viaje a Microsoft 365 u Office 365 y las características disponibles en Teams en función de su punto de partida y la existencia de Skype Empresarial local o Lync Server. En las siguientes secciones se detallan las capacidades básicas y las opciones de configuración, además de los requisitos previos anteriores. Hemos desglosado los escenarios de los puntos de partida en los temas siguientes:

**Configuración de equipos de** espacio empresarial: los modos de inquilino y usuario se usan para controlar el comportamiento del destinatario. Esta configuración se puede asignar en el nivel de inquilino o en el nivel de usuario de una organización. Para obtener más información, lea [Coexistencia con Skype Empresarial.](coexistence-chat-calls-presence.md)

**Chat/Comunicación externa en Teams:** los servicios de chat hacen referencia a conversaciones de chat de punto a punto o grupales dentro y dentro de la organización o externamente a la organización. Las comunicaciones externas también se conocen como federación en Skype Empresarial.

Crear y ver reuniones en **Teams:** un usuario siempre puede crear reuniones en línea mediante el complemento de Outlook Teams y el acceso telefónico RTC está disponible en todos los escenarios una vez que el usuario tiene licencia. Teams y Skype Empresarial almacenan información de calendario en el buzón de Exchange del usuario. El servidor exchange local debe estar Exchange Server 2016 CU3 o posterior para que el cliente de Teams pueda interactuar con el buzón del usuario. Sin el acceso al buzón de Exchange no se mostrará el icono de Calendario en Teams y el usuario no podrá ver, crear o modificar reuniones en el cliente de Teams.

**Características de llamadas VoIP/RTC** en Teams: las llamadas pueden ser de voz a través de IP (VoIP) o de red telefónica conmutada (RTC). La conectividad VoIP se produce de forma nativa entre clientes de Teams, mientras que la conectividad con RTC se produce cuando un usuario marca un número de teléfono externo.  

Teams admite dos tipos de conectividad con RTC. Plan de llamadas de Microsoft, cuando Microsoft proporciona infraestructura de telefonía, incluido el número de teléfono de un usuario, o la configuración de enrutamiento directo, donde el cliente proporciona la conectividad de telefonía a través de un controlador de borde de sesión (SBC) para el usuario de Teams.  
Para obtener más información, [lea ¿Qué plan de llamadas es adecuado para usted?](calling-plan-landing-page.md) y enrutamiento [directo del sistema telefónico.](direct-routing-landing-page.md)

**Colaboración de equipos y canales** en Teams: En Teams, los equipos son grupos de personas que se reúnen por causas de trabajo, proyectos o intereses comunes. Los equipos están configurados por canales. Cada canal se basa en un tema, como "Eventos de equipo", un nombre de departamento o solo por diversión. Los canales son los lugares donde se mantienen reuniones, se mantienen conversaciones y se trabaja conjuntamente en archivos. Durante la colaboración

OneDrive para la Empresa (uso compartido de archivos **P2P)** en Teams: fuera de equipos y canales, los usuarios de Teams pueden compartir archivos de punto a punto con OneDrive para la Empresa u otros programas de archivos compartidos P2P como Archivos Citrix, Dropbox, Box y Google Drive. Para OneDrive para la Empresa, un usuario debe tener asignada una licencia de SharePoint Online.

**Plataforma de** aplicaciones: las aplicaciones proporcionan herramientas integradas para que su organización obtenga más información sobre Teams. Estas aplicaciones combinan la funcionalidad de fichas, extensiones de mensajería, conectores y bots proporcionados por Microsoft, creados por un tercero o por desarrolladores de su organización.

**Características de seguridad y cumplimiento:** Teams tiene una amplia variedad de información para ayudarle con las áreas de cumplimiento, incluidas las directivas de retención, protección de pérdida de datos (DLP), exhibición de documentos electrónicos y retención legal para canales, chats y archivos, y búsqueda de registros de auditoría. Para obtener más información, lea [Seguridad y cumplimiento en Microsoft Teams.](security-compliance-overview.md)  

> [!NOTE]
> Las características de eDiscovery anticipada requieren licencias E5.

[Comparar las opciones de licencia.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)

Lea [cómo interactúan Exchange y Microsoft Teams](exchange-teams-interact.md) para saber qué características de cumplimiento están disponibles en su escenario.

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>Organizaciones **<span class="underline">sin</span>** Skype Empresarial o Lync Server

Este punto de partida supone que su organización no utiliza Skype Empresarial o Lync Server actualmente y que Teams será su primera aplicación en Microsoft 365 u Office 365. En la tabla siguiente se detalla la configuración de alto nivel y las capacidades del usuario final de Teams para los servicios principales.

<table>
<thead>
<tr class="header">
<th>Elemento</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configuración de Equipos de espacio empresarial</td>
<td>Solo en teams, todas las características de chat y llamadas están solo en Teams.</td>
</tr>
<tr class="even">
<td>Chat/Comunicación externa en Teams</td>
<td><p>Puede realizar comunicaciones internas (internos de Microsoft 365 u Office 365) y chats externos desde Teams.</p>
<p><em>Nota: Las entradas DNS deben configurarse para el acceso externo. Los registros DNS de Skype Empresarial son necesarios aunque no tenga Skype Empresarial local o en Microsoft 365 u Office 365 para permitir la federación con entornos de Lync y Skype Empresarial:<br />
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">Registros del sistema de nombres de dominio externos</a></em></p></td>
</tr>
<tr class="odd">
<td>Crear y ver reuniones en Teams</td>
<td><p>Puede crear reuniones internas y externas a través del complemento de Outlook.</p>
<p>La funcionalidad de acceso telefónico local y de salida RTC está disponible con las licencias de Audioconferencia.</p>
<p>El acceso al calendario de Teams requiere la implementación local de CU3+ de Exchange 2016 con Exchange hybrid established: Crear una implementación híbrida con <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">el Asistente para la configuración híbrida.</a> </p>
<p>Además de la configuración híbrida de Exchange, establezca la autenticación OAuth de Exchange: Configurar la autenticación de OAuth entre organizaciones de <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> Exchange y Exchange Online".</p>

</p></td>
</tr>
<tr class="even">
<td>Características de llamadas<br />
VoIP/RTC en Teams</td>
<td><p>VoIP interna y externamente para el espacio empresarial está disponible.</p>
<p>Los servicios RTC se pueden configurar a través de Microsoft Phone System, además de agregar un plan de llamadas de Microsoft o enrutamiento directo.</p></td>
</tr>
<tr class="odd">
<td>Colaboración de equipos y canales en Teams</td>
<td><p>Para obtener una experiencia completa, incluidas las características de cumplimiento, es necesario asignar al usuario una licencia de SharePoint Online.</p>
<p>No es necesaria la migración de sitios de SharePoint locales existentes.</p></td>
</tr>
<tr class="even">
<td>OneDrive para la Empresa (uso compartido de archivos P2P)</td>
<td>OneDrive para la Empresa requiere que un usuario tenga asignada una licencia de SharePoint Online. Sin este uso compartido de archivos punto a punto de licencia no será posible.</td>
</tr>
<tr class="odd">
<td>Plataforma de aplicaciones</td>
<td>Los usuarios podrán usar las aplicaciones designadas para ellos según las directivas de su empresa.<br />
Más información aquí: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Configuración de administración de aplicaciones en Teams</a></td>
</tr>
<tr class="even">
<td>Características de seguridad y cumplimiento</td>
<td><ul>
<li><p>Las directivas de retención están disponibles.</p></li>
<li><p>Se admite la exhibición de documentos electrónicos y la retención legal para el cumplimiento de los mensajes de canal.</p></li>
<li><p>Las directivas de prevención de pérdida de datos (DLP) están disponibles.</p></li>
</ul>
<p>Conjunto completo de características disponible con Exchange Online; Exchange local admite la mayoría de estas características. Para obtener una lista completa, vea <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">cómo interactúan Exchange y Teams.</a></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>Pasos de habilitación para organizaciones sin Skype Empresarial o Lync Server

1.  Cumpla los requisitos previos detallados en la sección anterior Comenzar aquí

2.  Cambie el espacio empresarial al modo solo teams (solo para inquilinos existentes): [establecer la configuración de coexistencia y actualización.](setting-your-coexistence-and-upgrade-settings.md)

3.  Configure el inquilino de acuerdo con las directivas empresariales/empresariales de su empresa: administre la configuración de [Microsoft Teams para su organización.](enable-features-office-365.md)

4.  Implementar el cliente de Teams a los usuarios: [Obtener clientes para Teams](get-clients.md)

5.  Impulsar el programa de adopción  
    [Adoptar Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Lista de comprobación para el inicio rápido de la adopción de Microsoft Teams](teams-adoption-quick-start-checklist.md)

6.  Empezar a planificar el desplazamiento de otras cargas de trabajo a Microsoft 365 u Office 365

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>Organizaciones **<span class="underline">con</span>** Skype Empresarial o Lync Server

En este punto de partida se supone que su organización utiliza Skype Empresarial 2019 o 2015+ o Lync 2013+ servidor local. Ya tenemos amplias directrices para las organizaciones que migran de servidores locales a Teams y deben seguirse para estos escenarios. Esta guía es específica para el escenario en el que Teams es la primera aplicación que utiliza en Microsoft 365 u Office 365. En la tabla siguiente se detalla la configuración de alto nivel y las capacidades del usuario final de Teams para los servicios principales.

<table>
<thead>
<tr class="header">
<th>Elemento</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configuración de Equipos de espacio empresarial</td>
<td>Modo de islas.</td>
</tr>
<tr class="even">
<td>Chat/Comunicación externa en Teams</td>
<td>Interna solo dentro de su propio espacio empresarial, la comunicación externa (federación) es a través de su implementación de Skype Empresarial o Lync Server.</td>
</tr>
<tr class="odd">
<td>Crear y ver reuniones en Teams</td>
<td><p>Puede crear reuniones internas y externas a través del complemento de Outlook.</p>
<p>La funcionalidad de acceso telefónico local y de salida RTC está disponible con las licencias de Audioconferencia.</p>
<p>El acceso al calendario de Teams requiere la implementación local de CU3+ de Exchange 2016 con Exchange híbrido establecido:<br />
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Cree una implementación híbrida con el Asistente para la configuración híbrida.</a></p>
<p>El administrador puede controlar el complemento de Outlook de Skype Empresarial a través del atributo PreferredMeetingProviderForIslandsMode de la directiva de reunión de Teams:<a href="https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy.</a></p> 
</td>
</tr>
<tr class="even">
<td>Características de llamadas<br />
VoIP/RTC en Teams</td>
<td><p>VoIP internamente para el espacio empresarial está disponible.</p>
<p>Los servicios de RTC o de plan de llamadas no están disponibles hasta que se mueve el usuario a la experiencia solo de Teams.</p></td>
</tr>
<tr class="odd">
<td>Colaboración de equipos y canales en Teams</td>
<td><p>Para obtener una experiencia completa, incluidas las características de cumplimiento, es necesario asignar al usuario una licencia de SharePoint Online.</p>
<p>No es necesaria la migración de sitios de SharePoint locales existentes.</p></td>
</tr>
<tr class="even">
<td>OneDrive para la Empresa (uso compartido de archivos P2P)</td>
<td>OneDrive para la Empresa requiere que un usuario tenga asignada una licencia de SharePoint Online. Sin esta licencia no será posible compartir archivos por punto.</td>
</tr>
<tr class="odd">
<td>Plataforma de aplicaciones</td>
<td>Los usuarios podrán usar las aplicaciones designadas para ellos según las directivas de su empresa.<br />
Más información aquí: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Configuración de administración de aplicaciones en Teams</a></td>
</tr>
<tr class="even">
<td>Características de seguridad y cumplimiento</td>
<td><ul>
<li><p>Las directivas de retención están disponibles.</p></li>
<li><p>Se admite la exhibición de documentos electrónicos y la retención legal para el cumplimiento de los mensajes de canal.</p></li>
<li><p>Las directivas de prevención de pérdida de datos (DLP) están disponibles.</p></li>
</ul>
<p>Conjunto completo de características disponible con Exchange Online; Exchange local admite la mayoría de estas características. Para obtener una lista completa, vea <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">cómo interactúan Exchange y Teams.</a></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>Pasos de habilitación para organizaciones con Skype Empresarial Server  

1.  Cumpla los requisitos previos detallados en la sección Anterior Comenzar aquí.

2.  Cambiar el inquilino al modo Islas (para inquilinos aprovisionados DESPUÉS del 1/9/2019, ponte en contacto con el servicio de soporte técnico para realizar este cambio)  
    [Configurar su coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md)

3.  Configurar el inquilino de acuerdo con las directivas de empresa/empresa de su empresa  
    [Administrar la configuración de Microsoft Teams para su organización](enable-features-office-365.md)

4.  Implementar el cliente de Teams  
    [Obtener clientes para Microsoft Teams](get-clients.md)

5.   Impulsar el programa de adopción  
    [Adoptar Microsoft Teams](adopt-microsoft-teams-landing-page.md)<br/>
    [Lista de comprobación para el inicio rápido de la adopción de Microsoft Teams](teams-adoption-quick-start-checklist.md)

6.  Empezar a planificar el desplazamiento de otras cargas de trabajo a Microsoft 365 u Office 365

7.  Establecer Skype Empresarial híbrido y seguir las rutas de actualización recomendadas para los servidores de Skype Empresarial y Lync  
    [Actualizar de Skype Empresarial local a Teams](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>Instrucción de cierre

Microsoft Teams puede permitir que su organización pueda reunir a todos los empleados, trabajadores de la información y trabajadores de la línea frontal en una sola plataforma. Puedes empezar [hoy](https://products.office.com/microsoft-teams/group-chat-software) mismo. Puedes estar en contacto con todos nuestros anuncios más recientes y con las actualizaciones mensuales de productos [aquí.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)

Además, a medida que empresas de todo el mundo administran la situación actual de COVID-19, hemos creado una serie de contenido que le ayudará a usar Teams para obtener el máximo impacto en su organización.

  - Nuestro [compromiso con los clientes durante covid-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)

  - [Dentro de dos semanas: lo que hemos aprendido sobre el trabajo remoto](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [Realizar reuniones y eventos en línea](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [Ayudar a las pequeñas y medianas empresas a trabajar de forma remota con Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [Transformación digital de eventos en directo: observaciones de Bob Bejano desde la línea frontal](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [Las 9 formas principales en que TI de Microsoft permite trabajar de forma remota a sus empleados](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/).

  - [Trabaje de forma remota, manténgase seguro: sugerencias para LOS MÁSÓXOS](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [Ayudar a profesores y alumnos a cambiar al aprendizaje remoto](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [Mantenerse productivo mientras trabaja de forma remota con Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>Referencia de los Servicios de soporte técnico

Teams se basa en Exchange Online, SharePoint Online, OneDrive para la Empresa y Grupos de Microsoft 365 para proporcionar a los usuarios una experiencia de Microsoft 365 u Office 365 totalmente integrada. Como se indicó anteriormente, Teams trabajará sin implementar estos servicios de forma completa, con funcionalidades limitadas. Puede obtener más información sobre Teams y sus requisitos previos aquí: [Le damos la bienvenida a Teams.](teams-overview.md)

Para obtener información específica sobre cada uno de los servicios enumerados anteriormente, siga los siguientes vínculos:

  - Exchange Online se usa para las características de calendario y almacenar mensajes de punto a punto en Teams. Para obtener más información, lea [cómo interactúan Exchange y Teams](exchange-teams-interact.md)

> [!IMPORTANT]
> Para la interoperabilidad de Teams con Exchange local, debe configurar el nuevo protocolo de autenticación OAuth de Exchange como se describe en Configurar autenticación OAuth entre organizaciones [de Exchange y Exchange Online.](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

  - SharePoint se usa para compartir archivos en canales, mientras que /OneDrive para la Empresa se usa para el uso compartido de archivos en chats grupales o uno a uno. Para obtener más información, lea [Cómo interactúan SharePoint Online y OneDrive para la Empresa con Microsoft Teams.](sharepoint-onedrive-interact.md)

  - [Los grupos de Microsoft 365 se](office-365-groups.md) utilizan para la creación o administración de equipos y canales.


## <a name="related-topics"></a>Temas relacionados

[Carteles de soluciones de telefonía y arquitectura de TI de Microsoft Teams](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[Planear la conectividad híbrida entre Skype Empresarial Server y Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[Dar soporte a los trabajadores remotos mediante Teams](support-remote-work-with-teams.md)

[Trabajar de forma remota con Microsoft 365](https://aka.ms/remote-work)
