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
# <a name="roll-out-microsoft-teams-first"></a><span data-ttu-id="18890-103">Implementación de Microsoft Teams primero</span><span class="sxs-lookup"><span data-stu-id="18890-103">Roll out Microsoft Teams First</span></span>

<span data-ttu-id="18890-104">Microsoft Teams puede ayudar a sus empleados a mantenerse conectados y colaborar entre ellos, especialmente en el momento de las vistas en las que el trabajo remoto es una realidad de los empleados de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="18890-104">Microsoft Teams can help your employees stay connected and collaborate with each other, especially in the current unprecedented time where remote work is a reality of employees around the world.</span></span> <span data-ttu-id="18890-105">Poder chatear, realizar reuniones de vídeo y colaborar en documentos de Office en Teams puede ayudar a las empresas a seguir siendo productivas.</span><span class="sxs-lookup"><span data-stu-id="18890-105">Being able to chat, do video meetings and collaborate on Office documents within Teams can help companies stay productive.</span></span> <span data-ttu-id="18890-106">Tanto si es una pequeña empresa, una organización sin ánimo de lucro o una organización grande, puede empezar con Teams como la primera carga de trabajo en el conjunto de aplicaciones de Microsoft 365 u Office 365 antes de implementar cualquier otra aplicación o servicio de Office.</span><span class="sxs-lookup"><span data-stu-id="18890-106">Whether you are a small business, a non-profit or a large organization, you can get started with Teams as the first workload within Microsoft 365 or Office 365 suite before deploying any other Office app or service.</span></span>

<span data-ttu-id="18890-107">En este artículo se detallan las consideraciones que debe tomar con el enfoque de "Teams primero".</span><span class="sxs-lookup"><span data-stu-id="18890-107">This article details the considerations you must make with the "Teams First" approach.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="18890-108">Aunque Teams puede ser la primera carga de trabajo implementada en la nube de su organización, la implementación de Teams debe formar parte de la estrategia general de implementación en la nube.</span><span class="sxs-lookup"><span data-stu-id="18890-108">While Teams can be your organization's first cloud deployed workload, deploying Teams should be part of your overall cloud deployment strategy.</span></span>

<span data-ttu-id="18890-109">Si ya ha lanzado otros servicios de Microsoft 365 u Office 365 y Teams es su próxima carga de trabajo para su implementación (en lugar de la primera), comience con Cómo lanzamiento [teams.](How-to-roll-out-teams.md)</span><span class="sxs-lookup"><span data-stu-id="18890-109">If you have already rolled out other Microsoft 365 or Office 365 services and Teams is your next workload to roll out (instead of the first), start with [How to roll out Teams](How-to-roll-out-teams.md).</span></span>

## <a name="start-here"></a><span data-ttu-id="18890-110">Empiece aquí</span><span class="sxs-lookup"><span data-stu-id="18890-110">Start here</span></span>

<span data-ttu-id="18890-111">Para empezar con la implementación de Teams First deberá cumplir como mínimo algunos requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="18890-111">To get started with your Teams First deployment you will need to meet at minimum some pre-requisites.</span></span> <span data-ttu-id="18890-112">La siguiente lista mostrará lo que debe tener para su organización antes de que se pueda habilitar Teams:</span><span class="sxs-lookup"><span data-stu-id="18890-112">The following list will show what you must have in place for your organization before Teams can be enabled:</span></span>

1.  <span data-ttu-id="18890-113">Una organización de Microsoft 365 u Office 365 configurada con su nombre de dominio</span><span class="sxs-lookup"><span data-stu-id="18890-113">A Microsoft 365 or Office 365 organization configured with your domain name</span></span>

2.  <span data-ttu-id="18890-114">Conectividad de Azure Active Directory (conexión AAD) o una solución de sincronización de identidades en la nube similar, con todos los atributos necesarios sincronizados con tu inquilino</span><span class="sxs-lookup"><span data-stu-id="18890-114">Azure Active Directory connectivity (AAD connect) or similar cloud identity sync solution – with all required attributes synched with your tenant</span></span>  
    <span data-ttu-id="18890-115">Para comprender los atributos sincronizados con la sincronización de AAD, lea Sincronización de Azure AD Connect: Atributos [sincronizados con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span><span class="sxs-lookup"><span data-stu-id="18890-115">To understand the attributes synchronized with AAD sync, read [Azure AD Connect sync: Attributes synchronized to Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span></span>

3.  <span data-ttu-id="18890-116">Licencias de usuario adecuadas asignadas para Teams</span><span class="sxs-lookup"><span data-stu-id="18890-116">Appropriate user licenses assigned for Teams</span></span>  
    <span data-ttu-id="18890-117">Para comprender las licencias de Teams, lea la [descripción del servicio Microsoft Teams.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="18890-117">To understand Teams licensing, read [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

4.  <span data-ttu-id="18890-118">Red de la organización preparada para Teams</span><span class="sxs-lookup"><span data-stu-id="18890-118">Organization's network prepared for Teams</span></span>  
    <span data-ttu-id="18890-119">Para comprender la preparación de la red, [lea Preparar la red de su organización para Teams.](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="18890-119">To understand network preparation, read [Prepare your organization's network for Teams](prepare-network.md).</span></span>

5.  <span data-ttu-id="18890-120">Permitir el acceso de red a Exchange, SharePoint y OneDrive para la Empresa en Microsoft 365 u Office 365: direcciones URL e intervalos de direcciones IP de [Office 365.](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)</span><span class="sxs-lookup"><span data-stu-id="18890-120">Allow network access to Exchange, Sharepoint, and OneDrive for Business in Microsoft 365 or Office 365: [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="18890-121">Los inquilinos creados después del 1 de septiembre de 2019 se aprovisionan solo en modo Teams.</span><span class="sxs-lookup"><span data-stu-id="18890-121">Tenants created after September 1, 2019 are provisioned in Teams Only mode.</span></span>
> 
> [!IMPORTANT]
> <span data-ttu-id="18890-122">Si tiene implementado Skype Empresarial Server y su espacio empresarial se aprovisionó después del 1 de septiembre de 2019, póngase en contacto con el soporte técnico para habilitar las capacidades de coexistencia de Teams.</span><span class="sxs-lookup"><span data-stu-id="18890-122">If you have Skype for Business Server deployed, and your tenant was provisioned AFTER September 1, 2019, please contact support to enable coexistence capabilities for Teams.</span></span> <span data-ttu-id="18890-123">Asegúrese de que la "directiva de actualización para toda la organización" esté establecida en "Modo <span class="underline">isla"</span> antes de asignar licencias de Teams a un usuario.</span><span class="sxs-lookup"><span data-stu-id="18890-123">Make sure your 'Organization wide upgrade policy' is set to 'Island mode' <span class="underline">before</span> you assign any Teams licenses to a user.</span></span>

## <a name="migration-starting-points"></a><span data-ttu-id="18890-124">Puntos iniciales de la migración</span><span class="sxs-lookup"><span data-stu-id="18890-124">Migration Starting points</span></span>

<span data-ttu-id="18890-125">Su viaje a Microsoft 365 u Office 365 y las características disponibles en Teams en función de su punto de partida y la existencia de Skype Empresarial local o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="18890-125">Your journey to Microsoft 365 or Office 365 and features available in Teams depending on your starting point and the existence of on premises Skype for Business or Lync server.</span></span> <span data-ttu-id="18890-126">En las siguientes secciones se detallan las capacidades básicas y las opciones de configuración, además de los requisitos previos anteriores.</span><span class="sxs-lookup"><span data-stu-id="18890-126">The following sections will detail basic capabilities and configuration options in addition to the pre-requisites above.</span></span> <span data-ttu-id="18890-127">Hemos desglosado los escenarios de los puntos de partida en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="18890-127">We have broken down the starting point scenarios to the following topics:</span></span>

<span data-ttu-id="18890-128">**Configuración de equipos de** espacio empresarial: los modos de inquilino y usuario se usan para controlar el comportamiento del destinatario.</span><span class="sxs-lookup"><span data-stu-id="18890-128">**Tenant Teams Configuration**: Tenant and user modes are used to control the recipient's behavior.</span></span> <span data-ttu-id="18890-129">Esta configuración se puede asignar en el nivel de inquilino o en el nivel de usuario de una organización.</span><span class="sxs-lookup"><span data-stu-id="18890-129">These settings can be assigned on the tenant level or the user level in an organization.</span></span> <span data-ttu-id="18890-130">Para obtener más información, lea [Coexistencia con Skype Empresarial.](coexistence-chat-calls-presence.md)</span><span class="sxs-lookup"><span data-stu-id="18890-130">To learn more, read [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>

<span data-ttu-id="18890-131">**Chat/Comunicación externa en Teams:** los servicios de chat hacen referencia a conversaciones de chat de punto a punto o grupales dentro y dentro de la organización o externamente a la organización.</span><span class="sxs-lookup"><span data-stu-id="18890-131">**Chat / External communication in Teams**: Chat services refer to peer to peer or group chat conversations within and organization or externally to the organization.</span></span> <span data-ttu-id="18890-132">Las comunicaciones externas también se conocen como federación en Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="18890-132">External communication is also referred to as federation in Skype for Business.</span></span>

<span data-ttu-id="18890-133">Crear y ver reuniones en **Teams:** un usuario siempre puede crear reuniones en línea mediante el complemento de Outlook Teams y el acceso telefónico RTC está disponible en todos los escenarios una vez que el usuario tiene licencia.</span><span class="sxs-lookup"><span data-stu-id="18890-133">**Create and view meetings in Teams**: A user can always create online meetings via the Outlook Teams add-in and PSTN dial-in is available in all scenarios once the user is licensed.</span></span> <span data-ttu-id="18890-134">Teams y Skype Empresarial almacenan información de calendario en el buzón de Exchange del usuario.</span><span class="sxs-lookup"><span data-stu-id="18890-134">Teams and Skype for Business store calendaring information in the user's Exchange mailbox.</span></span> <span data-ttu-id="18890-135">El servidor exchange local debe estar Exchange Server 2016 CU3 o posterior para que el cliente de Teams pueda interactuar con el buzón del usuario.</span><span class="sxs-lookup"><span data-stu-id="18890-135">On premises Exchange server must be Exchange Server 2016 CU3 or above for the Teams client to be able to interact with the user's mailbox.</span></span> <span data-ttu-id="18890-136">Sin el acceso al buzón de Exchange no se mostrará el icono de Calendario en Teams y el usuario no podrá ver, crear o modificar reuniones en el cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="18890-136">Without Exchange mailbox access the Calendar icon in Teams will not appear and they user will not be able to view, create or modify meetings in the Teams client.</span></span>

<span data-ttu-id="18890-137">**Características de llamadas VoIP/RTC** en Teams: las llamadas pueden ser de voz a través de IP (VoIP) o de red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="18890-137">**Calling features VoIP / PSTN in Teams**: Calling can be Voice over IP (VoIP) or Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="18890-138">La conectividad VoIP se produce de forma nativa entre clientes de Teams, mientras que la conectividad con RTC se produce cuando un usuario marca un número de teléfono externo.</span><span class="sxs-lookup"><span data-stu-id="18890-138">VoIP connectivity happens natively between Teams clients, while PSTN connectivity happen when a user dials an outside phone number.</span></span>  

<span data-ttu-id="18890-139">Teams admite dos tipos de conectividad con RTC.</span><span class="sxs-lookup"><span data-stu-id="18890-139">Teams support two types of PSTN connectivity.</span></span> <span data-ttu-id="18890-140">Plan de llamadas de Microsoft, cuando Microsoft proporciona infraestructura de telefonía, incluido el número de teléfono de un usuario, o la configuración de enrutamiento directo, donde el cliente proporciona la conectividad de telefonía a través de un controlador de borde de sesión (SBC) para el usuario de Teams.</span><span class="sxs-lookup"><span data-stu-id="18890-140">Microsoft Calling Plan, when Microsoft provides telephony infrastructure including the phone number for a user, or Direct Routing configuration, where the customer provides the telephony connectivity over a Session Border Controller (SBC) for the Teams user.</span></span>  
<span data-ttu-id="18890-141">Para obtener más información, [lea ¿Qué plan de llamadas es adecuado para usted?](calling-plan-landing-page.md) y enrutamiento [directo del sistema telefónico.](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="18890-141">To learn more, read [Which Calling Plan is right for you?](calling-plan-landing-page.md) and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="18890-142">**Colaboración de equipos y canales** en Teams: En Teams, los equipos son grupos de personas que se reúnen por causas de trabajo, proyectos o intereses comunes.</span><span class="sxs-lookup"><span data-stu-id="18890-142">**Teams and Channels collaboration in Teams**: In Teams, teams are groups of people brought together for work, projects, or common interests.</span></span> <span data-ttu-id="18890-143">Los equipos están configurados por canales.</span><span class="sxs-lookup"><span data-stu-id="18890-143">Teams are made up of channels.</span></span> <span data-ttu-id="18890-144">Cada canal se basa en un tema, como "Eventos de equipo", un nombre de departamento o solo por diversión.</span><span class="sxs-lookup"><span data-stu-id="18890-144">Each channel is built around a topic, like "Team Events," a department name, or just for fun.</span></span> <span data-ttu-id="18890-145">Los canales son los lugares donde se mantienen reuniones, se mantienen conversaciones y se trabaja conjuntamente en archivos.</span><span class="sxs-lookup"><span data-stu-id="18890-145">Channels are where you hold meetings, have conversations, and work on files together.</span></span> <span data-ttu-id="18890-146">Durante la colaboración</span><span class="sxs-lookup"><span data-stu-id="18890-146">During collaboration</span></span>

<span data-ttu-id="18890-147">OneDrive para la Empresa (uso compartido de archivos **P2P)** en Teams: fuera de equipos y canales, los usuarios de Teams pueden compartir archivos de punto a punto con OneDrive para la Empresa u otros programas de archivos compartidos P2P como Archivos Citrix, Dropbox, Box y Google Drive.</span><span class="sxs-lookup"><span data-stu-id="18890-147">**OneDrive for Business (P2P file sharing) in Teams**: Outside of Teams and Channels, Teams users can share files peer-to-peer using OneDrive for business or other P2P sharing file programs such as Citrix Files, DropBox, Box and Google Drive.</span></span> <span data-ttu-id="18890-148">Para OneDrive para la Empresa, un usuario debe tener asignada una licencia de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="18890-148">For OneDrive for business a user must have SharePoint Online license assigned.</span></span>

<span data-ttu-id="18890-149">**Plataforma de** aplicaciones: las aplicaciones proporcionan herramientas integradas para que su organización obtenga más información sobre Teams.</span><span class="sxs-lookup"><span data-stu-id="18890-149">**Application Platform**: Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="18890-150">Estas aplicaciones combinan la funcionalidad de fichas, extensiones de mensajería, conectores y bots proporcionados por Microsoft, creados por un tercero o por desarrolladores de su organización.</span><span class="sxs-lookup"><span data-stu-id="18890-150">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="18890-151">**Características de seguridad y cumplimiento:** Teams tiene una amplia variedad de información para ayudarle con las áreas de cumplimiento, incluidas las directivas de retención, protección de pérdida de datos (DLP), exhibición de documentos electrónicos y retención legal para canales, chats y archivos, y búsqueda de registros de auditoría.</span><span class="sxs-lookup"><span data-stu-id="18890-151">**Security and Compliance features:** Teams has a wide range of information to help you with compliance areas, including retention policies, Data Loss Protection (DLP), eDiscovery and legal hold for channels, chats and files, audit log search.</span></span> <span data-ttu-id="18890-152">Para obtener más información, lea [Seguridad y cumplimiento en Microsoft Teams.](security-compliance-overview.md)</span><span class="sxs-lookup"><span data-stu-id="18890-152">To learn more, read [Security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="18890-153">Las características de eDiscovery anticipada requieren licencias E5.</span><span class="sxs-lookup"><span data-stu-id="18890-153">Advance eDiscovery features require E5 licensing.</span></span>

<span data-ttu-id="18890-154">[Comparar las opciones de licencia.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)</span><span class="sxs-lookup"><span data-stu-id="18890-154">[Compare licensing options](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>

<span data-ttu-id="18890-155">Lea [cómo interactúan Exchange y Microsoft Teams](exchange-teams-interact.md) para saber qué características de cumplimiento están disponibles en su escenario.</span><span class="sxs-lookup"><span data-stu-id="18890-155">Read [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) to learn which compliance features are available in your scenario.</span></span>

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a><span data-ttu-id="18890-156">Organizaciones **<span class="underline">sin</span>** Skype Empresarial o Lync Server</span><span class="sxs-lookup"><span data-stu-id="18890-156">Organizations **<span class="underline">without</span>** Skype for Business or Lync Server</span></span>

<span data-ttu-id="18890-157">Este punto de partida supone que su organización no utiliza Skype Empresarial o Lync Server actualmente y que Teams será su primera aplicación en Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="18890-157">This starting point assumes that your organization does not utilize Skype for Business or Lync Server currently and Teams will be your first application in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="18890-158">En la tabla siguiente se detalla la configuración de alto nivel y las capacidades del usuario final de Teams para los servicios principales.</span><span class="sxs-lookup"><span data-stu-id="18890-158">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="18890-159">Elemento</span><span class="sxs-lookup"><span data-stu-id="18890-159">Item</span></span></th>
<th><span data-ttu-id="18890-160">Notas</span><span class="sxs-lookup"><span data-stu-id="18890-160">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="18890-161">Configuración de Equipos de espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="18890-161">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="18890-162">Solo en teams, todas las características de chat y llamadas están solo en Teams.</span><span class="sxs-lookup"><span data-stu-id="18890-162">Teams Only mode, all chat and calling features are in Teams Only.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="18890-163">Chat/Comunicación externa en Teams</span><span class="sxs-lookup"><span data-stu-id="18890-163">Chat / External Communication in Teams</span></span></td>
<td><p><span data-ttu-id="18890-164">Puede realizar comunicaciones internas (internos de Microsoft 365 u Office 365) y chats externos desde Teams.</span><span class="sxs-lookup"><span data-stu-id="18890-164">Internal (intra Microsoft 365 or Office 365 organization) and external chat communication possible from Teams.</span></span></p>
<p><span data-ttu-id="18890-165"><em>Nota: Las entradas DNS deben configurarse para el acceso externo.</span><span class="sxs-lookup"><span data-stu-id="18890-165"><em>Note: DNS entries must be configured for external access.</span></span> <span data-ttu-id="18890-166">Los registros DNS de Skype Empresarial son necesarios aunque no tenga Skype Empresarial local o en Microsoft 365 u Office 365 para permitir la federación con entornos de Lync y Skype Empresarial:</span><span class="sxs-lookup"><span data-stu-id="18890-166">Skype for Business DNS records are needed even though you don't have Skype for Business on-premises, or in Microsoft 365 or Office 365, to allow federation with Lync and Skype for Business environments:</span></span><br /><span data-ttu-id="18890-167">
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">Registros del sistema de nombres de dominio externos</a></em></span><span class="sxs-lookup"><span data-stu-id="18890-167">
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">External Domain Name System records</a></em></span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="18890-168">Crear y ver reuniones en Teams</span><span class="sxs-lookup"><span data-stu-id="18890-168">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="18890-169">Puede crear reuniones internas y externas a través del complemento de Outlook.</span><span class="sxs-lookup"><span data-stu-id="18890-169">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="18890-170">La funcionalidad de acceso telefónico local y de salida RTC está disponible con las licencias de Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="18890-170">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="18890-171">El acceso al calendario de Teams requiere la implementación local de CU3+ de Exchange 2016 con Exchange hybrid established: Crear una implementación híbrida con <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">el Asistente para la configuración híbrida.</a> </span><span class="sxs-lookup"><span data-stu-id="18890-171">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established: <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a> </span></span></p>
<p><span data-ttu-id="18890-172">Además de la configuración híbrida de Exchange, establezca la autenticación OAuth de Exchange: Configurar la autenticación de OAuth entre organizaciones de <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> Exchange y Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="18890-172">In addition to Exchange hybrid configuration, establish Exchange OAuth authentication: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Configure OAuth authentication between Exchange and Exchange Online organizations".</span></span></p>

</p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="18890-173">Características de llamadas</span><span class="sxs-lookup"><span data-stu-id="18890-173">Calling Features</span></span><br />
<span data-ttu-id="18890-174">VoIP/RTC en Teams</span><span class="sxs-lookup"><span data-stu-id="18890-174">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="18890-175">VoIP interna y externamente para el espacio empresarial está disponible.</span><span class="sxs-lookup"><span data-stu-id="18890-175">VoIP internally and externally to the tenant is available.</span></span></p>
<p><span data-ttu-id="18890-176">Los servicios RTC se pueden configurar a través de Microsoft Phone System, además de agregar un plan de llamadas de Microsoft o enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="18890-176">PSTN services can be configured via Microsoft Phone System, plus adding a Microsoft Calling Plan or Direct Routing.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="18890-177">Colaboración de equipos y canales en Teams</span><span class="sxs-lookup"><span data-stu-id="18890-177">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="18890-178">Para obtener una experiencia completa, incluidas las características de cumplimiento, es necesario asignar al usuario una licencia de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="18890-178">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="18890-179">No es necesaria la migración de sitios de SharePoint locales existentes.</span><span class="sxs-lookup"><span data-stu-id="18890-179">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="18890-180">OneDrive para la Empresa (uso compartido de archivos P2P)</span><span class="sxs-lookup"><span data-stu-id="18890-180">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="18890-181">OneDrive para la Empresa requiere que un usuario tenga asignada una licencia de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="18890-181">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="18890-182">Sin este uso compartido de archivos punto a punto de licencia no será posible.</span><span class="sxs-lookup"><span data-stu-id="18890-182">Without this license peer-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="18890-183">Plataforma de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="18890-183">Application platform</span></span></td>
<td><span data-ttu-id="18890-184">Los usuarios podrán usar las aplicaciones designadas para ellos según las directivas de su empresa.</span><span class="sxs-lookup"><span data-stu-id="18890-184">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="18890-185">Más información aquí: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Configuración de administración de aplicaciones en Teams</a></span><span class="sxs-lookup"><span data-stu-id="18890-185">Learn more here: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="18890-186">Características de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="18890-186">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="18890-187">Las directivas de retención están disponibles.</span><span class="sxs-lookup"><span data-stu-id="18890-187">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="18890-188">Se admite la exhibición de documentos electrónicos y la retención legal para el cumplimiento de los mensajes de canal.</span><span class="sxs-lookup"><span data-stu-id="18890-188">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="18890-189">Las directivas de prevención de pérdida de datos (DLP) están disponibles.</span><span class="sxs-lookup"><span data-stu-id="18890-189">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="18890-190">Conjunto completo de características disponible con Exchange Online; Exchange local admite la mayoría de estas características.</span><span class="sxs-lookup"><span data-stu-id="18890-190">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="18890-191">Para obtener una lista completa, vea <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">cómo interactúan Exchange y Teams.</a></span><span class="sxs-lookup"><span data-stu-id="18890-191">For a full list, see <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a>.</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a><span data-ttu-id="18890-192">Pasos de habilitación para organizaciones sin Skype Empresarial o Lync Server</span><span class="sxs-lookup"><span data-stu-id="18890-192">Enablement steps for organizations without Skype for Business or Lync Server</span></span>

1.  <span data-ttu-id="18890-193">Cumpla los requisitos previos detallados en la sección anterior Comenzar aquí</span><span class="sxs-lookup"><span data-stu-id="18890-193">Meet pre-requisites detailed in the Start Here section above</span></span>

2.  <span data-ttu-id="18890-194">Cambie el espacio empresarial al modo solo teams (solo para inquilinos existentes): [establecer la configuración de coexistencia y actualización.](setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="18890-194">Switch tenant into Teams Only mode (for existing tenants only): [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

3.  <span data-ttu-id="18890-195">Configure el inquilino de acuerdo con las directivas empresariales/empresariales de su empresa: administre la configuración de [Microsoft Teams para su organización.](enable-features-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="18890-195">Configure your tenant in accordance with your company's business/company policies: [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

4.  <span data-ttu-id="18890-196">Implementar el cliente de Teams a los usuarios: [Obtener clientes para Teams](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="18890-196">Deploy the Teams client to your users: [Get clients for Teams](get-clients.md)</span></span>

5.  <span data-ttu-id="18890-197">Impulsar el programa de adopción</span><span class="sxs-lookup"><span data-stu-id="18890-197">Drive your adoption program</span></span>  
    [<span data-ttu-id="18890-198">Adoptar Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="18890-198">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="18890-199">Lista de comprobación para el inicio rápido de la adopción de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="18890-199">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="18890-200">Empezar a planificar el desplazamiento de otras cargas de trabajo a Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="18890-200">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a><span data-ttu-id="18890-201">Organizaciones **<span class="underline">con</span>** Skype Empresarial o Lync Server</span><span class="sxs-lookup"><span data-stu-id="18890-201">Organizations **<span class="underline">with</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="18890-202">En este punto de partida se supone que su organización utiliza Skype Empresarial 2019 o 2015+ o Lync 2013+ servidor local.</span><span class="sxs-lookup"><span data-stu-id="18890-202">This starting point assumes that your organization utilizes Skype for Business 2019 or 2015+ or Lync 2013+ server on premises.</span></span> <span data-ttu-id="18890-203">Ya tenemos amplias directrices para las organizaciones que migran de servidores locales a Teams y deben seguirse para estos escenarios.</span><span class="sxs-lookup"><span data-stu-id="18890-203">We already have extensive guidance for organizations migrating from on premises servers to Teams and it should be followed for these scenarios.</span></span> <span data-ttu-id="18890-204">Esta guía es específica para el escenario en el que Teams es la primera aplicación que utiliza en Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="18890-204">This guidance is specific to the scenario that Teams is the first application you utilize in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="18890-205">En la tabla siguiente se detalla la configuración de alto nivel y las capacidades del usuario final de Teams para los servicios principales.</span><span class="sxs-lookup"><span data-stu-id="18890-205">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="18890-206">Elemento</span><span class="sxs-lookup"><span data-stu-id="18890-206">Item</span></span></th>
<th><span data-ttu-id="18890-207">Notas</span><span class="sxs-lookup"><span data-stu-id="18890-207">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="18890-208">Configuración de Equipos de espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="18890-208">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="18890-209">Modo de islas.</span><span class="sxs-lookup"><span data-stu-id="18890-209">Islands mode.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="18890-210">Chat/Comunicación externa en Teams</span><span class="sxs-lookup"><span data-stu-id="18890-210">Chat / External Communication in Teams</span></span></td>
<td><span data-ttu-id="18890-211">Interna solo dentro de su propio espacio empresarial, la comunicación externa (federación) es a través de su implementación de Skype Empresarial o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="18890-211">Internal within your own tenant only, external communication (federation) is via your Skype for Business or Lync server deployment.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="18890-212">Crear y ver reuniones en Teams</span><span class="sxs-lookup"><span data-stu-id="18890-212">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="18890-213">Puede crear reuniones internas y externas a través del complemento de Outlook.</span><span class="sxs-lookup"><span data-stu-id="18890-213">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="18890-214">La funcionalidad de acceso telefónico local y de salida RTC está disponible con las licencias de Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="18890-214">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="18890-215">El acceso al calendario de Teams requiere la implementación local de CU3+ de Exchange 2016 con Exchange híbrido establecido:</span><span class="sxs-lookup"><span data-stu-id="18890-215">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established:</span></span><br /><span data-ttu-id="18890-216">
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Cree una implementación híbrida con el Asistente para la configuración híbrida.</a></span><span class="sxs-lookup"><span data-stu-id="18890-216">
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a></span></span></p>
<p><span data-ttu-id="18890-217">El administrador puede controlar el complemento de Outlook de Skype Empresarial a través del atributo PreferredMeetingProviderForIslandsMode de la directiva de reunión de Teams:<a href="https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy.</a></span><span class="sxs-lookup"><span data-stu-id="18890-217">Administrator can control the Skype for Business Outlook add-in via the Teams meeting policy’s PreferredMeetingProviderForIslandsMode attribute:<a href="https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy</a>.</span></span></p> 
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="18890-218">Características de llamadas</span><span class="sxs-lookup"><span data-stu-id="18890-218">Calling Features</span></span><br />
<span data-ttu-id="18890-219">VoIP/RTC en Teams</span><span class="sxs-lookup"><span data-stu-id="18890-219">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="18890-220">VoIP internamente para el espacio empresarial está disponible.</span><span class="sxs-lookup"><span data-stu-id="18890-220">VoIP internally to the tenant is available.</span></span></p>
<p><span data-ttu-id="18890-221">Los servicios de RTC o de plan de llamadas no están disponibles hasta que se mueve el usuario a la experiencia solo de Teams.</span><span class="sxs-lookup"><span data-stu-id="18890-221">PSTN or Calling Plan services are not available until the user is moved to Teams Only experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="18890-222">Colaboración de equipos y canales en Teams</span><span class="sxs-lookup"><span data-stu-id="18890-222">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="18890-223">Para obtener una experiencia completa, incluidas las características de cumplimiento, es necesario asignar al usuario una licencia de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="18890-223">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="18890-224">No es necesaria la migración de sitios de SharePoint locales existentes.</span><span class="sxs-lookup"><span data-stu-id="18890-224">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="18890-225">OneDrive para la Empresa (uso compartido de archivos P2P)</span><span class="sxs-lookup"><span data-stu-id="18890-225">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="18890-226">OneDrive para la Empresa requiere que un usuario tenga asignada una licencia de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="18890-226">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="18890-227">Sin esta licencia no será posible compartir archivos por punto.</span><span class="sxs-lookup"><span data-stu-id="18890-227">Without this license per-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="18890-228">Plataforma de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="18890-228">Application platform</span></span></td>
<td><span data-ttu-id="18890-229">Los usuarios podrán usar las aplicaciones designadas para ellos según las directivas de su empresa.</span><span class="sxs-lookup"><span data-stu-id="18890-229">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="18890-230">Más información aquí: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Configuración de administración de aplicaciones en Teams</a></span><span class="sxs-lookup"><span data-stu-id="18890-230">Learn more here: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="18890-231">Características de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="18890-231">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="18890-232">Las directivas de retención están disponibles.</span><span class="sxs-lookup"><span data-stu-id="18890-232">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="18890-233">Se admite la exhibición de documentos electrónicos y la retención legal para el cumplimiento de los mensajes de canal.</span><span class="sxs-lookup"><span data-stu-id="18890-233">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="18890-234">Las directivas de prevención de pérdida de datos (DLP) están disponibles.</span><span class="sxs-lookup"><span data-stu-id="18890-234">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="18890-235">Conjunto completo de características disponible con Exchange Online; Exchange local admite la mayoría de estas características.</span><span class="sxs-lookup"><span data-stu-id="18890-235">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="18890-236">Para obtener una lista completa, vea <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">cómo interactúan Exchange y Teams.</a></span><span class="sxs-lookup"><span data-stu-id="18890-236">For a complete list, see <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact.</a></span></span></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a><span data-ttu-id="18890-237">Pasos de habilitación para organizaciones con Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="18890-237">Enablement steps for organizations with Skype for Business Server</span></span>  

1.  <span data-ttu-id="18890-238">Cumpla los requisitos previos detallados en la sección Anterior Comenzar aquí.</span><span class="sxs-lookup"><span data-stu-id="18890-238">Meet pre-requisites detailed in the Start Here section above.</span></span>

2.  <span data-ttu-id="18890-239">Cambiar el inquilino al modo Islas (para inquilinos aprovisionados DESPUÉS del 1/9/2019, ponte en contacto con el servicio de soporte técnico para realizar este cambio)</span><span class="sxs-lookup"><span data-stu-id="18890-239">Switch tenant into Islands mode (for tenants provisioned AFTER 9/1/2019, please contact support to make this change)</span></span>  
    [<span data-ttu-id="18890-240">Configurar su coexistencia y la configuración de actualización</span><span class="sxs-lookup"><span data-stu-id="18890-240">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

3.  <span data-ttu-id="18890-241">Configurar el inquilino de acuerdo con las directivas de empresa/empresa de su empresa</span><span class="sxs-lookup"><span data-stu-id="18890-241">Configure your tenant in accordance with your company's business/company policies</span></span>  
    [<span data-ttu-id="18890-242">Administrar la configuración de Microsoft Teams para su organización</span><span class="sxs-lookup"><span data-stu-id="18890-242">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)

4.  <span data-ttu-id="18890-243">Implementar el cliente de Teams</span><span class="sxs-lookup"><span data-stu-id="18890-243">Deploy the Teams client</span></span>  
    [<span data-ttu-id="18890-244">Obtener clientes para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="18890-244">Get clients for Teams</span></span>](get-clients.md)

5.   <span data-ttu-id="18890-245">Impulsar el programa de adopción</span><span class="sxs-lookup"><span data-stu-id="18890-245">Drive your adoption program</span></span>  
    [<span data-ttu-id="18890-246">Adoptar Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="18890-246">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)<br/>
    [<span data-ttu-id="18890-247">Lista de comprobación para el inicio rápido de la adopción de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="18890-247">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="18890-248">Empezar a planificar el desplazamiento de otras cargas de trabajo a Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="18890-248">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

7.  <span data-ttu-id="18890-249">Establecer Skype Empresarial híbrido y seguir las rutas de actualización recomendadas para los servidores de Skype Empresarial y Lync</span><span class="sxs-lookup"><span data-stu-id="18890-249">Establish Skype for Business hybrid and follow the recommended upgrade paths for Skype for Business and Lync servers</span></span>  
    [<span data-ttu-id="18890-250">Actualizar de Skype Empresarial local a Teams</span><span class="sxs-lookup"><span data-stu-id="18890-250">Upgrade from Skype for Business on-premises to Teams</span></span>](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a><span data-ttu-id="18890-251">Instrucción de cierre</span><span class="sxs-lookup"><span data-stu-id="18890-251">Closing statement</span></span>

<span data-ttu-id="18890-252">Microsoft Teams puede permitir que su organización pueda reunir a todos los empleados, trabajadores de la información y trabajadores de la línea frontal en una sola plataforma.</span><span class="sxs-lookup"><span data-stu-id="18890-252">Microsoft Teams can be an enabler for your organization to bring all the employees, information workers and Frontline workers, together on a single platform.</span></span> <span data-ttu-id="18890-253">Puedes empezar [hoy](https://products.office.com/microsoft-teams/group-chat-software) mismo.</span><span class="sxs-lookup"><span data-stu-id="18890-253">You can [get started](https://products.office.com/microsoft-teams/group-chat-software) today.</span></span> <span data-ttu-id="18890-254">Puedes estar en contacto con todos nuestros anuncios más recientes y con las actualizaciones mensuales de productos [aquí.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)</span><span class="sxs-lookup"><span data-stu-id="18890-254">You can keep in touch with all our latest announcements and monthly product updates [here](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).</span></span>

<span data-ttu-id="18890-255">Además, a medida que empresas de todo el mundo administran la situación actual de COVID-19, hemos creado una serie de contenido que le ayudará a usar Teams para obtener el máximo impacto en su organización.</span><span class="sxs-lookup"><span data-stu-id="18890-255">Additionally, as companies around the world are managing the current COVID-19 situation, we have created a series of content that will help you utilize Teams for the maximum impact in your organization.</span></span>

  - <span data-ttu-id="18890-256">Nuestro [compromiso con los clientes durante covid-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span><span class="sxs-lookup"><span data-stu-id="18890-256">Our [commitment to customers during COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span></span>

  - [<span data-ttu-id="18890-257">Dentro de dos semanas: lo que hemos aprendido sobre el trabajo remoto</span><span class="sxs-lookup"><span data-stu-id="18890-257">2 weeks in: what we've learned about remote work</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [<span data-ttu-id="18890-258">Realizar reuniones y eventos en línea</span><span class="sxs-lookup"><span data-stu-id="18890-258">Delivering online meetings and events</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [<span data-ttu-id="18890-259">Ayudar a las pequeñas y medianas empresas a trabajar de forma remota con Teams</span><span class="sxs-lookup"><span data-stu-id="18890-259">Helping small and medium-sized businesses work remotely with Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [<span data-ttu-id="18890-260">Transformación digital de eventos en directo: observaciones de Bob Bejano desde la línea frontal</span><span class="sxs-lookup"><span data-stu-id="18890-260">Digital transformation of live events: Bob Bejan's observations from the frontline</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - <span data-ttu-id="18890-261">[Las 9 formas principales en que TI de Microsoft permite trabajar de forma remota a sus empleados](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/).</span><span class="sxs-lookup"><span data-stu-id="18890-261">[The top 9 ways Microsoft IT is enabling remote work for its employees](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)</span></span>

  - [<span data-ttu-id="18890-262">Trabaje de forma remota, manténgase seguro: sugerencias para LOS MÁSÓXOS</span><span class="sxs-lookup"><span data-stu-id="18890-262">Work remotely, stay secure—tips for CISOs</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [<span data-ttu-id="18890-263">Ayudar a profesores y alumnos a cambiar al aprendizaje remoto</span><span class="sxs-lookup"><span data-stu-id="18890-263">Helping teachers and students make the switch to remote learning</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [<span data-ttu-id="18890-264">Mantenerse productivo mientras trabaja de forma remota con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="18890-264">Staying productive while working remotely with Microsoft Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a><span data-ttu-id="18890-265">Referencia de los Servicios de soporte técnico</span><span class="sxs-lookup"><span data-stu-id="18890-265">Support Services reference</span></span>

<span data-ttu-id="18890-266">Teams se basa en Exchange Online, SharePoint Online, OneDrive para la Empresa y Grupos de Microsoft 365 para proporcionar a los usuarios una experiencia de Microsoft 365 u Office 365 totalmente integrada.</span><span class="sxs-lookup"><span data-stu-id="18890-266">Teams relies on Exchange Online, SharePoint Online, OneDrive for Business and Microsoft 365 Groups to provide your users with a fully integrated Microsoft 365 or Office 365 experience.</span></span> <span data-ttu-id="18890-267">Como se indicó anteriormente, Teams trabajará sin implementar estos servicios de forma completa, con funcionalidades limitadas.</span><span class="sxs-lookup"><span data-stu-id="18890-267">As noted above, Teams will work without full deploying these services – with limited capabilities.</span></span> <span data-ttu-id="18890-268">Puede obtener más información sobre Teams y sus requisitos previos aquí: [Le damos la bienvenida a Teams.](teams-overview.md)</span><span class="sxs-lookup"><span data-stu-id="18890-268">You can read more about Teams and its pre-requisites here: [Welcome to Teams](teams-overview.md).</span></span>

<span data-ttu-id="18890-269">Para obtener información específica sobre cada uno de los servicios enumerados anteriormente, siga los siguientes vínculos:</span><span class="sxs-lookup"><span data-stu-id="18890-269">For specifics on each of the services listed above, please follow the links below:</span></span>

  - <span data-ttu-id="18890-270">Exchange Online se usa para las características de calendario y almacenar mensajes de punto a punto en Teams.</span><span class="sxs-lookup"><span data-stu-id="18890-270">Exchange Online is used for calendaring features and storing peer to peer messages in Teams.</span></span> <span data-ttu-id="18890-271">Para obtener más información, lea [cómo interactúan Exchange y Teams](exchange-teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="18890-271">To learn more, read [How Exchange and Teams interact](exchange-teams-interact.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="18890-272">Para la interoperabilidad de Teams con Exchange local, debe configurar el nuevo protocolo de autenticación OAuth de Exchange como se describe en Configurar autenticación OAuth entre organizaciones [de Exchange y Exchange Online.](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)</span><span class="sxs-lookup"><span data-stu-id="18890-272">For Teams interop with Exchange on-premises, you must configure the new Exchange OAuth authentication protocol as described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span></span>

  - <span data-ttu-id="18890-273">SharePoint se usa para compartir archivos en canales, mientras que /OneDrive para la Empresa se usa para el uso compartido de archivos en chats grupales o uno a uno.</span><span class="sxs-lookup"><span data-stu-id="18890-273">SharePoint is used for file sharing in channels, while /OneDrive for Business is used for file sharing in 1:1 or group chat.</span></span> <span data-ttu-id="18890-274">Para obtener más información, lea [Cómo interactúan SharePoint Online y OneDrive para la Empresa con Microsoft Teams.](sharepoint-onedrive-interact.md)</span><span class="sxs-lookup"><span data-stu-id="18890-274">To learn more, read [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

  - <span data-ttu-id="18890-275">[Los grupos de Microsoft 365 se](office-365-groups.md) utilizan para la creación o administración de equipos y canales.</span><span class="sxs-lookup"><span data-stu-id="18890-275">[Microsoft 365 Groups](office-365-groups.md) are used for team and channel creation/management.</span></span>


## <a name="related-topics"></a><span data-ttu-id="18890-276">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="18890-276">Related topics</span></span>

[<span data-ttu-id="18890-277">Carteles de soluciones de telefonía y arquitectura de TI de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="18890-277">Microsoft Teams IT architecture and telephony solutions posters</span></span>](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[<span data-ttu-id="18890-278">Planear la conectividad híbrida entre Skype Empresarial Server y Office 365</span><span class="sxs-lookup"><span data-stu-id="18890-278">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[<span data-ttu-id="18890-279">Dar soporte a los trabajadores remotos mediante Teams</span><span class="sxs-lookup"><span data-stu-id="18890-279">Support remote workers using Teams</span></span>](support-remote-work-with-teams.md)

[<span data-ttu-id="18890-280">Trabajar de forma remota con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="18890-280">Work remotely with Microsoft 365</span></span>](https://aka.ms/remote-work)
