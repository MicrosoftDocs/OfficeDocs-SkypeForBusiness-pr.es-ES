---
title: Implementar Microsoft Teams en primer lugar
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
description: Use esta guía para implementar Microsoft Teams como la primera carga de trabajo de Office 365.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 79607004c8f750ceed0325733c8c52a4873e9cdc
ms.sourcegitcommit: 89a7c0427a5abbef838a17ae7eac6934c6176a35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "42982164"
---
# <a name="roll-out-microsoft-teams-first"></a>Implementar Microsoft Teams en primer lugar

Microsoft Teams puede ayudar a sus empleados a permanecer en contacto y colaborar entre ellos, especialmente en el momento actual, en el que el trabajo remoto es una realidad de los empleados de todo el mundo. Poder chatear, hacer reuniones de video y colaborar en documentos de Office dentro de Teams puede ayudar a que las empresas sigan siendo productivas. Si es una pequeña empresa, una organización sin ánimo de lucro o de gran tamaño, puede empezar a trabajar con Teams como la primera carga de trabajo de Office 365 Suite antes de implementar cualquier otra aplicación o servicio de Office.

Este artículo detalla las consideraciones que debe tomar con el método "Team First".

> [!IMPORTANT]
> Aunque los equipos pueden ser la primera carga de trabajo implementada en la nube de su organización, la implementación de equipos debe formar parte de la estrategia general de implementación en la nube.

Si ya ha implementado otros servicios de Office 365 y Teams es la siguiente carga de trabajo que debe implementar (en lugar de la primera), empiece con [cómo implementar Teams](How-to-roll-out-teams.md).

## <a name="start-here"></a>Empiece aquí

Para empezar a usar su primer despliegue de Teams, deberá cumplir con un mínimo de requisitos previos. En la siguiente lista se mostrará lo que debe tener en el lugar de su organización antes de que se puedan habilitar los equipos:

1.  Un inquilino de Office 365 configurado con el nombre de dominio

2.  Conectividad de Azure Active Directory (AAD Connect) o solución de sincronización de identidad de nube similar, con todos los atributos obligatorios sincronizados con su espacio empresarial  
    Para comprender los atributos sincronizados con AAD Sync, lea [sincronización de Azure ad Connect: atributos sincronizados en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

3.  Licencias de usuario adecuadas asignadas a teams  
    Para comprender las licencias de Teams, lea [licencias de Office 365 para Microsoft Teams](office-365-licensing.md)

4.  Red de la organización preparada para Teams  
    Para comprender la preparación de la red, lea [preparar la red de su organización para Teams](prepare-network.md).

5.  Permitir el acceso de red a Exchange, SharePoint y OneDrive para la empresa en Office 365: [direcciones URL e intervalos de direcciones IP de office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).

> [!NOTE]
> Los inquilinos creados después del 1 de septiembre de 2019 se aprovisionan en el modo solo de Teams.
> 
> [!IMPORTANT]
> Si ha implementado Skype empresarial Server y se aprovisionó su inquilino después del 1 de septiembre de 2019, póngase en contacto con el soporte técnico de Premier para habilitar las capacidades de coexistencia para Teams. Asegúrese de que la "Directiva de actualización de toda la organización" está establecida en "modo islas" <span class="underline">antes</span> de asignar licencias de Teams a un usuario.

## <a name="migration-starting-points"></a>Puntos de partida de migración

Su viaje a Office 365 y las características disponibles en Teams según su punto de partida y la existencia de Skype empresarial local o Lync Server. En las siguientes secciones, se detallan las características básicas y las opciones de configuración, además de los requisitos previos anteriores. Hemos desglosado los escenarios de punto de partida en los siguientes temas:

**Configuración de equipos de inquilino**: los modos de inquilino y usuario se usan para controlar el comportamiento del destinatario. Esta configuración se puede asignar en el nivel de espacio empresarial o en el nivel de usuario de una organización. Para obtener más información, lea [coexistencia con Skype empresarial](coexistence-chat-calls-presence.md).

**Chat/comunicación externa en Teams**: los servicios de chat se refieren a las conversaciones entre usuarios del mismo nivel o chats grupales dentro y organización o externamente a la organización. La comunicación externa también se conoce como Federación en Skype empresarial.

**Crear y ver reuniones en Teams**: un usuario siempre puede crear reuniones en línea a través del complemento equipos de Outlook y el acceso telefónico PSTN está disponible en todos los escenarios una vez que el usuario tiene licencia. Teams y Skype empresarial almacenan información de calendario en el buzón de Exchange del usuario. El servidor de Exchange local debe ser Exchange Server 2016 CU3 o una versión posterior para que el cliente de Teams pueda interactuar con el buzón del usuario. Sin acceso al buzón de Exchange el icono de calendario de Teams no aparecerá y su usuario no podrá ver, crear ni modificar reuniones en el cliente de Teams.

**Llamadas a características VoIP/PSTN en Teams: las**llamadas pueden ser de voz a través de IP (VoIP) o de redes de telefonía pública conmutada (RTC). La conectividad de VoIP se produce de forma nativa entre los clientes de Teams, mientras que la conectividad RTC se produce cuando un usuario marca un número de teléfono externo.  

Teams admite dos tipos de conectividad RTC. Plan de llamadas de Microsoft, cuando Microsoft proporciona una infraestructura de telefonía, como el número de teléfono de un usuario o la configuración de enrutamiento directo, donde el cliente proporciona la conectividad de telefonía a través de un controlador de borde de sesión (SBC) para el usuario de Teams.  
Para obtener más información, lea [¿qué plan de llamadas es adecuado para usted?](calling-plan-landing-page.md) y [enrutamiento directo del sistema telefónico](direct-routing-landing-page.md).

**Colaboración entre equipos y canales en Teams**: en Teams, Teams reúne grupos de personas para el trabajo, los proyectos o los intereses comunes. Los equipos se componen de canales. Cada canal se crea en función de un tema, como "eventos de equipo", un nombre de departamento o simplemente por diversión. Los canales son donde se guardan las reuniones, se tienen conversaciones y se trabaja con los archivos juntos. Durante la colaboración

**OneDrive para la empresa (uso compartido de archivos P2P) en Teams**: fuera de los equipos y los canales, los usuarios de equipos pueden compartir archivos de punto a punto mediante OneDrive para la empresa u otros programas de archivos con uso compartido de P2P, como Citrix files, Dropbox, Box y Google Drive. En el caso de OneDrive para la empresa, un usuario debe tener asignada una licencia de SharePoint Online.

**Plataforma de aplicaciones**: las aplicaciones proporcionan herramientas para su organización para obtener más provecho de Teams. Estas aplicaciones combinan la funcionalidad de las pestañas, las extensiones de mensajería, los conectores y los bots proporcionados por Microsoft, creados por un tercero o por los programadores de su organización.

**Características de seguridad y cumplimiento:** Teams tiene una amplia variedad de información para ayudarle en áreas de cumplimiento, como directivas de retención, protección de pérdida de datos (DLP), eDiscovery y retención legal para canales, chats y archivos, búsqueda de registros de auditoría. Para obtener más información, lea [seguridad y cumplimiento en Microsoft Teams](security-compliance-overview.md).  

> [!NOTE]
> Las características de eDiscovery avanzado requieren licencias de E5.

[Compare las opciones de licencia](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).

Lea [cómo interactúan Exchange y Microsoft Teams](exchange-teams-interact.md) para saber qué características de cumplimiento están disponibles en su escenario.

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>Organizaciones **<span class="underline">sin</span>** Skype empresarial o Lync Server

Este punto de partida supone que su organización no utiliza actualmente Skype empresarial o Lync Server, y que Teams será su primera aplicación en Office 365. En la siguiente tabla, se detallan las capacidades de configuración y de usuario final de los equipos de los servicios básicos.

<table>
<thead>
<tr class="header">
<th>Elemento</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configuración de equipos de inquilino</td>
<td>Modo solo para equipos; todas las características de chat y de llamada están en Teams solamente</td>
</tr>
<tr class="even">
<td>Chat/comunicación externa en Teams</td>
<td><p>Interno (espacio empresarial intra365 dentro de la oficina) y comunicación de conversaciones externas posible desde Teams</p>
<p><em>Nota: las entradas DNS deben configurarse para acceso externo. Los registros DNS de Skype empresarial son necesarios incluso si no tiene Skype empresarial local o en Office 365 para permitir la Federación con entornos de Lync y Skype empresarial.<br />
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">Registros del sistema de nombres de dominio externo para Office 365</a></em></p></td>
</tr>
<tr class="odd">
<td><em>Crear y ver reuniones en Teams</em></td>
<td><p><em>Posibilidad de crear reuniones mediante el complemento de Outlook</em></p>
<p><em>La función de marcado y salida de llamadas RTC está disponible con las licencias de audioconferencia.<br />
Nota: Team Calendar Access requiere Exchange 2016 CU3 + local implementado con Exchange híbrido establecido: <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">crear una implementación híbrida con el Asistente para la configuración híbrida</a><br />
Además de la configuración híbrida de Exchange, establezca la autenticación de OAuth de Exchange: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">configurar la autenticación de OAuth entre Exchange y las organizaciones de Exchange Online</a></em></p></td>
</tr>
<tr class="even">
<td>Llamadas a características<br />
VoIP/PSTN en Teams</td>
<td><p>VoIP de forma interna y externa al inquilino está disponible</p>
<p>Los servicios RTC se pueden configurar a través de Microsoft Phone System, además de agregar un plan de llamadas de Microsoft o enrutamiento directo.</p></td>
</tr>
<tr class="odd">
<td>Colaboración de equipos y canales en Teams</td>
<td><p>Para obtener una experiencia completa, incluidas las características de cumplimiento, es necesario asignar una licencia de SharePoint Online al usuario.</p>
<p>No es necesario migrar los sitios de SharePoint locales existentes.</p></td>
</tr>
<tr class="even">
<td>OneDrive para la empresa (uso compartido de archivos P2P)</td>
<td>OneDrive para la empresa requiere que un usuario tenga asignada una licencia de SharePoint Online. Sin esta licencia, no será posible compartir archivos de punto a punto.</td>
</tr>
<tr class="odd">
<td>Plataforma de aplicaciones</td>
<td>Los usuarios podrán usar las aplicaciones que estén disponibles según las directivas de la empresa.<br />
Más información aquí: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">configuración de administración de aplicaciones en Teams</a></td>
</tr>
<tr class="even">
<td>Características de seguridad y cumplimiento</td>
<td><ul>
<li><p>Las directivas de retención están disponibles</p></li>
<li><p>eDiscovery y retención legal para el cumplimiento de los mensajes de canal es compatible</p></li>
<li><p>Están disponibles las directivas de prevención de pérdida de datos (DLP)</p></li>
</ul>
<p>Conjunto completo de características disponibles con Exchange Online, Exchange local admite la mayoría de estas características, vea</p>
<p><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Interacción entre Exchange y Microsoft Teams</a></p>
<p>para obtener una lista completa</p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>Pasos de habilitación para organizaciones sin Skype empresarial o Lync Server

1.  Conozca los requisitos previos que se detallan en la sección iniciar aquí anterior

2.  Cambiar el inquilino al modo solo para equipos (solo para los inquilinos existentes): [configurar la coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md).

3.  Configure su espacio empresarial de acuerdo con las directivas empresariales/de empresa de su empresa: [administrar la configuración de Microsoft Teams para su organización](enable-features-office-365.md).

4.  Implementar el cliente de Teams para sus usuarios: [obtener clientes para equipos](get-clients.md)

5.  Impulsar el programa de adopción  
    [Adoptar Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Lista de comprobación para el inicio rápido de la adopción de Microsoft Teams](teams-adoption-quick-start-checklist.md)

6.  Empezar a planear el movimiento de otras cargas de trabajo a Office 365

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>Organizaciones **<span class="underline">con</span>** Skype empresarial o Lync Server

Este punto de partida supone que su organización utiliza los servidores de Skype empresarial 2019, 2015 + o Lync 2013 + Server. Ya contamos con amplias instrucciones para las organizaciones que migran de servidores locales a equipos y que deben seguirse en estos escenarios. Esta guía es específica del escenario en el que Teams es la primera aplicación que se usa en Office 365. En la siguiente tabla, se detallan las capacidades de configuración y de usuario final de los equipos de los servicios básicos.

<table>
<thead>
<tr class="header">
<th>Elemento</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configuración de equipos de inquilino</td>
<td>Modo islas</td>
</tr>
<tr class="even">
<td>Chat/comunicación externa en Teams</td>
<td>Interno dentro de su propio espacio empresarial, la comunicación externa (Federación) se realiza a través de la implementación de Skype empresarial o de Lync Server.</td>
</tr>
<tr class="odd">
<td>Crear y ver reuniones en Teams</td>
<td><p>Posibilidad de crear reuniones mediante el complemento de Outlook</p>
<p>La función de marcado y salida de llamadas RTC está disponible con las licencias de audioconferencia.<br />
Teams Access Calendar requiere Exchange 2016 CU3 + local implementado con Exchange híbrido establecido:<br />
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Crear una implementación híbrida con el Asistente para la configuración híbrida</a></p></td>
</tr>
<tr class="even">
<td>Llamadas a características<br />
VoIP/PSTN en Teams</td>
<td><p>VoIP interno del inquilino está disponible</p>
<p>Los servicios de plan de llamadas o RTC no están disponibles hasta que el usuario solo se mueve a la experiencia de Teams</p></td>
</tr>
<tr class="odd">
<td>Colaboración de equipos y canales en Teams</td>
<td><p>Para obtener una experiencia completa, incluidas las características de cumplimiento, es necesario asignar una licencia de SharePoint Online al usuario.</p>
<p>No es necesario migrar los sitios de SharePoint locales existentes.</p></td>
</tr>
<tr class="even">
<td>OneDrive para la empresa (uso compartido de archivos P2P)</td>
<td>OneDrive para la empresa requiere que un usuario tenga asignada una licencia de SharePoint Online. Sin este uso compartido de archivos de licencia por par no será posible.</td>
</tr>
<tr class="odd">
<td>Plataforma de aplicaciones</td>
<td>Los usuarios podrán usar las aplicaciones que estén disponibles según las directivas de la empresa.<br />
Más información aquí: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">configuración de administración de aplicaciones en Teams</a></td>
</tr>
<tr class="even">
<td>Características de seguridad y cumplimiento</td>
<td><ul>
<li><p>Las directivas de retención están disponibles</p></li>
<li><p>eDiscovery y retención legal para el cumplimiento de los mensajes de canal es compatible</p></li>
<li><p>Están disponibles las directivas de prevención de pérdida de datos (DLP)</p></li>
</ul>
<p>Conjunto completo de características disponibles con Exchange Online, Exchange local admite la mayoría de estas características, vea</p>
<p><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Interacción entre Exchange y Microsoft Teams</a></p>
<ul>
<li><p>para obtener una lista completa</p></li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>Pasos de habilitación para las organizaciones con Skype empresarial Server  

1.  Reúna los requisitos previos que se detallan en la sección empezar aquí anterior.

2.  Cambiar el inquilino al modo islas (para los inquilinos aprovisionados después 9/1/2019, póngase en contacto con el soporte técnico Premier para hacer este cambio).  
    [Configurar su coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md)

3.  Configurar el espacio empresarial de acuerdo con las directivas empresariales y de empresa de su empresa  
    [Administrar la configuración de Microsoft Teams para su organización](enable-features-office-365.md)

4.  Implementar el cliente de Teams  
    [Obtener clientes para Microsoft Teams](get-clients.md)

5.   Impulsar el programa de adopción  
    [Adoptar Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Lista de comprobación para el inicio rápido de la adopción de Microsoft Teams](teams-adoption-quick-start-checklist.md)

6.  Empezar a planear el movimiento de otras cargas de trabajo a Office 365

7.  Establecer una implementación híbrida de Skype empresarial y seguir las rutas de actualización recomendadas para servidores de Skype empresarial y Lync  
    [Actualizar de Skype empresarial local a teams](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>Resumen de cierre

Microsoft Teams puede ser un habilitador para que su organización reúna a todos los empleados, trabajadores de la información y trabajadores de los Firstline, juntos en una sola plataforma. Puedes [comenzar](https://products.office.com/microsoft-teams/group-chat-software) hoy mismo. Puedes mantenerte en contacto con los últimos anuncios [y actualizaciones de](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)productos mensuales.

Además, como empresas de todo el mundo están administrando la situación actual de COVID-19, hemos creado una serie de contenidos que le ayudarán a usar Teams para obtener el máximo impacto de su organización.

  - Nuestro [compromiso con los clientes durante COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)

  - [2 semanas en: lo que hemos aprendido sobre el trabajo remoto](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [Entrega de reuniones y eventos en línea](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [Ayudar a las pequeñas y medianas empresas a trabajar de forma remota con Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [Transformación digital de eventos en vivo: las observaciones de Bob bejan de la Frontline](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [Las nueve maneras principales en las que Microsoft IT Habilita el trabajo remoto para sus empleados](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [Trabajar de forma remota, mantener la seguridad: consejos para CISOs](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [Ayudar a los profesores y a los estudiantes a cambiar de aprendizaje remoto](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [Mantener la productividad mientras trabaja de forma remota con Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>Referencia de servicios de soporte técnico

Teams depende de los grupos de Exchange Online, SharePoint Online, OneDrive para la empresa y Office 365 para ofrecer a los usuarios una experiencia de Office 365 totalmente integrada. Como se indicó anteriormente, Teams trabajará sin la total implementación de estos servicios, con capacidades limitadas. Puede obtener más información sobre Teams y sus requisitos previos aquí: [Bienvenido a teams](teams-overview.md).

Para obtener información específica sobre cada uno de los servicios mencionados anteriormente, sigue los siguientes vínculos:

  - Exchange Online se usa para características de calendario y para almacenar mensajes de par a par en Teams. Para obtener más información, lea [cómo interactúan Exchange y Teams](exchange-teams-interact.md)

> [!IMPORTANT]
> Para la interoperabilidad de Teams con Exchange local, debe configurar el nuevo protocolo de autenticación OAuth de Exchange según se describe en [configurar la autenticación OAuth entre Exchange y las organizaciones de Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).

  - SharePoint se usa para el uso compartido de archivos en canales, mientras que/OneDrive para empresas se usa para compartir archivos en 1:1 o chat grupal. Para obtener más información, lea [Cómo SharePoint Online y OneDrive para la empresa interactúan con Microsoft Teams](sharepoint-onedrive-interact.md).

  - Los [grupos de Office 365](office-365-groups.md) se usan para la creación y la administración de equipos y canales.


## <a name="related-topics"></a>Temas relacionados

[Carteles de soluciones de telefonía y arquitectura de TI de Microsoft Teams](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[Planear la conectividad híbrida entre Skype Empresarial Server y Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[Soporte técnico de trabajadores remotos con Teams](support-remote-work-with-teams.md)

[ Trabajar a distancia con Office 365 ](https://aka.ms/remote-work)