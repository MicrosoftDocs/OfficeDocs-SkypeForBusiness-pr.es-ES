---
title: Implementación de Microsoft Teams First
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
description: Use estas instrucciones para realizar Microsoft Teams como su primera carga de trabajo de Microsoft 365 u Office 365.
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
# <a name="roll-out-microsoft-teams-first"></a><span data-ttu-id="c6846-103">Implementación de Microsoft Teams First</span><span class="sxs-lookup"><span data-stu-id="c6846-103">Roll out Microsoft Teams First</span></span>

<span data-ttu-id="c6846-104">Microsoft Teams puede ayudar a sus empleados a mantenerse conectados y colaborar entre sí, especialmente en el momento sin precedentes actual en el que el trabajo remoto es una realidad de los empleados de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="c6846-104">Microsoft Teams can help your employees stay connected and collaborate with each other, especially in the current unprecedented time where remote work is a reality of employees around the world.</span></span> <span data-ttu-id="c6846-105">Poder chatear, realizar reuniones de vídeo y colaborar en documentos de Office dentro de Teams puede ayudar a las empresas a mantenerse productivas.</span><span class="sxs-lookup"><span data-stu-id="c6846-105">Being able to chat, do video meetings and collaborate on Office documents within Teams can help companies stay productive.</span></span> <span data-ttu-id="c6846-106">Ya sea una pequeña empresa, una organización sin ánimo de lucro o una organización grande, puede empezar a usar Teams como la primera carga de trabajo dentro de Microsoft 365 u Conjunto de aplicaciones de Office 365 antes de implementar cualquier otra aplicación o servicio de Office.</span><span class="sxs-lookup"><span data-stu-id="c6846-106">Whether you are a small business, a non-profit or a large organization, you can get started with Teams as the first workload within Microsoft 365 or Office 365 suite before deploying any other Office app or service.</span></span>

<span data-ttu-id="c6846-107">En este artículo se detallan las consideraciones que debe realizar con el enfoque "Teams First".</span><span class="sxs-lookup"><span data-stu-id="c6846-107">This article details the considerations you must make with the "Teams First" approach.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c6846-108">Aunque Teams puede ser la primera carga de trabajo implementada en la nube de su organización, la implementación de Teams debe formar parte de su estrategia general de implementación en la nube.</span><span class="sxs-lookup"><span data-stu-id="c6846-108">While Teams can be your organization's first cloud deployed workload, deploying Teams should be part of your overall cloud deployment strategy.</span></span>

<span data-ttu-id="c6846-109">Si ya ha lanzado otros servicios de Microsoft 365 u Office 365 y Teams es la siguiente carga de trabajo que se va a realizar (en lugar de la primera), empiece por Cómo realizar [Teams.](./deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c6846-109">If you have already rolled out other Microsoft 365 or Office 365 services and Teams is your next workload to roll out (instead of the first), start with [How to roll out Teams](./deploy-overview.md).</span></span>

## <a name="start-here"></a><span data-ttu-id="c6846-110">Empiece aquí</span><span class="sxs-lookup"><span data-stu-id="c6846-110">Start here</span></span>

<span data-ttu-id="c6846-111">Para empezar con la implementación de Teams First, tendrá que cumplir como mínimo algunos requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="c6846-111">To get started with your Teams First deployment you will need to meet at minimum some pre-requisites.</span></span> <span data-ttu-id="c6846-112">La siguiente lista mostrará lo que debe tener en su organización para poder habilitar Teams:</span><span class="sxs-lookup"><span data-stu-id="c6846-112">The following list will show what you must have in place for your organization before Teams can be enabled:</span></span>

1.  <span data-ttu-id="c6846-113">Una organización de Microsoft 365 u Office 365 configurada con su nombre de dominio</span><span class="sxs-lookup"><span data-stu-id="c6846-113">A Microsoft 365 or Office 365 organization configured with your domain name</span></span>

2.  <span data-ttu-id="c6846-114">Conectividad de Azure Active Directory (conexión AAD) o una solución de sincronización de identidad de nube similar, con todos los atributos necesarios sincronizados con el inquilino</span><span class="sxs-lookup"><span data-stu-id="c6846-114">Azure Active Directory connectivity (AAD connect) or similar cloud identity sync solution – with all required attributes synched with your tenant</span></span>  
    <span data-ttu-id="c6846-115">Para comprender los atributos sincronizados con la sincronización de AAD, lea [Sincronización de Azure AD Connect: Atributos sincronizados con Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span><span class="sxs-lookup"><span data-stu-id="c6846-115">To understand the attributes synchronized with AAD sync, read [Azure AD Connect sync: Attributes synchronized to Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span></span>

3.  <span data-ttu-id="c6846-116">Licencias de usuario adecuadas asignadas para Teams</span><span class="sxs-lookup"><span data-stu-id="c6846-116">Appropriate user licenses assigned for Teams</span></span>  
    <span data-ttu-id="c6846-117">Para comprender las licencias de Teams, lea [Descripción del servicio de Microsoft Teams](/office365/servicedescriptions/teams-service-description).</span><span class="sxs-lookup"><span data-stu-id="c6846-117">To understand Teams licensing, read [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

4.  <span data-ttu-id="c6846-118">Red de la organización preparada para Teams</span><span class="sxs-lookup"><span data-stu-id="c6846-118">Organization's network prepared for Teams</span></span>  
    <span data-ttu-id="c6846-119">Para comprender la preparación de la red, lea Preparar la red de su organización [para Teams.](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="c6846-119">To understand network preparation, read [Prepare your organization's network for Teams](prepare-network.md).</span></span>

5.  <span data-ttu-id="c6846-120">Permitir el acceso de red a Exchange, Sharepoint y OneDrive para la Empresa en Microsoft 365 u Office 365: direcciones URL e intervalos de direcciones IP de [Office 365.](/office365/enterprise/urls-and-ip-address-ranges)</span><span class="sxs-lookup"><span data-stu-id="c6846-120">Allow network access to Exchange, Sharepoint, and OneDrive for Business in Microsoft 365 or Office 365: [Office 365 URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="c6846-121">Los inquilinos creados después del 1 de septiembre de 2019 se aprovisionan en modo Solo para equipos.</span><span class="sxs-lookup"><span data-stu-id="c6846-121">Tenants created after September 1, 2019 are provisioned in Teams Only mode.</span></span>
> 
> [!IMPORTANT]
> <span data-ttu-id="c6846-122">Si tiene Skype Empresarial Server implementado y su inquilino se aprovisionó después del 1 de septiembre de 2019, póngase en contacto con el soporte técnico para habilitar las capacidades de coexistencia de Teams.</span><span class="sxs-lookup"><span data-stu-id="c6846-122">If you have Skype for Business Server deployed, and your tenant was provisioned AFTER September 1, 2019, please contact support to enable coexistence capabilities for Teams.</span></span> <span data-ttu-id="c6846-123">Asegúrese de que la "directiva de actualización de toda la organización" está establecida en "Modo <span class="underline">isla"</span> antes de asignar licencias de Teams a un usuario.</span><span class="sxs-lookup"><span data-stu-id="c6846-123">Make sure your 'Organization wide upgrade policy' is set to 'Island mode' <span class="underline">before</span> you assign any Teams licenses to a user.</span></span>

## <a name="migration-starting-points"></a><span data-ttu-id="c6846-124">Puntos iniciales de migración</span><span class="sxs-lookup"><span data-stu-id="c6846-124">Migration Starting points</span></span>

<span data-ttu-id="c6846-125">Su viaje a Microsoft 365 u Office 365 y las características disponibles en Teams en función de su punto de partida y de la existencia de Skype Empresarial local o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c6846-125">Your journey to Microsoft 365 or Office 365 and features available in Teams depending on your starting point and the existence of on premises Skype for Business or Lync server.</span></span> <span data-ttu-id="c6846-126">En las secciones siguientes se detallarán las capacidades básicas y las opciones de configuración, además de los requisitos previos anteriores.</span><span class="sxs-lookup"><span data-stu-id="c6846-126">The following sections will detail basic capabilities and configuration options in addition to the pre-requisites above.</span></span> <span data-ttu-id="c6846-127">Hemos desglosado los escenarios de punto de partida para los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="c6846-127">We have broken down the starting point scenarios to the following topics:</span></span>

<span data-ttu-id="c6846-128">**Configuración de Tenant Teams:** los modos de inquilino y usuario se usan para controlar el comportamiento del destinatario.</span><span class="sxs-lookup"><span data-stu-id="c6846-128">**Tenant Teams Configuration**: Tenant and user modes are used to control the recipient's behavior.</span></span> <span data-ttu-id="c6846-129">Esta configuración se puede asignar en el nivel de inquilino o en el nivel de usuario de una organización.</span><span class="sxs-lookup"><span data-stu-id="c6846-129">These settings can be assigned on the tenant level or the user level in an organization.</span></span> <span data-ttu-id="c6846-130">Para obtener más información, lea [Coexistencia con Skype Empresarial.](coexistence-chat-calls-presence.md)</span><span class="sxs-lookup"><span data-stu-id="c6846-130">To learn more, read [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>

<span data-ttu-id="c6846-131">**Chat/comunicación externa en Teams:** los servicios de chat hacen referencia a conversaciones de chat de punto a punto o grupales dentro y dentro de la organización o externamente a la organización.</span><span class="sxs-lookup"><span data-stu-id="c6846-131">**Chat / External communication in Teams**: Chat services refer to peer to peer or group chat conversations within and organization or externally to the organization.</span></span> <span data-ttu-id="c6846-132">La comunicación externa también se conoce como federación en Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="c6846-132">External communication is also referred to as federation in Skype for Business.</span></span>

<span data-ttu-id="c6846-133">Crear y ver reuniones en **Teams:** un usuario siempre puede crear reuniones en línea a través del complemento Outlook Teams y el acceso telefónico RTC está disponible en todos los escenarios una vez que el usuario tiene licencia.</span><span class="sxs-lookup"><span data-stu-id="c6846-133">**Create and view meetings in Teams**: A user can always create online meetings via the Outlook Teams add-in and PSTN dial-in is available in all scenarios once the user is licensed.</span></span> <span data-ttu-id="c6846-134">Información de calendario de Teams y Skype Empresarial store en el buzón de Exchange del usuario.</span><span class="sxs-lookup"><span data-stu-id="c6846-134">Teams and Skype for Business store calendaring information in the user's Exchange mailbox.</span></span> <span data-ttu-id="c6846-135">En el servidor exchange local debe Exchange Server 2016 CU3 o posterior para que el cliente de Teams pueda interactuar con el buzón del usuario.</span><span class="sxs-lookup"><span data-stu-id="c6846-135">On premises Exchange server must be Exchange Server 2016 CU3 or above for the Teams client to be able to interact with the user's mailbox.</span></span> <span data-ttu-id="c6846-136">Sin acceso al buzón de Exchange, el icono Calendario en Teams no aparecerá y el usuario no podrá ver, crear o modificar reuniones en el cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="c6846-136">Without Exchange mailbox access the Calendar icon in Teams will not appear and they user will not be able to view, create or modify meetings in the Teams client.</span></span>

<span data-ttu-id="c6846-137">**Características de llamadas VoIP/RTC en Teams:** las llamadas pueden ser Llamadas a través de IP (VoIP) o Red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="c6846-137">**Calling features VoIP / PSTN in Teams**: Calling can be Voice over IP (VoIP) or Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="c6846-138">La conectividad VoIP se produce de forma nativa entre los clientes de Teams, mientras que la conectividad RTC se produce cuando un usuario marca un número de teléfono externo.</span><span class="sxs-lookup"><span data-stu-id="c6846-138">VoIP connectivity happens natively between Teams clients, while PSTN connectivity happen when a user dials an outside phone number.</span></span>  

<span data-ttu-id="c6846-139">Teams admite dos tipos de conectividad RTC.</span><span class="sxs-lookup"><span data-stu-id="c6846-139">Teams support two types of PSTN connectivity.</span></span> <span data-ttu-id="c6846-140">Plan de llamadas de Microsoft, cuando Microsoft proporciona infraestructura de telefonía, incluido el número de teléfono de un usuario, o configuración de enrutamiento directo, donde el cliente proporciona la conectividad de telefonía a través de un controlador de borde de sesión (SBC) para el usuario de Teams.</span><span class="sxs-lookup"><span data-stu-id="c6846-140">Microsoft Calling Plan, when Microsoft provides telephony infrastructure including the phone number for a user, or Direct Routing configuration, where the customer provides the telephony connectivity over a Session Border Controller (SBC) for the Teams user.</span></span>  
<span data-ttu-id="c6846-141">Para obtener más información, lea [¿Qué plan de llamadas es adecuado para usted?](calling-plan-landing-page.md) y [Enrutamiento directo del sistema telefónico.](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="c6846-141">To learn more, read [Which Calling Plan is right for you?](calling-plan-landing-page.md) and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="c6846-142">**Colaboración de teams y canales en Teams:** en Teams, los equipos son grupos de personas que se reúnen para trabajar, proyectos o intereses comunes.</span><span class="sxs-lookup"><span data-stu-id="c6846-142">**Teams and Channels collaboration in Teams**: In Teams, teams are groups of people brought together for work, projects, or common interests.</span></span> <span data-ttu-id="c6846-143">Los equipos están hechos de canales.</span><span class="sxs-lookup"><span data-stu-id="c6846-143">Teams are made up of channels.</span></span> <span data-ttu-id="c6846-144">Cada canal se basa en un tema, como "Eventos de grupo", un nombre de departamento o simplemente por diversión.</span><span class="sxs-lookup"><span data-stu-id="c6846-144">Each channel is built around a topic, like "Team Events," a department name, or just for fun.</span></span> <span data-ttu-id="c6846-145">Los canales son los lugares donde se mantienen reuniones, se mantienen conversaciones y se trabaja en archivos juntos.</span><span class="sxs-lookup"><span data-stu-id="c6846-145">Channels are where you hold meetings, have conversations, and work on files together.</span></span> <span data-ttu-id="c6846-146">Durante la colaboración</span><span class="sxs-lookup"><span data-stu-id="c6846-146">During collaboration</span></span>

<span data-ttu-id="c6846-147">OneDrive para la Empresa (uso compartido de archivos **P2P)** en Teams: Fuera de Teams y canales, los usuarios de Teams pueden compartir archivos de punto a punto con OneDrive para la Empresa u otros programas de archivos de uso compartido P2P como Archivos Citrix, DropBox, Box y Google Drive.</span><span class="sxs-lookup"><span data-stu-id="c6846-147">**OneDrive for Business (P2P file sharing) in Teams**: Outside of Teams and Channels, Teams users can share files peer-to-peer using OneDrive for business or other P2P sharing file programs such as Citrix Files, DropBox, Box and Google Drive.</span></span> <span data-ttu-id="c6846-148">Para OneDrive para la Empresa, un usuario debe tener asignada una licencia de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="c6846-148">For OneDrive for business a user must have SharePoint Online license assigned.</span></span>

<span data-ttu-id="c6846-149">**Plataforma de aplicaciones:** las aplicaciones proporcionan herramientas integradas para que su organización obtenga más información sobre Teams.</span><span class="sxs-lookup"><span data-stu-id="c6846-149">**Application Platform**: Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="c6846-150">Estas aplicaciones combinan la funcionalidad de pestañas, extensiones de mensajería, conectores y bots proporcionados por Microsoft, creados por un tercero o por desarrolladores de su organización.</span><span class="sxs-lookup"><span data-stu-id="c6846-150">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="c6846-151">**Características de seguridad y cumplimiento:** Teams tiene una amplia gama de información para ayudarle con las áreas de cumplimiento, incluidas las directivas de retención, protección contra pérdida de datos (DLP), exhibición de documentos electrónicos y retención legal para canales, chats y archivos, búsqueda de registros de auditoría.</span><span class="sxs-lookup"><span data-stu-id="c6846-151">**Security and Compliance features:** Teams has a wide range of information to help you with compliance areas, including retention policies, Data Loss Protection (DLP), eDiscovery and legal hold for channels, chats and files, audit log search.</span></span> <span data-ttu-id="c6846-152">Para obtener más información, lea [Seguridad y cumplimiento en Microsoft Teams.](security-compliance-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c6846-152">To learn more, read [Security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="c6846-153">Las características de eDiscovery avanzadas requieren licencias E5.</span><span class="sxs-lookup"><span data-stu-id="c6846-153">Advance eDiscovery features require E5 licensing.</span></span>

<span data-ttu-id="c6846-154">[Comparar opciones de licencias.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)</span><span class="sxs-lookup"><span data-stu-id="c6846-154">[Compare licensing options](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>

<span data-ttu-id="c6846-155">Lea [Cómo interactúan Exchange y Microsoft Teams](exchange-teams-interact.md) para saber qué características de cumplimiento están disponibles en su escenario.</span><span class="sxs-lookup"><span data-stu-id="c6846-155">Read [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) to learn which compliance features are available in your scenario.</span></span>

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a><span data-ttu-id="c6846-156">Organizaciones **<span class="underline">sin</span>** Skype Empresarial o Lync Server</span><span class="sxs-lookup"><span data-stu-id="c6846-156">Organizations **<span class="underline">without</span>** Skype for Business or Lync Server</span></span>

<span data-ttu-id="c6846-157">Este punto de partida supone que su organización no usa Actualmente Skype Empresarial o Lync Server y Teams será su primera aplicación en Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="c6846-157">This starting point assumes that your organization does not utilize Skype for Business or Lync Server currently and Teams will be your first application in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="c6846-158">En la tabla siguiente se detalla la configuración de alto nivel y las capacidades de usuario final de Teams para los servicios principales.</span><span class="sxs-lookup"><span data-stu-id="c6846-158">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="c6846-159">Elemento</span><span class="sxs-lookup"><span data-stu-id="c6846-159">Item</span></span></th>
<th><span data-ttu-id="c6846-160">Notas</span><span class="sxs-lookup"><span data-stu-id="c6846-160">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="c6846-161">Configuración de Tenant Teams</span><span class="sxs-lookup"><span data-stu-id="c6846-161">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="c6846-162">Solo en modo Teams, todas las características de chat y llamadas están en Solo Teams.</span><span class="sxs-lookup"><span data-stu-id="c6846-162">Teams Only mode, all chat and calling features are in Teams Only.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c6846-163">Chat y comunicación externa en Teams</span><span class="sxs-lookup"><span data-stu-id="c6846-163">Chat / External Communication in Teams</span></span></td>
<td><p><span data-ttu-id="c6846-164">La comunicación interna (dentro de Microsoft 365 u organización de Office 365) y el chat externo posible desde Teams.</span><span class="sxs-lookup"><span data-stu-id="c6846-164">Internal (intra Microsoft 365 or Office 365 organization) and external chat communication possible from Teams.</span></span></p>
<p><span data-ttu-id="c6846-165"><em>Nota: Las entradas DNS deben configurarse para el acceso externo.</span><span class="sxs-lookup"><span data-stu-id="c6846-165"><em>Note: DNS entries must be configured for external access.</span></span> <span data-ttu-id="c6846-166">Los registros DNS de Skype Empresarial son necesarios aunque no tenga Skype Empresarial local, ni en Microsoft 365 u Office 365, para permitir la federación con entornos de Lync y Skype Empresarial:</span><span class="sxs-lookup"><span data-stu-id="c6846-166">Skype for Business DNS records are needed even though you don't have Skype for Business on-premises, or in Microsoft 365 or Office 365, to allow federation with Lync and Skype for Business environments:</span></span><br /><span data-ttu-id="c6846-167">
<a href="/office365/enterprise/external-domain-name-system-records">Registros del sistema de nombres de dominio externos</a></em></span><span class="sxs-lookup"><span data-stu-id="c6846-167">
<a href="/office365/enterprise/external-domain-name-system-records">External Domain Name System records</a></em></span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c6846-168">Crear y ver reuniones en Teams</span><span class="sxs-lookup"><span data-stu-id="c6846-168">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="c6846-169">Puede crear reuniones internas y externas a través del complemento de Outlook.</span><span class="sxs-lookup"><span data-stu-id="c6846-169">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="c6846-170">La capacidad de marcado RTC y de marcado de salida está disponible con las licencias de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="c6846-170">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="c6846-171">El acceso al calendario de Teams requiere exchange 2016 CU3+ local implementado con exchange híbrido establecido: Crear una implementación híbrida <a href="/exchange/hybrid-deployment/deploy-hybrid">con el Asistente para configuración híbrida.</a> </span><span class="sxs-lookup"><span data-stu-id="c6846-171">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established: <a href="/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a> </span></span></p>
<p><span data-ttu-id="c6846-172">Además de la configuración híbrida de Exchange, establezca la autenticación de OAuth de Exchange: Configurar la autenticación de OAuth entre las organizaciones <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> de Exchange y Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="c6846-172">In addition to Exchange hybrid configuration, establish Exchange OAuth authentication: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Configure OAuth authentication between Exchange and Exchange Online organizations".</span></span></p>

</p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c6846-173">Características de llamadas</span><span class="sxs-lookup"><span data-stu-id="c6846-173">Calling Features</span></span><br />
<span data-ttu-id="c6846-174">VoIP /RTC en Teams</span><span class="sxs-lookup"><span data-stu-id="c6846-174">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="c6846-175">VoIP interna y externamente para el inquilino está disponible.</span><span class="sxs-lookup"><span data-stu-id="c6846-175">VoIP internally and externally to the tenant is available.</span></span></p>
<p><span data-ttu-id="c6846-176">Los servicios RTC se pueden configurar a través de Microsoft Phone System, además de agregar un plan de llamadas de Microsoft o enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="c6846-176">PSTN services can be configured via Microsoft Phone System, plus adding a Microsoft Calling Plan or Direct Routing.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c6846-177">Colaboración de teams y canales en Teams</span><span class="sxs-lookup"><span data-stu-id="c6846-177">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="c6846-178">Para obtener una experiencia completa, incluidas las características de cumplimiento normativo, es necesario asignar una licencia de SharePoint Online al usuario.</span><span class="sxs-lookup"><span data-stu-id="c6846-178">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="c6846-179">No es necesaria la migración de sitios de SharePoint locales existentes.</span><span class="sxs-lookup"><span data-stu-id="c6846-179">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c6846-180">OneDrive para la Empresa (uso compartido de archivos P2P)</span><span class="sxs-lookup"><span data-stu-id="c6846-180">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="c6846-181">OneDrive para la Empresa requiere que un usuario tenga asignada una licencia de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="c6846-181">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="c6846-182">Sin este uso compartido de archivos punto a punto de licencia no será posible.</span><span class="sxs-lookup"><span data-stu-id="c6846-182">Without this license peer-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c6846-183">Plataforma de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="c6846-183">Application platform</span></span></td>
<td><span data-ttu-id="c6846-184">Los usuarios podrán usar las aplicaciones designadas disponibles para ellas según las directivas de su empresa.</span><span class="sxs-lookup"><span data-stu-id="c6846-184">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="c6846-185">Más información aquí: <a href="/microsoftteams/admin-settings">Configuración de administración de aplicaciones en Teams</a></span><span class="sxs-lookup"><span data-stu-id="c6846-185">Learn more here: <a href="/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c6846-186">Características de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="c6846-186">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="c6846-187">Las directivas de retención están disponibles.</span><span class="sxs-lookup"><span data-stu-id="c6846-187">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="c6846-188">Se admite la exhibición de documentos electrónicos y la retención legal para el cumplimiento en los mensajes de canal.</span><span class="sxs-lookup"><span data-stu-id="c6846-188">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="c6846-189">Las directivas de prevención de pérdida de datos (DLP) están disponibles.</span><span class="sxs-lookup"><span data-stu-id="c6846-189">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="c6846-190">Conjunto de características completo disponible con Exchange Online; Exchange local admite la mayoría de estas características.</span><span class="sxs-lookup"><span data-stu-id="c6846-190">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="c6846-191">Para obtener una lista completa, vea <a href="/MicrosoftTeams/exchange-teams-interact">Cómo interactúan Exchange y Teams.</a></span><span class="sxs-lookup"><span data-stu-id="c6846-191">For a full list, see <a href="/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a>.</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a><span data-ttu-id="c6846-192">Pasos de habilitación para organizaciones sin Skype Empresarial o Lync Server</span><span class="sxs-lookup"><span data-stu-id="c6846-192">Enablement steps for organizations without Skype for Business or Lync Server</span></span>

1.  <span data-ttu-id="c6846-193">Cumplir los requisitos previos detallados en la sección Empezar aquí anterior</span><span class="sxs-lookup"><span data-stu-id="c6846-193">Meet pre-requisites detailed in the Start Here section above</span></span>

2.  <span data-ttu-id="c6846-194">Cambiar el espacio empresarial al modo solo de Teams (solo para inquilinos existentes): [Establecer la configuración de coexistencia y actualización.](setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c6846-194">Switch tenant into Teams Only mode (for existing tenants only): [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

3.  <span data-ttu-id="c6846-195">Configure el espacio empresarial de acuerdo con las directivas empresariales o empresariales de su empresa: Administrar la configuración [de Microsoft Teams para su organización.](enable-features-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="c6846-195">Configure your tenant in accordance with your company's business/company policies: [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

4.  <span data-ttu-id="c6846-196">Implementar el cliente de Teams a los usuarios: [Obtener clientes para Teams](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="c6846-196">Deploy the Teams client to your users: [Get clients for Teams](get-clients.md)</span></span>

5.  <span data-ttu-id="c6846-197">Impulsar el programa de adopción</span><span class="sxs-lookup"><span data-stu-id="c6846-197">Drive your adoption program</span></span>  
    [<span data-ttu-id="c6846-198">Adoptar Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c6846-198">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="c6846-199">Lista de comprobación para el inicio rápido de la adopción de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c6846-199">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="c6846-200">Empezar a planear la mudanza de otras cargas de trabajo a Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="c6846-200">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a><span data-ttu-id="c6846-201">Organizaciones **<span class="underline">con</span>** Skype Empresarial o Lync Server</span><span class="sxs-lookup"><span data-stu-id="c6846-201">Organizations **<span class="underline">with</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="c6846-202">Este punto de partida supone que su organización utiliza Skype Empresarial 2019 o 2015+ o lync 2013+ servidor local.</span><span class="sxs-lookup"><span data-stu-id="c6846-202">This starting point assumes that your organization utilizes Skype for Business 2019 or 2015+ or Lync 2013+ server on premises.</span></span> <span data-ttu-id="c6846-203">Ya tenemos instrucciones exhaustivas para las organizaciones que migran desde servidores locales a Teams y deben seguirse para estos escenarios.</span><span class="sxs-lookup"><span data-stu-id="c6846-203">We already have extensive guidance for organizations migrating from on premises servers to Teams and it should be followed for these scenarios.</span></span> <span data-ttu-id="c6846-204">Esta guía es específica del escenario en el que Teams es la primera aplicación que usa en Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="c6846-204">This guidance is specific to the scenario that Teams is the first application you utilize in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="c6846-205">En la tabla siguiente se detalla la configuración de alto nivel y las capacidades de usuario final de Teams para los servicios principales.</span><span class="sxs-lookup"><span data-stu-id="c6846-205">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="c6846-206">Elemento</span><span class="sxs-lookup"><span data-stu-id="c6846-206">Item</span></span></th>
<th><span data-ttu-id="c6846-207">Notas</span><span class="sxs-lookup"><span data-stu-id="c6846-207">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="c6846-208">Configuración de Tenant Teams</span><span class="sxs-lookup"><span data-stu-id="c6846-208">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="c6846-209">Modo Islas.</span><span class="sxs-lookup"><span data-stu-id="c6846-209">Islands mode.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c6846-210">Chat y comunicación externa en Teams</span><span class="sxs-lookup"><span data-stu-id="c6846-210">Chat / External Communication in Teams</span></span></td>
<td><span data-ttu-id="c6846-211">La comunicación externa (federación) solo está dentro de su propio inquilino a través de su implementación de Skype Empresarial o lync server.</span><span class="sxs-lookup"><span data-stu-id="c6846-211">Internal within your own tenant only, external communication (federation) is via your Skype for Business or Lync server deployment.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c6846-212">Crear y ver reuniones en Teams</span><span class="sxs-lookup"><span data-stu-id="c6846-212">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="c6846-213">Puede crear reuniones internas y externas a través del complemento de Outlook.</span><span class="sxs-lookup"><span data-stu-id="c6846-213">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="c6846-214">La capacidad de marcado RTC y de marcado de salida está disponible con las licencias de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="c6846-214">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="c6846-215">El acceso al calendario de Teams requiere exchange 2016 CU3+ local implementado con exchange híbrido establecido:</span><span class="sxs-lookup"><span data-stu-id="c6846-215">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established:</span></span><br /><span data-ttu-id="c6846-216">
<a href="/exchange/hybrid-deployment/deploy-hybrid">Cree una implementación híbrida con el Asistente para configuración híbrida.</a></span><span class="sxs-lookup"><span data-stu-id="c6846-216">
<a href="/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a></span></span></p>
<p><span data-ttu-id="c6846-217">El administrador puede controlar el complemento de Skype Empresarial Outlook a través del atributo PreferredMeetingProviderForIslandsMode de la directiva de reunión de Teams:<a href="/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy</a>.</span><span class="sxs-lookup"><span data-stu-id="c6846-217">Administrator can control the Skype for Business Outlook add-in via the Teams meeting policy’s PreferredMeetingProviderForIslandsMode attribute:<a href="/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy</a>.</span></span></p> 
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="c6846-218">Características de llamadas</span><span class="sxs-lookup"><span data-stu-id="c6846-218">Calling Features</span></span><br />
<span data-ttu-id="c6846-219">VoIP /RTC en Teams</span><span class="sxs-lookup"><span data-stu-id="c6846-219">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="c6846-220">VoIP internamente para el inquilino está disponible.</span><span class="sxs-lookup"><span data-stu-id="c6846-220">VoIP internally to the tenant is available.</span></span></p>
<p><span data-ttu-id="c6846-221">Los servicios RTC o planes de llamadas no están disponibles hasta que el usuario se mueve a la experiencia solo de Teams.</span><span class="sxs-lookup"><span data-stu-id="c6846-221">PSTN or Calling Plan services are not available until the user is moved to Teams Only experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c6846-222">Colaboración de teams y canales en Teams</span><span class="sxs-lookup"><span data-stu-id="c6846-222">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="c6846-223">Para obtener una experiencia completa, incluidas las características de cumplimiento normativo, es necesario asignar una licencia de SharePoint Online al usuario.</span><span class="sxs-lookup"><span data-stu-id="c6846-223">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="c6846-224">No es necesaria la migración de sitios de SharePoint locales existentes.</span><span class="sxs-lookup"><span data-stu-id="c6846-224">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c6846-225">OneDrive para la Empresa (uso compartido de archivos P2P)</span><span class="sxs-lookup"><span data-stu-id="c6846-225">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="c6846-226">OneDrive para la Empresa requiere que un usuario tenga asignada una licencia de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="c6846-226">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="c6846-227">Sin esta licencia, no será posible compartir archivos por punto.</span><span class="sxs-lookup"><span data-stu-id="c6846-227">Without this license per-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c6846-228">Plataforma de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="c6846-228">Application platform</span></span></td>
<td><span data-ttu-id="c6846-229">Los usuarios podrán usar las aplicaciones designadas disponibles para ellas según las directivas de su empresa.</span><span class="sxs-lookup"><span data-stu-id="c6846-229">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="c6846-230">Más información aquí: <a href="/microsoftteams/admin-settings">Configuración de administración de aplicaciones en Teams</a></span><span class="sxs-lookup"><span data-stu-id="c6846-230">Learn more here: <a href="/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c6846-231">Características de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="c6846-231">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="c6846-232">Las directivas de retención están disponibles.</span><span class="sxs-lookup"><span data-stu-id="c6846-232">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="c6846-233">Se admite la exhibición de documentos electrónicos y la retención legal para el cumplimiento en los mensajes de canal.</span><span class="sxs-lookup"><span data-stu-id="c6846-233">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="c6846-234">Las directivas de prevención de pérdida de datos (DLP) están disponibles.</span><span class="sxs-lookup"><span data-stu-id="c6846-234">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="c6846-235">Conjunto de características completo disponible con Exchange Online; Exchange local admite la mayoría de estas características.</span><span class="sxs-lookup"><span data-stu-id="c6846-235">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="c6846-236">Para obtener una lista completa, vea <a href="/MicrosoftTeams/exchange-teams-interact">Cómo interactúan Exchange y Teams.</a></span><span class="sxs-lookup"><span data-stu-id="c6846-236">For a complete list, see <a href="/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact.</a></span></span></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a><span data-ttu-id="c6846-237">Pasos de habilitación para organizaciones con Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c6846-237">Enablement steps for organizations with Skype for Business Server</span></span>  

1.  <span data-ttu-id="c6846-238">Cumpla los requisitos previos detallados en la sección Empezar aquí anterior.</span><span class="sxs-lookup"><span data-stu-id="c6846-238">Meet pre-requisites detailed in the Start Here section above.</span></span>

2.  <span data-ttu-id="c6846-239">Cambiar el inquilino al modo Islas (para inquilinos aprovisionados después del 1/9/2019, póngase en contacto con el soporte técnico para realizar este cambio)</span><span class="sxs-lookup"><span data-stu-id="c6846-239">Switch tenant into Islands mode (for tenants provisioned AFTER 9/1/2019, please contact support to make this change)</span></span>  
    [<span data-ttu-id="c6846-240">Configurar su coexistencia y la configuración de actualización</span><span class="sxs-lookup"><span data-stu-id="c6846-240">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

3.  <span data-ttu-id="c6846-241">Configurar el espacio empresarial de acuerdo con las directivas de empresa o empresa de su empresa</span><span class="sxs-lookup"><span data-stu-id="c6846-241">Configure your tenant in accordance with your company's business/company policies</span></span>  
    [<span data-ttu-id="c6846-242">Administrar la configuración de Microsoft Teams para su organización</span><span class="sxs-lookup"><span data-stu-id="c6846-242">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)

4.  <span data-ttu-id="c6846-243">Implementar el cliente de Teams</span><span class="sxs-lookup"><span data-stu-id="c6846-243">Deploy the Teams client</span></span>  
    [<span data-ttu-id="c6846-244">Obtener clientes para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c6846-244">Get clients for Teams</span></span>](get-clients.md)

5.   <span data-ttu-id="c6846-245">Impulsar el programa de adopción</span><span class="sxs-lookup"><span data-stu-id="c6846-245">Drive your adoption program</span></span>  
    [<span data-ttu-id="c6846-246">Adoptar Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c6846-246">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)<br/>
    [<span data-ttu-id="c6846-247">Lista de comprobación para el inicio rápido de la adopción de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c6846-247">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="c6846-248">Empezar a planear la mudanza de otras cargas de trabajo a Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="c6846-248">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

7.  <span data-ttu-id="c6846-249">Establecer Skype Empresarial híbrido y seguir las rutas de actualización recomendadas para los servidores de Skype Empresarial y Lync</span><span class="sxs-lookup"><span data-stu-id="c6846-249">Establish Skype for Business hybrid and follow the recommended upgrade paths for Skype for Business and Lync servers</span></span>  
    [<span data-ttu-id="c6846-250">Actualizar de Skype Empresarial local a Teams</span><span class="sxs-lookup"><span data-stu-id="c6846-250">Upgrade from Skype for Business on-premises to Teams</span></span>](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a><span data-ttu-id="c6846-251">Instrucción de cierre</span><span class="sxs-lookup"><span data-stu-id="c6846-251">Closing statement</span></span>

<span data-ttu-id="c6846-252">Microsoft Teams puede ser un habilitador para que su organización pueda reunir a todos los empleados, los trabajadores de la información y los trabajadores de Frontline en una única plataforma.</span><span class="sxs-lookup"><span data-stu-id="c6846-252">Microsoft Teams can be an enabler for your organization to bring all the employees, information workers and Frontline workers, together on a single platform.</span></span> <span data-ttu-id="c6846-253">Puede empezar [hoy](https://products.office.com/microsoft-teams/group-chat-software) mismo.</span><span class="sxs-lookup"><span data-stu-id="c6846-253">You can [get started](https://products.office.com/microsoft-teams/group-chat-software) today.</span></span> <span data-ttu-id="c6846-254">Puedes mantenerte en contacto con todos nuestros últimos anuncios y actualizaciones mensuales de productos [aquí.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)</span><span class="sxs-lookup"><span data-stu-id="c6846-254">You can keep in touch with all our latest announcements and monthly product updates [here](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).</span></span>

<span data-ttu-id="c6846-255">Además, a medida que empresas de todo el mundo administran la situación actual de COVID-19, hemos creado una serie de contenido que le ayudará a usar Teams para el máximo impacto en su organización.</span><span class="sxs-lookup"><span data-stu-id="c6846-255">Additionally, as companies around the world are managing the current COVID-19 situation, we have created a series of content that will help you utilize Teams for the maximum impact in your organization.</span></span>

  - <span data-ttu-id="c6846-256">Nuestro [compromiso con los clientes durante COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span><span class="sxs-lookup"><span data-stu-id="c6846-256">Our [commitment to customers during COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span></span>

  - [<span data-ttu-id="c6846-257">2 semanas después: lo que hemos aprendido sobre el trabajo remoto</span><span class="sxs-lookup"><span data-stu-id="c6846-257">2 weeks in: what we've learned about remote work</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [<span data-ttu-id="c6846-258">Ofrecer reuniones y eventos en línea</span><span class="sxs-lookup"><span data-stu-id="c6846-258">Delivering online meetings and events</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [<span data-ttu-id="c6846-259">Ayudar a las pequeñas y medianas empresas a trabajar de forma remota con Teams</span><span class="sxs-lookup"><span data-stu-id="c6846-259">Helping small and medium-sized businesses work remotely with Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [<span data-ttu-id="c6846-260">Transformación digital de eventos en directo: observaciones de Bob Bejan desde la primera línea</span><span class="sxs-lookup"><span data-stu-id="c6846-260">Digital transformation of live events: Bob Bejan's observations from the frontline</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - <span data-ttu-id="c6846-261">[Las 9 formas principales en que TI de Microsoft permite trabajar de forma remota a sus empleados](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/).</span><span class="sxs-lookup"><span data-stu-id="c6846-261">[The top 9 ways Microsoft IT is enabling remote work for its employees](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)</span></span>

  - [<span data-ttu-id="c6846-262">Trabajar de forma remota, mantenerse seguro: sugerencias para OSC</span><span class="sxs-lookup"><span data-stu-id="c6846-262">Work remotely, stay secure—tips for CISOs</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [<span data-ttu-id="c6846-263">Ayudar a profesores y alumnos a cambiar al aprendizaje remoto</span><span class="sxs-lookup"><span data-stu-id="c6846-263">Helping teachers and students make the switch to remote learning</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [<span data-ttu-id="c6846-264">Mantenerse productivo mientras trabaja de forma remota con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c6846-264">Staying productive while working remotely with Microsoft Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a><span data-ttu-id="c6846-265">Referencia de servicios de soporte técnico</span><span class="sxs-lookup"><span data-stu-id="c6846-265">Support Services reference</span></span>

<span data-ttu-id="c6846-266">Teams se basa en Exchange Online, SharePoint Online, OneDrive para la Empresa y grupos de Microsoft 365 para proporcionar a los usuarios una experiencia de Microsoft 365 u Office 365 totalmente integrada.</span><span class="sxs-lookup"><span data-stu-id="c6846-266">Teams relies on Exchange Online, SharePoint Online, OneDrive for Business and Microsoft 365 Groups to provide your users with a fully integrated Microsoft 365 or Office 365 experience.</span></span> <span data-ttu-id="c6846-267">Como se ha indicado anteriormente, Teams funcionará sin la implementación completa de estos servicios, con capacidades limitadas.</span><span class="sxs-lookup"><span data-stu-id="c6846-267">As noted above, Teams will work without full deploying these services – with limited capabilities.</span></span> <span data-ttu-id="c6846-268">Puede obtener más información sobre Teams y sus requisitos previos aquí: [Bienvenido a Teams.](teams-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c6846-268">You can read more about Teams and its pre-requisites here: [Welcome to Teams](teams-overview.md).</span></span>

<span data-ttu-id="c6846-269">Para obtener información específica sobre cada uno de los servicios enumerados anteriormente, siga los siguientes vínculos:</span><span class="sxs-lookup"><span data-stu-id="c6846-269">For specifics on each of the services listed above, please follow the links below:</span></span>

  - <span data-ttu-id="c6846-270">Exchange Online se usa para las características de calendario y para almacenar mensajes de punto a punto en Teams.</span><span class="sxs-lookup"><span data-stu-id="c6846-270">Exchange Online is used for calendaring features and storing peer to peer messages in Teams.</span></span> <span data-ttu-id="c6846-271">Para obtener más información, lea [Cómo interactúan Exchange y Teams](exchange-teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="c6846-271">To learn more, read [How Exchange and Teams interact](exchange-teams-interact.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c6846-272">Para la interoperabilidad de Teams con Exchange local, debe configurar el nuevo protocolo de autenticación de OAuth de Exchange como se describe en Configurar la autenticación de OAuth entre organizaciones de [Exchange y Exchange Online.](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)</span><span class="sxs-lookup"><span data-stu-id="c6846-272">For Teams interop with Exchange on-premises, you must configure the new Exchange OAuth authentication protocol as described in [Configure OAuth authentication between Exchange and Exchange Online organizations](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span></span>

  - <span data-ttu-id="c6846-273">SharePoint se usa para compartir archivos en canales, mientras que /OneDrive para la Empresa se usa para compartir archivos en chat grupal o 1:1.</span><span class="sxs-lookup"><span data-stu-id="c6846-273">SharePoint is used for file sharing in channels, while /OneDrive for Business is used for file sharing in 1:1 or group chat.</span></span> <span data-ttu-id="c6846-274">Para obtener más información, lea [Cómo interactúan SharePoint Online y OneDrive para la Empresa con Microsoft Teams.](sharepoint-onedrive-interact.md)</span><span class="sxs-lookup"><span data-stu-id="c6846-274">To learn more, read [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

  - <span data-ttu-id="c6846-275">[Los grupos de Microsoft 365](office-365-groups.md) se usan para la creación y administración de equipos y canales.</span><span class="sxs-lookup"><span data-stu-id="c6846-275">[Microsoft 365 Groups](office-365-groups.md) are used for team and channel creation/management.</span></span>


## <a name="related-topics"></a><span data-ttu-id="c6846-276">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c6846-276">Related topics</span></span>

[<span data-ttu-id="c6846-277">Carteles de soluciones de telefonía y arquitectura de TI de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c6846-277">Microsoft Teams IT architecture and telephony solutions posters</span></span>](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[<span data-ttu-id="c6846-278">Planear la conectividad híbrida entre Skype Empresarial Server y Office 365</span><span class="sxs-lookup"><span data-stu-id="c6846-278">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[<span data-ttu-id="c6846-279">Admitir trabajadores remotos con Teams</span><span class="sxs-lookup"><span data-stu-id="c6846-279">Support remote workers using Teams</span></span>](support-remote-work-with-teams.md)

[<span data-ttu-id="c6846-280">Trabajar de forma remota con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c6846-280">Work remotely with Microsoft 365</span></span>](https://aka.ms/remote-work)