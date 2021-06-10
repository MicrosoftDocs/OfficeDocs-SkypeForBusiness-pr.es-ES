---
title: Implementación en Microsoft Teams Primero
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
description: Use esta guía para Microsoft Teams como su primera Microsoft 365 o Office 365 trabajo.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 81ecf9a0f963a1be577149c585424c140df2abd5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119359"
---
# <a name="roll-out-microsoft-teams-first"></a>Implementación en Microsoft Teams Primero

Microsoft Teams ayudar a sus empleados a mantenerse conectados y colaborar entre sí, especialmente en el momento sin precedentes actual en el que el trabajo remoto es una realidad de los empleados de todo el mundo. Poder chatear, realizar reuniones de vídeo y colaborar en Office documentos dentro de Teams ayudar a las empresas a mantenerse productivas. Ya sea una pequeña empresa, una organización sin ánimo de lucro o una organización grande, puede empezar con Teams como la primera carga de trabajo dentro de un conjunto de aplicaciones Microsoft 365 o Office 365 antes de implementar cualquier otro Aplicación de Office o servicio.

En este artículo se detallan las consideraciones que debe realizar con el enfoque "Teams primero".

> [!IMPORTANT]
> Aunque Teams puede ser la primera carga de trabajo implementada en la nube de su organización, la implementación de Teams debe formar parte de su estrategia de implementación en la nube general.

Si ya ha lanzado otros servicios de Microsoft 365 o Office 365 y Teams es la siguiente carga de trabajo que se va a realizar (en lugar de la primera), empiece por [Cómo](./deploy-overview.md)Teams .

## <a name="start-here"></a>Empiece aquí

Para empezar con su Teams primera implementación, tendrá que cumplir como mínimo algunos requisitos previos. La siguiente lista mostrará lo que debe tener en su organización antes de que Teams se pueda habilitar:

1.  Una Microsoft 365 o Office 365 configurada con su nombre de dominio

2.  Azure Active Directory conectividad (conexión AAD) o una solución de sincronización de identidad de nube similar, con todos los atributos necesarios sincronizados con el inquilino  
    Para comprender los atributos sincronizados con la sincronización de AAD, lea [Azure AD Conectar sincronización: Atributos sincronizados con Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

3.  Licencias de usuario adecuadas asignadas para Teams  
    Para comprender Teams licencias, [lea Microsoft Teams descripción del servicio](/office365/servicedescriptions/teams-service-description).

4.  Red de la organización preparada para Teams  
    Para comprender la preparación de la red, lea [Preparar la red de su organización para Teams](prepare-network.md).

5.  Permitir el acceso de red a Exchange, Sharepoint y OneDrive para la Empresa en Microsoft 365 o Office 365: Office 365 direcciones URL e [intervalos de direcciones IP.](/office365/enterprise/urls-and-ip-address-ranges)

> [!NOTE]
> Los inquilinos creados después del 1 de septiembre de 2019 se aprovisionan en Teams modo único.
> 
> [!IMPORTANT]
> Si ha implementado Skype Empresarial Server y el espacio empresarial se aprovisionamiento después del 1 de septiembre de 2019, póngase en contacto con el soporte técnico para habilitar las capacidades de coexistencia para Teams. Asegúrese de que la "directiva de actualización de toda la organización" está establecida en "Modo <span class="underline">isla"</span> antes de asignar cualquier licencia de Teams a un usuario.

## <a name="migration-starting-points"></a>Puntos iniciales de migración

Viaje a Microsoft 365 o Office 365 y características disponibles en Teams según su punto de partida y la existencia de servidores locales Skype Empresarial Lync Server. En las secciones siguientes se detallarán las capacidades básicas y las opciones de configuración, además de los requisitos previos anteriores. Hemos desglosado los escenarios de punto de partida para los temas siguientes:

**Configuración Teams inquilino:** los modos inquilino y usuario se usan para controlar el comportamiento del destinatario. Esta configuración se puede asignar en el nivel de inquilino o en el nivel de usuario de una organización. Para obtener más información, lea [Coexistencia con Skype Empresarial](coexistence-chat-calls-presence.md).

**Chat/comunicación externa en Teams:** los servicios de chat se refieren a conversaciones de chat de punto a punto o grupales dentro y dentro de la organización o externamente a la organización. La comunicación externa también se conoce como federación en Skype Empresarial.

Crear y ver reuniones en **Teams:** un usuario siempre puede crear reuniones en línea mediante el complemento Outlook Teams y el acceso telefónico RTC está disponible en todos los escenarios una vez que el usuario tiene licencia. Teams y Skype Empresarial la información de calendario en el buzón de correo Exchange usuario. El servidor Exchange local debe estar Exchange Server CU3 de 2016 o posterior para que el cliente Teams pueda interactuar con el buzón del usuario. Sin Exchange buzón de correo, el icono Calendario de Teams no aparecerá y el usuario no podrá ver, crear o modificar reuniones en el Teams cliente.

**Características de llamadas VoIP /RTC** en Teams: Las llamadas pueden ser Voz a través de IP (VoIP) o Red telefónica conmutada (RTC). La conectividad VoIP se produce de forma nativa entre Teams clientes, mientras que la conectividad RTC se produce cuando un usuario marca un número de teléfono externo.  

Teams dos tipos de conectividad RTC. Plan de llamadas de Microsoft, cuando Microsoft proporciona infraestructura de telefonía, incluido el número de teléfono de un usuario, o la configuración de enrutamiento directo, donde el cliente proporciona la conectividad de telefonía a través de un controlador de borde de sesión (SBC) para el Teams usuario.  
Para obtener más información, lea [¿Qué plan de llamadas es adecuado para usted?](calling-plan-landing-page.md) y [Sistema telefónico enrutamiento directo.](direct-routing-landing-page.md)

**Teams y canales en Teams:** en Teams, los equipos son grupos de personas que se reúnen para trabajar, proyectos o intereses comunes. Teams están hechos de canales. Cada canal se basa en un tema, como "Eventos de grupo", un nombre de departamento o simplemente por diversión. Los canales son los lugares donde se mantienen reuniones, se mantienen conversaciones y se trabaja en archivos juntos. Durante la colaboración

OneDrive para la Empresa (uso compartido de archivos **P2P)** en Teams: Fuera de Teams y canales, los usuarios de Teams pueden compartir archivos de punto a punto con OneDrive para empresas u otros programas de archivos de uso compartido P2P como Archivos Citrix, DropBox, Box y Google Drive. Para OneDrive para empresas, un usuario debe tener SharePoint licencia en línea asignada.

**Plataforma de aplicaciones:** las aplicaciones proporcionan herramientas integradas para que su organización obtenga más información sobre Teams. Estas aplicaciones combinan la funcionalidad de pestañas, extensiones de mensajería, conectores y bots proporcionados por Microsoft, creados por un tercero o por desarrolladores de su organización.

Características de seguridad y **cumplimiento:** Teams tiene una amplia gama de información para ayudarle con las áreas de cumplimiento, incluidas las directivas de retención, protección contra pérdida de datos (DLP), exhibición de documentos electrónicos y retención legal para canales, chats y archivos, búsqueda de registros de auditoría. Para obtener más información, lea [Seguridad y cumplimiento en Microsoft Teams](security-compliance-overview.md).  

> [!NOTE]
> Las características de eDiscovery avanzadas requieren licencias E5.

[Comparar opciones de licencias.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)

Lea [Cómo Exchange y Microsoft Teams interactúan](exchange-teams-interact.md) para saber qué características de cumplimiento están disponibles en su escenario.

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>Organizaciones **<span class="underline">sin</span>** Skype Empresarial o Lync Server

Este punto de partida supone que su organización no usa Skype Empresarial o Lync Server actualmente y Teams será su primera aplicación en Microsoft 365 o Office 365. En la tabla siguiente se detalla la configuración de alto nivel y las capacidades de usuario final para Teams para los servicios principales.

<table>
<thead>
<tr class="header">
<th>Elemento</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configuración Teams inquilino</td>
<td>Teams Solo en modo, todas las características de chat y llamadas están Teams solo.</td>
</tr>
<tr class="even">
<td>Chat y comunicación externa en Teams</td>
<td><p>Las comunicaciones internas (Microsoft 365 o Office 365) y de chat externo posibles desde Teams.</p>
<p><em>Nota: Las entradas DNS deben configurarse para el acceso externo. Skype Empresarial Los registros DNS son necesarios aunque no tenga Skype Empresarial locales, o en Microsoft 365 o Office 365, para permitir la federación con Lync y Skype Empresarial entornos:<br />
<a href="/office365/enterprise/external-domain-name-system-records">Registros del sistema de nombres de dominio externos</a></em></p></td>
</tr>
<tr class="odd">
<td>Crear y ver reuniones en Teams</td>
<td><p>Puede crear reuniones internas y externas a través Outlook complemento.</p>
<p>La capacidad de marcado RTC y de marcado de salida está disponible con las licencias de audioconferencia.</p>
<p>Teams de calendario requiere Exchange 2016 CU3 Exchange+ local implementado con una implementación híbrida establecida: Crear una implementación híbrida con el Asistente para configuración <a href="/exchange/hybrid-deployment/deploy-hybrid">híbrida.</a> </p>
<p>Además de Exchange configuración híbrida, establezca Exchange autenticación de OAuth: Configurar la autenticación de OAuth entre Exchange y <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> Exchange Online organizaciones".</p>

</p></td>
</tr>
<tr class="even">
<td>Características de llamadas<br />
VoIP /RTC en Teams</td>
<td><p>VoIP interna y externamente para el inquilino está disponible.</p>
<p>Los servicios RTC se pueden configurar mediante Teléfono Microsoft sistema, además de agregar un plan de llamadas de Microsoft o enrutamiento directo.</p></td>
</tr>
<tr class="odd">
<td>Teams y canales en Teams</td>
<td><p>Para obtener una experiencia completa, incluidas las características de cumplimiento normativo, es necesario asignar SharePoint licencia en línea al usuario.</p>
<p>No se requiere la migración de sitios SharePoint locales existentes.</p></td>
</tr>
<tr class="even">
<td>OneDrive para la Empresa (uso compartido de archivos P2P)</td>
<td>OneDrive para la Empresa requiere que un usuario tenga asignada una SharePoint en línea. Sin este uso compartido de archivos punto a punto de licencia no será posible.</td>
</tr>
<tr class="odd">
<td>Plataforma de aplicaciones</td>
<td>Los usuarios podrán usar las aplicaciones designadas disponibles para ellas según las directivas de su empresa.<br />
Más información aquí: <a href="/microsoftteams/admin-settings">Configuración de administración de aplicaciones en Teams</a></td>
</tr>
<tr class="even">
<td>Características de seguridad y cumplimiento</td>
<td><ul>
<li><p>Las directivas de retención están disponibles.</p></li>
<li><p>Se admite la exhibición de documentos electrónicos y la retención legal para el cumplimiento en los mensajes de canal.</p></li>
<li><p>Las directivas de prevención de pérdida de datos (DLP) están disponibles.</p></li>
</ul>
<p>Conjunto de características completo disponible con Exchange Online; Exchange local admite la mayoría de estas características. Para obtener una lista completa, <a href="/MicrosoftTeams/exchange-teams-interact">vea Exchange y Teams interactuar.</a></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>Pasos de habilitación para organizaciones sin Skype Empresarial o Lync Server

1.  Cumplir los requisitos previos detallados en la sección Empezar aquí anterior

2.  Cambiar el espacio empresarial al Teams único (solo para inquilinos existentes): Establecer la configuración de [coexistencia y actualización.](setting-your-coexistence-and-upgrade-settings.md)

3.  Configure su inquilino de acuerdo con las directivas empresariales o de empresa de su empresa: Administrar Microsoft Teams [configuración de su organización.](enable-features-office-365.md)

4.  Implementar el Teams a los usuarios: [Obtener clientes para Teams](get-clients.md)

5.  Impulsar el programa de adopción  
    [Adoptar Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Lista de comprobación para el inicio rápido de la adopción de Microsoft Teams](teams-adoption-quick-start-checklist.md)

6.  Empiece a planear mover otras cargas de trabajo Microsoft 365 o Office 365

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>Organizaciones **<span class="underline">con</span>** Skype Empresarial o Lync Server

Este punto de partida supone que su organización usa Skype Empresarial servidor 2019 o 2015+ o Lync 2013+ local. Ya tenemos instrucciones exhaustivas para las organizaciones que migran desde servidores locales a Teams y deben seguirse para estos escenarios. Esta guía es específica del escenario en el que Teams es la primera aplicación que usa en Microsoft 365 o Office 365. En la tabla siguiente se detalla la configuración de alto nivel y las capacidades de usuario final para Teams para los servicios principales.

<table>
<thead>
<tr class="header">
<th>Elemento</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configuración Teams inquilino</td>
<td>Modo Islas.</td>
</tr>
<tr class="even">
<td>Chat y comunicación externa en Teams</td>
<td>Dentro de su propio espacio empresarial, la comunicación externa (federación) es a través de su Skype Empresarial o implementación de Lync Server.</td>
</tr>
<tr class="odd">
<td>Crear y ver reuniones en Teams</td>
<td><p>Puede crear reuniones internas y externas a través Outlook complemento.</p>
<p>La capacidad de marcado RTC y de marcado de salida está disponible con las licencias de audioconferencia.</p>
<p>Teams acceso de calendario requiere Exchange 2016 CU3+ local implementado con Exchange híbrido establecido:<br />
<a href="/exchange/hybrid-deployment/deploy-hybrid">Cree una implementación híbrida con el Asistente para configuración híbrida.</a></p>
<p>El administrador puede controlar el complemento Skype Empresarial Outlook mediante el atributo PreferredMeetingProviderForIslandsMode de la directiva de reunión de Teams:<a href="/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy</a>.</p> 
</td>
</tr>
<tr class="even">
<td>Características de llamadas<br />
VoIP /RTC en Teams</td>
<td><p>VoIP internamente para el inquilino está disponible.</p>
<p>Los servicios RTC o planes de llamadas no están disponibles hasta que el usuario se mueve a Teams solo experiencia.</p></td>
</tr>
<tr class="odd">
<td>Teams y canales en Teams</td>
<td><p>Para obtener una experiencia completa, incluidas las características de cumplimiento normativo, es necesario asignar SharePoint licencia en línea al usuario.</p>
<p>No se requiere la migración de sitios SharePoint locales existentes.</p></td>
</tr>
<tr class="even">
<td>OneDrive para la Empresa (uso compartido de archivos P2P)</td>
<td>OneDrive para la Empresa requiere que un usuario tenga asignada una SharePoint en línea. Sin esta licencia, no será posible compartir archivos por punto.</td>
</tr>
<tr class="odd">
<td>Plataforma de aplicaciones</td>
<td>Los usuarios podrán usar las aplicaciones designadas disponibles para ellas según las directivas de su empresa.<br />
Más información aquí: <a href="/microsoftteams/admin-settings">Configuración de administración de aplicaciones en Teams</a></td>
</tr>
<tr class="even">
<td>Características de seguridad y cumplimiento</td>
<td><ul>
<li><p>Las directivas de retención están disponibles.</p></li>
<li><p>Se admite la exhibición de documentos electrónicos y la retención legal para el cumplimiento en los mensajes de canal.</p></li>
<li><p>Las directivas de prevención de pérdida de datos (DLP) están disponibles.</p></li>
</ul>
<p>Conjunto de características completo disponible con Exchange Online; Exchange local admite la mayoría de estas características. Para obtener una lista completa, vea <a href="/MicrosoftTeams/exchange-teams-interact">Exchange y Teams interactuar.</a></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>Pasos de habilitación para organizaciones con Skype Empresarial Server  

1.  Cumpla los requisitos previos detallados en la sección Empezar aquí anterior.

2.  Cambiar el inquilino al modo Islas (para inquilinos aprovisionados después del 1/9/2019, póngase en contacto con el soporte técnico para realizar este cambio)  
    [Configurar su coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md)

3.  Configurar el espacio empresarial de acuerdo con las directivas de empresa o empresa de su empresa  
    [Administrar la configuración de Microsoft Teams para su organización](enable-features-office-365.md)

4.  Implementar el Teams cliente  
    [Obtener clientes para Microsoft Teams](get-clients.md)

5.   Impulsar el programa de adopción  
    [Adoptar Microsoft Teams](adopt-microsoft-teams-landing-page.md)<br/>
    [Lista de comprobación para el inicio rápido de la adopción de Microsoft Teams](teams-adoption-quick-start-checklist.md)

6.  Empiece a planear mover otras cargas de trabajo Microsoft 365 o Office 365

7.  Establecer Skype Empresarial híbrido y seguir las rutas de actualización recomendadas para Skype Empresarial y servidores lync  
    [Actualizar de Skype Empresarial local a Teams](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>Instrucción de cierre

Microsoft Teams puede ser un habilitador para que su organización pueda reunir a todos los empleados, los trabajadores de la información y los trabajadores de Frontline en una única plataforma. Puede empezar [hoy](https://products.office.com/microsoft-teams/group-chat-software) mismo. Puedes mantenerte en contacto con todos nuestros últimos anuncios y actualizaciones mensuales de productos [aquí.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)

Además, a medida que empresas de todo el mundo administran la situación actual de COVID-19, hemos creado una serie de contenido que le ayudará a usar Teams para el máximo impacto en su organización.

  - Nuestro [compromiso con los clientes durante COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)

  - [2 semanas después: lo que hemos aprendido sobre el trabajo remoto](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [Ofrecer reuniones y eventos en línea](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [Ayudar a las pequeñas y medianas empresas a trabajar de forma remota con Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [Transformación digital de eventos en directo: observaciones de Bob Bejan desde la primera línea](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [Las 9 formas principales en que TI de Microsoft permite trabajar de forma remota a sus empleados](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/).

  - [Trabajar de forma remota, mantenerse seguro: sugerencias para OSC](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [Ayudar a profesores y alumnos a cambiar al aprendizaje remoto](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [Mantenerse productivo mientras trabaja de forma remota con Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>Referencia de servicios de soporte técnico

Teams se basa en Exchange Online, SharePoint Online, OneDrive para la Empresa y Microsoft 365 Groups para proporcionar a los usuarios una experiencia Microsoft 365 o Office 365 integrada. Como se ha indicado anteriormente, Teams funcionará sin la implementación completa de estos servicios, con capacidades limitadas. Puede obtener más información sobre Teams y sus requisitos previos aquí: Bienvenido [a Teams](teams-overview.md).

Para obtener información específica sobre cada uno de los servicios enumerados anteriormente, siga los siguientes vínculos:

  - Exchange Online se usa para las características de calendario y para almacenar mensajes de punto a punto en Teams. Para obtener más información, lea [Cómo Exchange y Teams interactuar](exchange-teams-interact.md)

> [!IMPORTANT]
> Para Teams interoperabilidad con Exchange local, debe configurar el nuevo protocolo de autenticación de [OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)de Exchange como se describe en Configurar autenticación de OAuth entre Exchange y Exchange Online organizaciones.

  - SharePoint se usa para el uso compartido de archivos en canales, mientras que /OneDrive para la Empresa se usa para el uso compartido de archivos en chat grupal o 1:1. Para obtener más información, lea [Cómo SharePoint en línea OneDrive para la Empresa interactuar con Microsoft Teams](sharepoint-onedrive-interact.md).

  - [Microsoft 365 se usan](office-365-groups.md) para la creación y administración de equipos y canales.


## <a name="related-topics"></a>Temas relacionados

[Carteles de soluciones de telefonía y arquitectura de TI de Microsoft Teams](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[Planear la conectividad híbrida entre Skype Empresarial Server y Office 365](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[Soporte técnico para trabajadores remotos con Teams](support-remote-work-with-teams.md)

[Trabajar de forma remota con Microsoft 365](https://aka.ms/remote-work)