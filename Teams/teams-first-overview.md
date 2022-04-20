---
title: Implementar primero Microsoft Teams
author: LaszloSomi
ms.author: lsomi
manager: swerth
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: lsomi
ms.localizationpriority: medium
search.appverid: MET150
description: Use esta guía para implementar Microsoft Teams como el primer Microsoft 365 o Office 365 carga de trabajo.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: f6dba57003aaa58b9d0b72e7e866da261bed578e
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922691"
---
# <a name="roll-out-microsoft-teams-first"></a>Implementar primero Microsoft Teams

Microsoft Teams pueden ayudar a los empleados a mantenerse conectados y colaborar entre sí, especialmente en un momento sin precedentes en el que el trabajo remoto es una realidad para los empleados de todo el mundo. Poder chatear, realizar reuniones de vídeo y colaborar en documentos de Office dentro de Teams puede ayudar a las empresas a seguir siendo productivas. Tanto si es una pequeña empresa, una organización sin ánimo de lucro o una organización grande, puede empezar con Teams como la primera carga de trabajo en Microsoft 365 o Office 365 conjunto de aplicaciones antes de implementar cualquier otro Aplicación de Office o servicio.

En este artículo se describen las consideraciones que debe tener en cuenta con el enfoque "Teams Primero".

> [!IMPORTANT]
> Aunque Teams puede ser la primera carga de trabajo implementada en la nube de su organización, la implementación de Teams debe formar parte de su estrategia general de implementación en la nube.

Si ya ha implementado otros servicios de Microsoft 365 o Office 365 y Teams es la siguiente carga de trabajo que se implementará (en lugar de la primera), comience con [Cómo implementar Teams](./deploy-overview.md).

## <a name="start-here"></a>Empiece aquí

Para empezar con su Teams Primera implementación, tendrá que cumplir como mínimo algunos requisitos previos. La siguiente lista mostrará lo que debe tener en vigor para su organización antes de que se pueda habilitar Teams:

1.  Una Microsoft 365 o Office 365 organización configurada con su nombre de dominio

2.  Azure Active Directory conectividad (AAD conectar) o una solución de sincronización de identidad de nube similar, con todos los atributos necesarios sincronizados con su inquilino  
    Para comprender los atributos sincronizados con AAD sincronización, lea [Azure AD Conectar sincronización: Atributos sincronizados con Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

3.  Licencias de usuario adecuadas asignadas para Teams  
    Para comprender Teams licencias, lea [Microsoft Teams descripción del servicio](/office365/servicedescriptions/teams-service-description).

4.  La red de la organización preparada para Teams  
    Para comprender la preparación de la red, lea [Preparar la red de su organización para Teams](prepare-network.md).

5.  Permitir el acceso de red a Exchange, SharePoint y OneDrive para la Empresa en Microsoft 365 o Office 365: [direcciones URL Office 365 e intervalos de direcciones IP](/office365/enterprise/urls-and-ip-address-ranges).

> [!NOTE]
> Los inquilinos creados después del 1 de septiembre de 2019 se aprovisionan en modo Solo Teams.
> 
> [!IMPORTANT]
> Si ha implementado Skype Empresarial Server y su inquilino se ha aprovisionado después del 1 de septiembre de 2019, póngase en contacto con el soporte técnico para habilitar las capacidades de coexistencia para Teams. Asegúrese de que la "Directiva de actualización para toda la organización" esté establecida en "Modo de isla" <span class="underline">antes</span> de asignar licencias de Teams a un usuario.

## <a name="migration-starting-points"></a>Puntos de inicio de la migración

Su viaje a Microsoft 365 o Office 365 y características disponibles en Teams en función de su punto de inicio y de la existencia de Skype Empresarial local o servidor de Lync. En las siguientes secciones se detallarán las capacidades básicas y las opciones de configuración, además de los requisitos previos anteriores. Hemos desglosado los escenarios de punto de partida en los siguientes temas:

**Configuración de Teams** de espacio empresarial: los modos de inquilino y usuario se usan para controlar el comportamiento del destinatario. Esta configuración se puede asignar en el nivel de inquilino o en el nivel de usuario de una organización. Para obtener más información, lea [Coexistencia con Skype Empresarial](coexistence-chat-calls-presence.md).

**Chat/comunicación externa en Teams**: Los servicios de chat hacen referencia a conversaciones de chat de punto a punto o grupales dentro y dentro de la organización o externamente a la organización. La comunicación externa también se conoce como federación en Skype Empresarial.

**Crear y ver reuniones en Teams**: un usuario siempre puede crear reuniones en línea a través de Outlook Teams complemento y el acceso telefónico RTC está disponible en todos los escenarios una vez que el usuario tiene licencia. Teams y Skype Empresarial almacenar información de calendario en el buzón Exchange del usuario. El servidor de Exchange local debe ser Exchange Server CU3 de 2016 o superior para que el cliente de Teams pueda interactuar con el buzón del usuario. Sin Exchange buzón de correo, el icono calendario de Teams no aparecerá y el usuario no podrá ver, crear o modificar reuniones en el cliente de Teams.

**Características de llamadas VoIP/RTC en Teams**: las llamadas pueden ser de voz a través de IP (VoIP) o de red telefónica conmutada (RTC). La conectividad VoIP se produce de forma nativa entre Teams clientes, mientras que la conectividad RTC se produce cuando un usuario marca un número de teléfono externo.  

Teams admiten dos tipos de conectividad CON RTC. Plan de llamadas de Microsoft, cuando Microsoft proporciona infraestructura de telefonía, incluido el número de teléfono de un usuario, o la configuración de enrutamiento directo, donde el cliente proporciona la conectividad de telefonía a través de un controlador de borde de sesión (SBC) para el usuario de Teams.  
Para obtener más información, lea [¿Qué plan de llamadas es el adecuado para usted?](calling-plan-landing-page.md) y [Sistema telefónico Enrutamiento directo](direct-routing-landing-page.md).

**Teams y los canales de colaboración en Teams**: en Teams, los equipos son grupos de personas que se reúnen por cuestiones de trabajo, proyectos o intereses comunes. Teams se componen de canales. Cada canal se crea en torno a un tema, como "Eventos de equipo", un nombre de departamento o simplemente por diversión. Los canales son donde se realizan reuniones, se mantienen conversaciones y se trabaja conjuntamente en archivos. Durante la colaboración

**OneDrive para la Empresa (uso compartido de archivos P2P) en Teams**: Fuera de Teams y canales, Teams los usuarios pueden compartir archivos de punto a punto con OneDrive para empresas u otros programas de archivos de uso compartido P2P, como Citrix Files, DropBox, Box y Google Drive. Para OneDrive empresariales, un usuario debe tener asignada SharePoint licencia online.

**Plataforma de** aplicaciones: las aplicaciones proporcionan herramientas predefinidas para que su organización saque más partido a Teams. Estas aplicaciones combinan la funcionalidad de pestañas, extensiones de mensajería, conectores y bots proporcionados por Microsoft, creados por un tercero o por desarrolladores de su organización.

**Características de seguridad y cumplimiento:** Teams tiene una amplia variedad de información para ayudarle con áreas de cumplimiento, como directivas de retención, prevención de pérdida de datos (DLP), exhibición de documentos electrónicos y retención legal de canales, chats y archivos, búsqueda de registros de auditoría. Para obtener más información, lea [Seguridad y cumplimiento en Microsoft Teams](security-compliance-overview.md).  

> [!NOTE]
> Las características avanzadas de eDiscovery requieren licencias E5.

[Compare las opciones de licencia](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).

Lea [Cómo Exchange y Microsoft Teams interactuar](exchange-teams-interact.md) para saber qué características de cumplimiento están disponibles en su escenario.

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>Organizaciones **<span class="underline">sin</span>** Skype Empresarial o Lync Server

Este punto de partida asume que su organización no usa Skype Empresarial o Lync Server actualmente y Teams será la primera aplicación en Microsoft 365 o Office 365. En la tabla siguiente se detallan las capacidades de usuario final y configuración de alto nivel para Teams para los servicios principales.

<table>
<thead>
<tr class="header">
<th>Elemento</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configuración de Teams de espacio empresarial</td>
<td>Teams Solo, todas las características de chat y llamada están en solo Teams.</td>
</tr>
<tr class="even">
<td>Chat o comunicación externa en Teams</td>
<td><p>Las comunicaciones internas (intra Microsoft 365 u Office 365 de la organización) y de chat externo pueden obtenerse de Teams.</p>
<p><em>Nota: Las entradas DNS deben configurarse para el acceso externo. Skype Empresarial registros DNS son necesarios aunque no tenga Skype Empresarial local, ni en Microsoft 365 o Office 365, para permitir la federación con entornos de Lync y Skype Empresarial:<br />
<a href="/office365/enterprise/external-domain-name-system-records">Registros del sistema de nombres de dominio externo</a></em></p></td>
</tr>
<tr class="odd">
<td>Crear y ver reuniones en Teams</td>
<td><p>Puede crear reuniones internas y externas a través de Outlook complemento.</p>
<p>La funcionalidad de acceso telefónico local y de acceso telefónico local está disponible con las licencias de Audioconferencia.</p>
<p>Teams el acceso al calendario requiere Exchange 2016 CU3+ local implementado con Exchange implementación híbrida establecida: <a href="/exchange/hybrid-deployment/deploy-hybrid">Crear una implementación híbrida con el Asistente para la configuración híbrida.</a> </p>

Además de Exchange configuración híbrida, establezca Exchange autenticación de OAuth: [Configurar la autenticación de OAuth entre Exchange y Exchange Online organizaciones](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help). 

</p></td>
</tr>
<tr class="even">
<td>Características de llamadas<br />
VoIP/RTC en Teams</td>
<td><p>VoIP interna y externamente al inquilino está disponible.</p>
<p>Los servicios RTC se pueden configurar a través de Teléfono Microsoft Sistema, además de agregar un plan de llamadas de Microsoft o enrutamiento directo.</p></td>
</tr>
<tr class="odd">
<td>colaboración Teams y canales en Teams</td>
<td><p>Para obtener una experiencia completa, incluidas las características de cumplimiento, es necesario asignar al usuario una licencia de SharePoint Online.</p>
<p>No es necesaria la migración de sitios de SharePoint locales existentes.</p></td>
</tr>
<tr class="even">
<td>OneDrive para la Empresa (uso compartido de archivos P2P)</td>
<td>OneDrive para la Empresa requiere que un usuario tenga asignada una licencia de SharePoint Online. Sin esta licencia no será posible compartir archivos de punto a punto.</td>
</tr>
<tr class="odd">
<td>Plataforma de aplicaciones</td>
<td>Los usuarios podrán usar las aplicaciones designadas para ellos según las directivas de su empresa.<br />
Más información aquí: <a href="/microsoftteams/admin-settings">Configuración de administración de aplicaciones en Teams</a></td>
</tr>
<tr class="even">
<td>Características de seguridad y cumplimiento</td>
<td><ul>
<li><p>Las directivas de retención están disponibles.</p></li>
<li><p>EDiscovery y Legal Hold for compliance on channel messages is supported.</p></li>
<li><p>Están disponibles directivas de prevención de pérdida de datos (DLP).</p></li>
</ul>
<p>Conjunto completo de características disponible con Exchange Online; Exchange local admite la mayoría de estas características. Para obtener una lista completa, consulta <a href="/MicrosoftTeams/exchange-teams-interact">Cómo Exchange y Teams interactuar</a>.</p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>Pasos de habilitación para organizaciones sin Skype Empresarial o Lync Server

1.  Cumplir los requisitos previos que se detallan en la sección Comenzar aquí anterior

2.  Cambiar el inquilino al modo Solo Teams (solo para inquilinos existentes): Establecer la [configuración de coexistencia y actualización](setting-your-coexistence-and-upgrade-settings.md).

3.  Configure su inquilino de acuerdo con las directivas empresariales o empresariales de su empresa: [Administrar la configuración de Microsoft Teams para su organización](enable-features-office-365.md).

4.  Implementar el cliente de Teams a los usuarios: [Obtener clientes para Teams](get-clients.md)

5.  Impulsar el programa de adopción  
    [Adoptar Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Lista de comprobación para el inicio rápido de la adopción de Microsoft Teams](teams-adoption-quick-start-checklist.md)

6.  Empezar a planear la migración de otras cargas de trabajo a Microsoft 365 o Office 365

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>Organizaciones **<span class="underline">con</span>** Skype Empresarial o Lync Server

Este punto de partida asume que su organización usa Skype Empresarial 2019 o 2015 o posteriores o el servidor de Lync 2013+ local. Ya disponemos de una amplia orientación para las organizaciones que migran de servidores locales a Teams y se debe seguir para estos escenarios. Esta guía es específica para el escenario que Teams es la primera aplicación que utiliza en Microsoft 365 o Office 365. En la tabla siguiente se detallan las capacidades de usuario final y configuración de alto nivel para Teams para los servicios principales.

<table>
<thead>
<tr class="header">
<th>Elemento</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configuración de Teams de espacio empresarial</td>
<td>Modo islas.</td>
</tr>
<tr class="even">
<td>Chat o comunicación externa en Teams</td>
<td>Solo dentro de su propio espacio empresarial, la comunicación externa (federación) se realiza a través de su Skype Empresarial o implementación de Lync Server.</td>
</tr>
<tr class="odd">
<td>Crear y ver reuniones en Teams</td>
<td><p>Puede crear reuniones internas y externas a través de Outlook complemento.</p>
<p>La funcionalidad de acceso telefónico local y de acceso telefónico local está disponible con las licencias de Audioconferencia.</p>
<p>Teams el acceso al calendario requiere Exchange 2016 CU3+ local implementado con Exchange implementación híbrida:<br />
<a href="/exchange/hybrid-deployment/deploy-hybrid">Cree una implementación híbrida con el Asistente para la configuración híbrida.</a></p>
<p>El administrador puede controlar el complemento Skype Empresarial Outlook a través del atributo PreferredMeetingProviderForIslandsMode de la directiva de reunión de Teams:<a href="/powershell/module/skype/set-csteamsmeetingpolicy"> set-csteamsmeetingpolicy</a>.</p> 
</td>
</tr>
<tr class="even">
<td>Características de llamadas<br />
VoIP/RTC en Teams</td>
<td><p>VoIP internamente para el inquilino está disponible.</p>
<p>Los servicios RTC o plan de llamadas no están disponibles hasta que el usuario se mueve a Teams Solo experiencia.</p></td>
</tr>
<tr class="odd">
<td>colaboración Teams y canales en Teams</td>
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
Más información aquí: <a href="/microsoftteams/admin-settings">Configuración de administración de aplicaciones en Teams</a></td>
</tr>
<tr class="even">
<td>Características de seguridad y cumplimiento</td>
<td><ul>
<li><p>Las directivas de retención están disponibles.</p></li>
<li><p>EDiscovery y Legal Hold for compliance on channel messages is supported.</p></li>
<li><p>Las directivas de prevención de pérdida de datos (DLP) están disponibles.</p></li>
</ul>
<p>Conjunto completo de características disponible con Exchange Online; Exchange local admite la mayoría de estas características. Para obtener una lista completa, consulta <a href="/MicrosoftTeams/exchange-teams-interact">Cómo Exchange y Teams interactuar.</a></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>Pasos de habilitación para organizaciones con Skype Empresarial Server  

1.  Cumpla los requisitos previos detallados en la sección Anterior Iniciar aquí.

2.  Cambiar el inquilino al modo Islas (para los inquilinos aprovisionados DESPUÉS del 1/9/2019, póngase en contacto con el servicio de soporte técnico para realizar este cambio)  
    [Configurar su coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md)

3.  Configurar el inquilino de acuerdo con las directivas empresariales o de empresa de su empresa  
    [Administrar la configuración de Microsoft Teams para su organización](enable-features-office-365.md)

4.  Implementar el cliente de Teams  
    [Obtener clientes para Microsoft Teams](get-clients.md)

5.   Impulsar el programa de adopción  
    [Adoptar Microsoft Teams](adopt-microsoft-teams-landing-page.md)<br/>
    [Lista de comprobación para el inicio rápido de la adopción de Microsoft Teams](teams-adoption-quick-start-checklist.md)

6.  Empezar a planear la migración de otras cargas de trabajo a Microsoft 365 o Office 365

7.  Establecer Skype Empresarial híbrido y seguir las rutas de actualización recomendadas para Skype Empresarial y servidores de Lync  
    [Actualizar de Skype Empresarial local a Teams](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>Declaración de cierre

Microsoft Teams puede ser un facilitador para que su organización reúna a todos los empleados, trabajadores de la información y trabajadores de frontline en una única plataforma. Puedes [empezar](https://products.office.com/microsoft-teams/group-chat-software) hoy mismo. Puedes mantenerte en contacto con todos nuestros últimos anuncios y actualizaciones mensuales de productos [aquí](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).

Además, como las empresas de todo el mundo administran la situación actual de COVID-19, hemos creado una serie de contenidos que le ayudarán a utilizar Teams para lograr el máximo impacto en su organización.

  - Nuestro [compromiso con los clientes durante covid-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)

  - [2 semanas en: lo que hemos aprendido sobre el trabajo remoto](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [Entrega de eventos y reuniones en línea](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [Ayudar a las pequeñas y medianas empresas a trabajar de forma remota con Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [Transformación digital de eventos en directo: las observaciones de Bob Bejan desde el frente](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [Las 9 formas principales en que TI de Microsoft permite trabajar de forma remota a sus empleados](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/).

  - [Trabajar de forma remota y mantenerse protegido: sugerencias para LOS CISOs](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [Ayudar a profesores y alumnos a cambiar al aprendizaje remoto](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [Mantener la productividad mientras se trabaja de forma remota con Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>Referencia de servicios de soporte técnico

Teams se basa en Exchange Online, SharePoint Online, OneDrive para la Empresa y Grupos de Microsoft 365 para proporcionar a los usuarios una Microsoft 365 o Office 365 totalmente integrada.  Experiencia. Como se mencionó anteriormente, Teams funcionará sin implementar completamente estos servicios, con capacidades limitadas. Puede obtener más información sobre Teams y sus requisitos previos aquí: [Bienvenido a Teams](teams-overview.md).

Para obtener información específica sobre cada uno de los servicios enumerados anteriormente, sigue los siguientes vínculos:

  - Exchange Online se usa para las características de calendario y para almacenar mensajes de punto a punto en Teams. Para obtener más información, lee [Cómo Exchange e Teams interactuar](exchange-teams-interact.md)

> [!IMPORTANT]
> Para Teams interoperabilidad con Exchange local, debe configurar el nuevo protocolo de autenticación de OAuth Exchange como se describe en [Configurar autenticación de OAuth entre organizaciones Exchange y Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).

  - SharePoint se usa para compartir archivos en canales, mientras que /OneDrive para la Empresa se usa para compartir archivos en 1:1 o chat grupal. Para obtener más información, consulta [Cómo SharePoint en línea y OneDrive para la Empresa interactuar con Microsoft Teams](sharepoint-onedrive-interact.md).

  - [Grupos de Microsoft 365](office-365-groups.md) se usan para la creación y administración de equipos y canales.


## <a name="related-topics"></a>Temas relacionados

[Carteles de soluciones de telefonía y arquitectura de TI de Microsoft Teams](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[Planear la conectividad híbrida entre Skype Empresarial Server y Office 365](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[Soporte técnico a los trabajadores remotos con Teams](support-remote-work-with-teams.md)

[Trabajar de forma remota con Microsoft 365](https://aka.ms/remote-work)
