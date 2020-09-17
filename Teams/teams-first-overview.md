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
description: Use esta guía para implementar Microsoft Teams como la primera carga de trabajo de Microsoft 365 u Office 365.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2f7acdfb092e74ae5e10e818b4007c4e22762a36
ms.sourcegitcommit: e773823a3f71efb6eee3bcbc928f1fee24c9381c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950866"
---
# <a name="roll-out-microsoft-teams-first"></a><span data-ttu-id="f426b-103">Implementar Microsoft Teams en primer lugar</span><span class="sxs-lookup"><span data-stu-id="f426b-103">Roll out Microsoft Teams First</span></span>

<span data-ttu-id="f426b-104">Microsoft Teams puede ayudar a sus empleados a permanecer en contacto y colaborar entre ellos, especialmente en el momento actual, en el que el trabajo remoto es una realidad de los empleados de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="f426b-104">Microsoft Teams can help your employees stay connected and collaborate with each other, especially in the current unprecedented time where remote work is a reality of employees around the world.</span></span> <span data-ttu-id="f426b-105">Poder chatear, hacer reuniones de video y colaborar en documentos de Office dentro de Teams puede ayudar a que las empresas sigan siendo productivas.</span><span class="sxs-lookup"><span data-stu-id="f426b-105">Being able to chat, do video meetings and collaborate on Office documents within Teams can help companies stay productive.</span></span> <span data-ttu-id="f426b-106">Si es una pequeña empresa, una organización sin ánimo de lucro o de gran tamaño, puede empezar a trabajar con Teams como la primera carga de trabajo de Microsoft 365 u Office 365 Suite antes de implementar cualquier otra aplicación o servicio de Office.</span><span class="sxs-lookup"><span data-stu-id="f426b-106">Whether you are a small business, a non-profit or a large organization, you can get started with Teams as the first workload within Microsoft 365 or Office 365 suite before deploying any other Office app or service.</span></span>

<span data-ttu-id="f426b-107">Este artículo detalla las consideraciones que debe tomar con el método "Team First".</span><span class="sxs-lookup"><span data-stu-id="f426b-107">This article details the considerations you must make with the "Teams First" approach.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f426b-108">Aunque los equipos pueden ser la primera carga de trabajo implementada en la nube de su organización, la implementación de equipos debe formar parte de la estrategia general de implementación en la nube.</span><span class="sxs-lookup"><span data-stu-id="f426b-108">While Teams can be your organization's first cloud deployed workload, deploying Teams should be part of your overall cloud deployment strategy.</span></span>

<span data-ttu-id="f426b-109">Si ya ha implementado otros servicios de Microsoft 365 u Office 365 y Teams es la siguiente carga de trabajo que debe implementar (en lugar de la primera), empiece con [cómo implementar Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="f426b-109">If you have already rolled out other Microsoft 365 or Office 365 services and Teams is your next workload to roll out (instead of the first), start with [How to roll out Teams](How-to-roll-out-teams.md).</span></span>

## <a name="start-here"></a><span data-ttu-id="f426b-110">Empiece aquí</span><span class="sxs-lookup"><span data-stu-id="f426b-110">Start here</span></span>

<span data-ttu-id="f426b-111">Para empezar a usar su primer despliegue de Teams, deberá cumplir con un mínimo de requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="f426b-111">To get started with your Teams First deployment you will need to meet at minimum some pre-requisites.</span></span> <span data-ttu-id="f426b-112">En la siguiente lista se mostrará lo que debe tener en el lugar de su organización antes de que se puedan habilitar los equipos:</span><span class="sxs-lookup"><span data-stu-id="f426b-112">The following list will show what you must have in place for your organization before Teams can be enabled:</span></span>

1.  <span data-ttu-id="f426b-113">Una organización de Microsoft 365 u Office 365 configurada con el nombre de dominio</span><span class="sxs-lookup"><span data-stu-id="f426b-113">A Microsoft 365 or Office 365 organization configured with your domain name</span></span>

2.  <span data-ttu-id="f426b-114">Conectividad de Azure Active Directory (AAD Connect) o solución de sincronización de identidad de nube similar, con todos los atributos obligatorios sincronizados con su espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="f426b-114">Azure Active Directory connectivity (AAD connect) or similar cloud identity sync solution – with all required attributes synched with your tenant</span></span>  
    <span data-ttu-id="f426b-115">Para comprender los atributos sincronizados con AAD Sync, lea [sincronización de Azure ad Connect: atributos sincronizados en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span><span class="sxs-lookup"><span data-stu-id="f426b-115">To understand the attributes synchronized with AAD sync, read [Azure AD Connect sync: Attributes synchronized to Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span></span>

3.  <span data-ttu-id="f426b-116">Licencias de usuario adecuadas asignadas a teams</span><span class="sxs-lookup"><span data-stu-id="f426b-116">Appropriate user licenses assigned for Teams</span></span>  
    <span data-ttu-id="f426b-117">Para comprender las licencias de Teams, lea [Descripción del servicio Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span><span class="sxs-lookup"><span data-stu-id="f426b-117">To understand Teams licensing, read [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

4.  <span data-ttu-id="f426b-118">Red de la organización preparada para Teams</span><span class="sxs-lookup"><span data-stu-id="f426b-118">Organization's network prepared for Teams</span></span>  
    <span data-ttu-id="f426b-119">Para comprender la preparación de la red, lea [preparar la red de su organización para Teams](prepare-network.md).</span><span class="sxs-lookup"><span data-stu-id="f426b-119">To understand network preparation, read [Prepare your organization's network for Teams](prepare-network.md).</span></span>

5.  <span data-ttu-id="f426b-120">Permitir el acceso de red a Exchange, SharePoint y OneDrive para la empresa en Microsoft 365 u Office 365: [office 365 direcciones URL e intervalos de direcciones IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="f426b-120">Allow network access to Exchange, Sharepoint, and OneDrive for Business in Microsoft 365 or Office 365: [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="f426b-121">Los inquilinos creados después del 1 de septiembre de 2019 se aprovisionan en el modo solo de Teams.</span><span class="sxs-lookup"><span data-stu-id="f426b-121">Tenants created after September 1, 2019 are provisioned in Teams Only mode.</span></span>
> 
> [!IMPORTANT]
> <span data-ttu-id="f426b-122">Si ha implementado Skype empresarial Server y se aprovisionó su inquilino después del 1 de septiembre de 2019, póngase en contacto con el soporte técnico para habilitar las capacidades de coexistencia de Teams.</span><span class="sxs-lookup"><span data-stu-id="f426b-122">If you have Skype for Business Server deployed, and your tenant was provisioned AFTER September 1, 2019, please contact support to enable coexistence capabilities for Teams.</span></span> <span data-ttu-id="f426b-123">Asegúrese de que la "Directiva de actualización de toda la organización" está establecida en "modo islas" <span class="underline">antes</span> de asignar licencias de Teams a un usuario.</span><span class="sxs-lookup"><span data-stu-id="f426b-123">Make sure your 'Organization wide upgrade policy' is set to 'Island mode' <span class="underline">before</span> you assign any Teams licenses to a user.</span></span>

## <a name="migration-starting-points"></a><span data-ttu-id="f426b-124">Puntos de partida de migración</span><span class="sxs-lookup"><span data-stu-id="f426b-124">Migration Starting points</span></span>

<span data-ttu-id="f426b-125">Su viaje a Microsoft 365 u Office 365 y las características disponibles en Teams según su punto de partida y la existencia de Skype empresarial local o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f426b-125">Your journey to Microsoft 365 or Office 365 and features available in Teams depending on your starting point and the existence of on premises Skype for Business or Lync server.</span></span> <span data-ttu-id="f426b-126">En las siguientes secciones, se detallan las características básicas y las opciones de configuración, además de los requisitos previos anteriores.</span><span class="sxs-lookup"><span data-stu-id="f426b-126">The following sections will detail basic capabilities and configuration options in addition to the pre-requisites above.</span></span> <span data-ttu-id="f426b-127">Hemos desglosado los escenarios de punto de partida en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="f426b-127">We have broken down the starting point scenarios to the following topics:</span></span>

<span data-ttu-id="f426b-128">**Configuración de equipos de inquilino**: los modos de inquilino y usuario se usan para controlar el comportamiento del destinatario.</span><span class="sxs-lookup"><span data-stu-id="f426b-128">**Tenant Teams Configuration**: Tenant and user modes are used to control the recipient's behavior.</span></span> <span data-ttu-id="f426b-129">Esta configuración se puede asignar en el nivel de espacio empresarial o en el nivel de usuario de una organización.</span><span class="sxs-lookup"><span data-stu-id="f426b-129">These settings can be assigned on the tenant level or the user level in an organization.</span></span> <span data-ttu-id="f426b-130">Para obtener más información, lea [coexistencia con Skype empresarial](coexistence-chat-calls-presence.md).</span><span class="sxs-lookup"><span data-stu-id="f426b-130">To learn more, read [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>

<span data-ttu-id="f426b-131">**Chat/comunicación externa en Teams**: los servicios de chat se refieren a las conversaciones entre usuarios del mismo nivel o chats grupales dentro y organización o externamente a la organización.</span><span class="sxs-lookup"><span data-stu-id="f426b-131">**Chat / External communication in Teams**: Chat services refer to peer to peer or group chat conversations within and organization or externally to the organization.</span></span> <span data-ttu-id="f426b-132">La comunicación externa también se conoce como Federación en Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="f426b-132">External communication is also referred to as federation in Skype for Business.</span></span>

<span data-ttu-id="f426b-133">**Crear y ver reuniones en Teams**: un usuario siempre puede crear reuniones en línea a través del complemento equipos de Outlook y el acceso telefónico PSTN está disponible en todos los escenarios una vez que el usuario tiene licencia.</span><span class="sxs-lookup"><span data-stu-id="f426b-133">**Create and view meetings in Teams**: A user can always create online meetings via the Outlook Teams add-in and PSTN dial-in is available in all scenarios once the user is licensed.</span></span> <span data-ttu-id="f426b-134">Teams y Skype empresarial almacenan información de calendario en el buzón de Exchange del usuario.</span><span class="sxs-lookup"><span data-stu-id="f426b-134">Teams and Skype for Business store calendaring information in the user's Exchange mailbox.</span></span> <span data-ttu-id="f426b-135">El servidor de Exchange local debe ser Exchange Server 2016 CU3 o una versión posterior para que el cliente de Teams pueda interactuar con el buzón del usuario.</span><span class="sxs-lookup"><span data-stu-id="f426b-135">On premises Exchange server must be Exchange Server 2016 CU3 or above for the Teams client to be able to interact with the user's mailbox.</span></span> <span data-ttu-id="f426b-136">Sin acceso al buzón de Exchange el icono de calendario de Teams no aparecerá y su usuario no podrá ver, crear ni modificar reuniones en el cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="f426b-136">Without Exchange mailbox access the Calendar icon in Teams will not appear and they user will not be able to view, create or modify meetings in the Teams client.</span></span>

<span data-ttu-id="f426b-137">**Llamadas a características VoIP/PSTN en Teams: las**llamadas pueden ser de voz a través de IP (VoIP) o de redes de telefonía pública conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="f426b-137">**Calling features VoIP / PSTN in Teams**: Calling can be Voice over IP (VoIP) or Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="f426b-138">La conectividad de VoIP se produce de forma nativa entre los clientes de Teams, mientras que la conectividad RTC se produce cuando un usuario marca un número de teléfono externo.</span><span class="sxs-lookup"><span data-stu-id="f426b-138">VoIP connectivity happens natively between Teams clients, while PSTN connectivity happen when a user dials an outside phone number.</span></span>  

<span data-ttu-id="f426b-139">Teams admite dos tipos de conectividad RTC.</span><span class="sxs-lookup"><span data-stu-id="f426b-139">Teams support two types of PSTN connectivity.</span></span> <span data-ttu-id="f426b-140">Plan de llamadas de Microsoft, cuando Microsoft proporciona una infraestructura de telefonía, como el número de teléfono de un usuario o la configuración de enrutamiento directo, donde el cliente proporciona la conectividad de telefonía a través de un controlador de borde de sesión (SBC) para el usuario de Teams.</span><span class="sxs-lookup"><span data-stu-id="f426b-140">Microsoft Calling Plan, when Microsoft provides telephony infrastructure including the phone number for a user, or Direct Routing configuration, where the customer provides the telephony connectivity over a Session Border Controller (SBC) for the Teams user.</span></span>  
<span data-ttu-id="f426b-141">Para obtener más información, lea [¿qué plan de llamadas es adecuado para usted?](calling-plan-landing-page.md) y [enrutamiento directo del sistema telefónico](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="f426b-141">To learn more, read [Which Calling Plan is right for you?](calling-plan-landing-page.md) and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="f426b-142">**Colaboración entre equipos y canales en Teams**: en Teams, Teams reúne grupos de personas para el trabajo, los proyectos o los intereses comunes.</span><span class="sxs-lookup"><span data-stu-id="f426b-142">**Teams and Channels collaboration in Teams**: In Teams, teams are groups of people brought together for work, projects, or common interests.</span></span> <span data-ttu-id="f426b-143">Los equipos se componen de canales.</span><span class="sxs-lookup"><span data-stu-id="f426b-143">Teams are made up of channels.</span></span> <span data-ttu-id="f426b-144">Cada canal se crea en función de un tema, como "eventos de equipo", un nombre de departamento o simplemente por diversión.</span><span class="sxs-lookup"><span data-stu-id="f426b-144">Each channel is built around a topic, like "Team Events," a department name, or just for fun.</span></span> <span data-ttu-id="f426b-145">Los canales son donde se guardan las reuniones, se tienen conversaciones y se trabaja con los archivos juntos.</span><span class="sxs-lookup"><span data-stu-id="f426b-145">Channels are where you hold meetings, have conversations, and work on files together.</span></span> <span data-ttu-id="f426b-146">Durante la colaboración</span><span class="sxs-lookup"><span data-stu-id="f426b-146">During collaboration</span></span>

<span data-ttu-id="f426b-147">**OneDrive para la empresa (uso compartido de archivos P2P) en Teams**: fuera de los equipos y los canales, los usuarios de equipos pueden compartir archivos de punto a punto mediante OneDrive para la empresa u otros programas de archivos con uso compartido de P2P, como Citrix files, Dropbox, Box y Google Drive.</span><span class="sxs-lookup"><span data-stu-id="f426b-147">**OneDrive for Business (P2P file sharing) in Teams**: Outside of Teams and Channels, Teams users can share files peer-to-peer using OneDrive for business or other P2P sharing file programs such as Citrix Files, DropBox, Box and Google Drive.</span></span> <span data-ttu-id="f426b-148">En el caso de OneDrive para la empresa, un usuario debe tener asignada una licencia de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f426b-148">For OneDrive for business a user must have SharePoint Online license assigned.</span></span>

<span data-ttu-id="f426b-149">**Plataforma de aplicaciones**: las aplicaciones proporcionan herramientas para su organización para obtener más provecho de Teams.</span><span class="sxs-lookup"><span data-stu-id="f426b-149">**Application Platform**: Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="f426b-150">Estas aplicaciones combinan la funcionalidad de las pestañas, las extensiones de mensajería, los conectores y los bots proporcionados por Microsoft, creados por un tercero o por los programadores de su organización.</span><span class="sxs-lookup"><span data-stu-id="f426b-150">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="f426b-151">**Características de seguridad y cumplimiento:** Teams tiene una amplia variedad de información para ayudarle en áreas de cumplimiento, como directivas de retención, protección de pérdida de datos (DLP), eDiscovery y retención legal para canales, chats y archivos, búsqueda de registros de auditoría.</span><span class="sxs-lookup"><span data-stu-id="f426b-151">**Security and Compliance features:** Teams has a wide range of information to help you with compliance areas, including retention policies, Data Loss Protection (DLP), eDiscovery and legal hold for channels, chats and files, audit log search.</span></span> <span data-ttu-id="f426b-152">Para obtener más información, lea [seguridad y cumplimiento en Microsoft Teams](security-compliance-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f426b-152">To learn more, read [Security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="f426b-153">Las características de eDiscovery avanzado requieren licencias de E5.</span><span class="sxs-lookup"><span data-stu-id="f426b-153">Advance eDiscovery features require E5 licensing.</span></span>

<span data-ttu-id="f426b-154">[Compare las opciones de licencia](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span><span class="sxs-lookup"><span data-stu-id="f426b-154">[Compare licensing options](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>

<span data-ttu-id="f426b-155">Lea [cómo interactúan Exchange y Microsoft Teams](exchange-teams-interact.md) para saber qué características de cumplimiento están disponibles en su escenario.</span><span class="sxs-lookup"><span data-stu-id="f426b-155">Read [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) to learn which compliance features are available in your scenario.</span></span>

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a><span data-ttu-id="f426b-156">Organizaciones **<span class="underline">sin</span>** Skype empresarial o Lync Server</span><span class="sxs-lookup"><span data-stu-id="f426b-156">Organizations **<span class="underline">without</span>** Skype for Business or Lync Server</span></span>

<span data-ttu-id="f426b-157">Este punto de partida supone que su organización no utiliza actualmente Skype empresarial o Lync Server, y que Teams será su primera aplicación en Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="f426b-157">This starting point assumes that your organization does not utilize Skype for Business or Lync Server currently and Teams will be your first application in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="f426b-158">En la siguiente tabla, se detallan las capacidades de configuración y de usuario final de los equipos de los servicios básicos.</span><span class="sxs-lookup"><span data-stu-id="f426b-158">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="f426b-159">Elemento</span><span class="sxs-lookup"><span data-stu-id="f426b-159">Item</span></span></th>
<th><span data-ttu-id="f426b-160">Notas</span><span class="sxs-lookup"><span data-stu-id="f426b-160">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f426b-161">Configuración de equipos de inquilino</span><span class="sxs-lookup"><span data-stu-id="f426b-161">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="f426b-162">El modo solo para equipos, todas las características de chat y de llamada están en Teams.</span><span class="sxs-lookup"><span data-stu-id="f426b-162">Teams Only mode, all chat and calling features are in Teams Only.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f426b-163">Chat/comunicación externa en Teams</span><span class="sxs-lookup"><span data-stu-id="f426b-163">Chat / External Communication in Teams</span></span></td>
<td><p><span data-ttu-id="f426b-164">Las comunicaciones internas (intra365 o de Office 365) y chat externo posibles de Teams.</span><span class="sxs-lookup"><span data-stu-id="f426b-164">Internal (intra Microsoft 365 or Office 365 organization) and external chat communication possible from Teams.</span></span></p>
<p><span data-ttu-id="f426b-165"><em>Nota: las entradas DNS deben configurarse para acceso externo.</span><span class="sxs-lookup"><span data-stu-id="f426b-165"><em>Note: DNS entries must be configured for external access.</span></span> <span data-ttu-id="f426b-166">Los registros DNS de Skype empresarial son necesarios incluso si no tiene Skype empresarial local o en Microsoft 365 u Office 365, para permitir la Federación con entornos de Lync y Skype empresarial:</span><span class="sxs-lookup"><span data-stu-id="f426b-166">Skype for Business DNS records are needed even though you don't have Skype for Business on-premises, or in Microsoft 365 or Office 365, to allow federation with Lync and Skype for Business environments:</span></span><br /><span data-ttu-id="f426b-167">
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">Registros del sistema de nombres de dominio externo</a></em></span><span class="sxs-lookup"><span data-stu-id="f426b-167">
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">External Domain Name System records</a></em></span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f426b-168">Crear y ver reuniones en Teams</span><span class="sxs-lookup"><span data-stu-id="f426b-168">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="f426b-169">Puede crear reuniones internas y externas a través del complemento de Outlook.</span><span class="sxs-lookup"><span data-stu-id="f426b-169">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="f426b-170">La función de marcado y salida de llamadas RTC está disponible con las licencias de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="f426b-170">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="f426b-171">Teams Access Calendar requiere Exchange 2016 CU3 + local implementado con Exchange híbrido establecido: <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">crear una implementación híbrida con el Asistente para la configuración híbrida.</a> </span><span class="sxs-lookup"><span data-stu-id="f426b-171">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established: <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a> </span></span></p>
<p><span data-ttu-id="f426b-172">Además de la configuración híbrida de Exchange, establezca la autenticación de OAuth de Exchange: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> configurar la autenticación de OAuth entre Exchange y las organizaciones de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f426b-172">In addition to Exchange hybrid configuration, establish Exchange OAuth authentication: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Configure OAuth authentication between Exchange and Exchange Online organizations".</span></span></p>

</p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f426b-173">Llamadas a características</span><span class="sxs-lookup"><span data-stu-id="f426b-173">Calling Features</span></span><br />
<span data-ttu-id="f426b-174">VoIP/PSTN en Teams</span><span class="sxs-lookup"><span data-stu-id="f426b-174">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="f426b-175">VoIP de forma interna y externa al inquilino está disponible.</span><span class="sxs-lookup"><span data-stu-id="f426b-175">VoIP internally and externally to the tenant is available.</span></span></p>
<p><span data-ttu-id="f426b-176">Los servicios RTC se pueden configurar a través de Microsoft Phone System, además de agregar un plan de llamadas de Microsoft o enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="f426b-176">PSTN services can be configured via Microsoft Phone System, plus adding a Microsoft Calling Plan or Direct Routing.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f426b-177">Colaboración de equipos y canales en Teams</span><span class="sxs-lookup"><span data-stu-id="f426b-177">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="f426b-178">Para obtener una experiencia completa, incluidas las características de cumplimiento, es necesario asignar una licencia de SharePoint Online al usuario.</span><span class="sxs-lookup"><span data-stu-id="f426b-178">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="f426b-179">No es necesario migrar los sitios de SharePoint locales existentes.</span><span class="sxs-lookup"><span data-stu-id="f426b-179">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f426b-180">OneDrive para la empresa (uso compartido de archivos P2P)</span><span class="sxs-lookup"><span data-stu-id="f426b-180">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="f426b-181">OneDrive para la empresa requiere que un usuario tenga asignada una licencia de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f426b-181">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="f426b-182">Sin esta licencia, no será posible compartir archivos de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="f426b-182">Without this license peer-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f426b-183">Plataforma de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="f426b-183">Application platform</span></span></td>
<td><span data-ttu-id="f426b-184">Los usuarios podrán usar las aplicaciones que estén disponibles según las directivas de la empresa.</span><span class="sxs-lookup"><span data-stu-id="f426b-184">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="f426b-185">Más información aquí: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">configuración de administración de aplicaciones en Teams</a></span><span class="sxs-lookup"><span data-stu-id="f426b-185">Learn more here: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f426b-186">Características de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="f426b-186">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="f426b-187">Hay directivas de retención disponibles.</span><span class="sxs-lookup"><span data-stu-id="f426b-187">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="f426b-188">se admite eDiscovery y retención legal para el cumplimiento de los mensajes de canal.</span><span class="sxs-lookup"><span data-stu-id="f426b-188">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="f426b-189">Están disponibles las directivas de prevención de pérdida de datos (DLP).</span><span class="sxs-lookup"><span data-stu-id="f426b-189">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="f426b-190">Conjunto completo de características disponibles con Exchange Online; Exchange local es compatible con la mayoría de estas características.</span><span class="sxs-lookup"><span data-stu-id="f426b-190">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="f426b-191">Para obtener una lista completa, vea <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">cómo interactúan Exchange y Teams</a>.</span><span class="sxs-lookup"><span data-stu-id="f426b-191">For a full list, see <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a>.</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a><span data-ttu-id="f426b-192">Pasos de habilitación para organizaciones sin Skype empresarial o Lync Server</span><span class="sxs-lookup"><span data-stu-id="f426b-192">Enablement steps for organizations without Skype for Business or Lync Server</span></span>

1.  <span data-ttu-id="f426b-193">Conozca los requisitos previos que se detallan en la sección iniciar aquí anterior</span><span class="sxs-lookup"><span data-stu-id="f426b-193">Meet pre-requisites detailed in the Start Here section above</span></span>

2.  <span data-ttu-id="f426b-194">Cambiar el inquilino al modo solo para equipos (solo para los inquilinos existentes): [configurar la coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md).</span><span class="sxs-lookup"><span data-stu-id="f426b-194">Switch tenant into Teams Only mode (for existing tenants only): [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

3.  <span data-ttu-id="f426b-195">Configure su espacio empresarial de acuerdo con las directivas empresariales/de empresa de su empresa: [administrar la configuración de Microsoft Teams para su organización](enable-features-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="f426b-195">Configure your tenant in accordance with your company's business/company policies: [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

4.  <span data-ttu-id="f426b-196">Implementar el cliente de Teams para sus usuarios: [obtener clientes para equipos](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="f426b-196">Deploy the Teams client to your users: [Get clients for Teams](get-clients.md)</span></span>

5.  <span data-ttu-id="f426b-197">Impulsar el programa de adopción</span><span class="sxs-lookup"><span data-stu-id="f426b-197">Drive your adoption program</span></span>  
    [<span data-ttu-id="f426b-198">Adoptar Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f426b-198">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="f426b-199">Lista de comprobación para el inicio rápido de la adopción de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f426b-199">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="f426b-200">Empezar a planificar el movimiento de otras cargas de trabajo a Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="f426b-200">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a><span data-ttu-id="f426b-201">Organizaciones **<span class="underline">con</span>** Skype empresarial o Lync Server</span><span class="sxs-lookup"><span data-stu-id="f426b-201">Organizations **<span class="underline">with</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="f426b-202">Este punto de partida supone que su organización utiliza los servidores de Skype empresarial 2019, 2015 + o Lync 2013 + Server.</span><span class="sxs-lookup"><span data-stu-id="f426b-202">This starting point assumes that your organization utilizes Skype for Business 2019 or 2015+ or Lync 2013+ server on premises.</span></span> <span data-ttu-id="f426b-203">Ya contamos con amplias instrucciones para las organizaciones que migran de servidores locales a equipos y que deben seguirse en estos escenarios.</span><span class="sxs-lookup"><span data-stu-id="f426b-203">We already have extensive guidance for organizations migrating from on premises servers to Teams and it should be followed for these scenarios.</span></span> <span data-ttu-id="f426b-204">Esta guía es específica del escenario en el que Teams es la primera aplicación que se usa en Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="f426b-204">This guidance is specific to the scenario that Teams is the first application you utilize in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="f426b-205">En la siguiente tabla, se detallan las capacidades de configuración y de usuario final de los equipos de los servicios básicos.</span><span class="sxs-lookup"><span data-stu-id="f426b-205">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="f426b-206">Elemento</span><span class="sxs-lookup"><span data-stu-id="f426b-206">Item</span></span></th>
<th><span data-ttu-id="f426b-207">Notas</span><span class="sxs-lookup"><span data-stu-id="f426b-207">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f426b-208">Configuración de equipos de inquilino</span><span class="sxs-lookup"><span data-stu-id="f426b-208">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="f426b-209">Modo islas.</span><span class="sxs-lookup"><span data-stu-id="f426b-209">Islands mode.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f426b-210">Chat/comunicación externa en Teams</span><span class="sxs-lookup"><span data-stu-id="f426b-210">Chat / External Communication in Teams</span></span></td>
<td><span data-ttu-id="f426b-211">Interno dentro de su propio espacio empresarial, la comunicación externa (Federación) se realiza a través de la implementación de Skype empresarial o de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f426b-211">Internal within your own tenant only, external communication (federation) is via your Skype for Business or Lync server deployment.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f426b-212">Crear y ver reuniones en Teams</span><span class="sxs-lookup"><span data-stu-id="f426b-212">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="f426b-213">Puede crear reuniones internas y externas a través del complemento de Outlook.</span><span class="sxs-lookup"><span data-stu-id="f426b-213">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="f426b-214">La función de marcado y salida de llamadas RTC está disponible con las licencias de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="f426b-214">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="f426b-215">Teams Access Calendar requiere Exchange 2016 CU3 + local implementado con Exchange híbrido establecido:</span><span class="sxs-lookup"><span data-stu-id="f426b-215">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established:</span></span><br /><span data-ttu-id="f426b-216">
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Crear una implementación híbrida con el Asistente para la configuración híbrida.</a></span><span class="sxs-lookup"><span data-stu-id="f426b-216">
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a></span></span></p>
<p><span data-ttu-id="f426b-217">El administrador puede controlar el complemento de Outlook para Skype empresarial a través del atributo PreferredMeetingProviderForIslandsMode de la Directiva de reunión de Teams:<a href="https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy</a>.</span><span class="sxs-lookup"><span data-stu-id="f426b-217">Administrator can control the Skype for Business Outlook add-in via the Teams meeting policy’s PreferredMeetingProviderForIslandsMode attribute:<a href="https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy</a>.</span></span></p> 
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="f426b-218">Llamadas a características</span><span class="sxs-lookup"><span data-stu-id="f426b-218">Calling Features</span></span><br />
<span data-ttu-id="f426b-219">VoIP/PSTN en Teams</span><span class="sxs-lookup"><span data-stu-id="f426b-219">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="f426b-220">El VoIP interno del inquilino está disponible.</span><span class="sxs-lookup"><span data-stu-id="f426b-220">VoIP internally to the tenant is available.</span></span></p>
<p><span data-ttu-id="f426b-221">Los servicios de plan de llamadas o RTC no están disponibles hasta que el usuario solo se mueve a la experiencia de Teams.</span><span class="sxs-lookup"><span data-stu-id="f426b-221">PSTN or Calling Plan services are not available until the user is moved to Teams Only experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f426b-222">Colaboración de equipos y canales en Teams</span><span class="sxs-lookup"><span data-stu-id="f426b-222">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="f426b-223">Para obtener una experiencia completa, incluidas las características de cumplimiento, es necesario asignar una licencia de SharePoint Online al usuario.</span><span class="sxs-lookup"><span data-stu-id="f426b-223">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="f426b-224">No es necesario migrar los sitios de SharePoint locales existentes.</span><span class="sxs-lookup"><span data-stu-id="f426b-224">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f426b-225">OneDrive para la empresa (uso compartido de archivos P2P)</span><span class="sxs-lookup"><span data-stu-id="f426b-225">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="f426b-226">OneDrive para la empresa requiere que un usuario tenga asignada una licencia de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f426b-226">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="f426b-227">Sin este uso compartido de archivos de licencia por par no será posible.</span><span class="sxs-lookup"><span data-stu-id="f426b-227">Without this license per-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f426b-228">Plataforma de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="f426b-228">Application platform</span></span></td>
<td><span data-ttu-id="f426b-229">Los usuarios podrán usar las aplicaciones que estén disponibles según las directivas de la empresa.</span><span class="sxs-lookup"><span data-stu-id="f426b-229">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="f426b-230">Más información aquí: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">configuración de administración de aplicaciones en Teams</a></span><span class="sxs-lookup"><span data-stu-id="f426b-230">Learn more here: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f426b-231">Características de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="f426b-231">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="f426b-232">Hay directivas de retención disponibles.</span><span class="sxs-lookup"><span data-stu-id="f426b-232">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="f426b-233">se admite eDiscovery y retención legal para el cumplimiento de los mensajes de canal.</span><span class="sxs-lookup"><span data-stu-id="f426b-233">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="f426b-234">Están disponibles las directivas de prevención de pérdida de datos (DLP).</span><span class="sxs-lookup"><span data-stu-id="f426b-234">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="f426b-235">Conjunto completo de características disponibles con Exchange Online; Exchange local es compatible con la mayoría de estas características.</span><span class="sxs-lookup"><span data-stu-id="f426b-235">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="f426b-236">Para obtener una lista completa, vea <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">cómo interactúan Exchange y Teams.</a></span><span class="sxs-lookup"><span data-stu-id="f426b-236">For a complete list, see <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact.</a></span></span></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a><span data-ttu-id="f426b-237">Pasos de habilitación para las organizaciones con Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f426b-237">Enablement steps for organizations with Skype for Business Server</span></span>  

1.  <span data-ttu-id="f426b-238">Reúna los requisitos previos que se detallan en la sección empezar aquí anterior.</span><span class="sxs-lookup"><span data-stu-id="f426b-238">Meet pre-requisites detailed in the Start Here section above.</span></span>

2.  <span data-ttu-id="f426b-239">Cambiar el inquilino al modo islas (para los inquilinos aprovisionados después de 9/1/2019, póngase en contacto con el soporte técnico para hacer este cambio).</span><span class="sxs-lookup"><span data-stu-id="f426b-239">Switch tenant into Islands mode (for tenants provisioned AFTER 9/1/2019, please contact support to make this change)</span></span>  
    [<span data-ttu-id="f426b-240">Configurar su coexistencia y la configuración de actualización</span><span class="sxs-lookup"><span data-stu-id="f426b-240">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

3.  <span data-ttu-id="f426b-241">Configurar el espacio empresarial de acuerdo con las directivas empresariales y de empresa de su empresa</span><span class="sxs-lookup"><span data-stu-id="f426b-241">Configure your tenant in accordance with your company's business/company policies</span></span>  
    [<span data-ttu-id="f426b-242">Administrar la configuración de Microsoft Teams para su organización</span><span class="sxs-lookup"><span data-stu-id="f426b-242">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)

4.  <span data-ttu-id="f426b-243">Implementar el cliente de Teams</span><span class="sxs-lookup"><span data-stu-id="f426b-243">Deploy the Teams client</span></span>  
    [<span data-ttu-id="f426b-244">Obtener clientes para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f426b-244">Get clients for Teams</span></span>](get-clients.md)

5.   <span data-ttu-id="f426b-245">Impulsar el programa de adopción</span><span class="sxs-lookup"><span data-stu-id="f426b-245">Drive your adoption program</span></span>  
    [<span data-ttu-id="f426b-246">Adoptar Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f426b-246">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)<br/>
    [<span data-ttu-id="f426b-247">Lista de comprobación para el inicio rápido de la adopción de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f426b-247">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="f426b-248">Empezar a planificar el movimiento de otras cargas de trabajo a Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="f426b-248">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

7.  <span data-ttu-id="f426b-249">Establecer una implementación híbrida de Skype empresarial y seguir las rutas de actualización recomendadas para servidores de Skype empresarial y Lync</span><span class="sxs-lookup"><span data-stu-id="f426b-249">Establish Skype for Business hybrid and follow the recommended upgrade paths for Skype for Business and Lync servers</span></span>  
    [<span data-ttu-id="f426b-250">Actualizar de Skype empresarial local a teams</span><span class="sxs-lookup"><span data-stu-id="f426b-250">Upgrade from Skype for Business on-premises to Teams</span></span>](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a><span data-ttu-id="f426b-251">Resumen de cierre</span><span class="sxs-lookup"><span data-stu-id="f426b-251">Closing statement</span></span>

<span data-ttu-id="f426b-252">Microsoft Teams puede ser un habilitador para que su organización reúna a todos los empleados, trabajadores de la información y trabajadores de los Firstline, juntos en una sola plataforma.</span><span class="sxs-lookup"><span data-stu-id="f426b-252">Microsoft Teams can be an enabler for your organization to bring all the employees, information workers and Firstline workers, together on a single platform.</span></span> <span data-ttu-id="f426b-253">Puedes [comenzar](https://products.office.com/microsoft-teams/group-chat-software) hoy mismo.</span><span class="sxs-lookup"><span data-stu-id="f426b-253">You can [get started](https://products.office.com/microsoft-teams/group-chat-software) today.</span></span> <span data-ttu-id="f426b-254">Puedes mantenerte en contacto con los últimos anuncios [y actualizaciones de](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)productos mensuales.</span><span class="sxs-lookup"><span data-stu-id="f426b-254">You can keep in touch with all our latest announcements and monthly product updates [here](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).</span></span>

<span data-ttu-id="f426b-255">Además, como empresas de todo el mundo están administrando la situación actual de COVID-19, hemos creado una serie de contenidos que le ayudarán a usar Teams para obtener el máximo impacto de su organización.</span><span class="sxs-lookup"><span data-stu-id="f426b-255">Additionally, as companies around the world are managing the current COVID-19 situation, we have created a series of content that will help you utilize Teams for the maximum impact in your organization.</span></span>

  - <span data-ttu-id="f426b-256">Nuestro [compromiso con los clientes durante COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span><span class="sxs-lookup"><span data-stu-id="f426b-256">Our [commitment to customers during COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span></span>

  - [<span data-ttu-id="f426b-257">2 semanas en: lo que hemos aprendido sobre el trabajo remoto</span><span class="sxs-lookup"><span data-stu-id="f426b-257">2 weeks in: what we've learned about remote work</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [<span data-ttu-id="f426b-258">Entrega de reuniones y eventos en línea</span><span class="sxs-lookup"><span data-stu-id="f426b-258">Delivering online meetings and events</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [<span data-ttu-id="f426b-259">Ayudar a las pequeñas y medianas empresas a trabajar de forma remota con Teams</span><span class="sxs-lookup"><span data-stu-id="f426b-259">Helping small and medium-sized businesses work remotely with Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [<span data-ttu-id="f426b-260">Transformación digital de eventos en vivo: las observaciones de Bob bejan de la Frontline</span><span class="sxs-lookup"><span data-stu-id="f426b-260">Digital transformation of live events: Bob Bejan's observations from the frontline</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - <span data-ttu-id="f426b-261">[Las 9 formas principales en que TI de Microsoft permite trabajar de forma remota a sus empleados](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/).</span><span class="sxs-lookup"><span data-stu-id="f426b-261">[The top 9 ways Microsoft IT is enabling remote work for its employees](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)</span></span>

  - [<span data-ttu-id="f426b-262">Trabajar de forma remota, mantener la seguridad: consejos para CISOs</span><span class="sxs-lookup"><span data-stu-id="f426b-262">Work remotely, stay secure—tips for CISOs</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [<span data-ttu-id="f426b-263">Ayudar a los profesores y a los estudiantes a cambiar de aprendizaje remoto</span><span class="sxs-lookup"><span data-stu-id="f426b-263">Helping teachers and students make the switch to remote learning</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [<span data-ttu-id="f426b-264">Mantener la productividad mientras trabaja de forma remota con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f426b-264">Staying productive while working remotely with Microsoft Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a><span data-ttu-id="f426b-265">Referencia de servicios de soporte técnico</span><span class="sxs-lookup"><span data-stu-id="f426b-265">Support Services reference</span></span>

<span data-ttu-id="f426b-266">Teams depende de los grupos de Exchange Online, SharePoint Online, OneDrive para la empresa y Microsoft 365 para ofrecer a los usuarios una experiencia de Microsoft 365 o de Office 365 totalmente integrada.</span><span class="sxs-lookup"><span data-stu-id="f426b-266">Teams relies on Exchange Online, SharePoint Online, OneDrive for Business and Microsoft 365 Groups to provide your users with a fully integrated Microsoft 365 or Office 365 experience.</span></span> <span data-ttu-id="f426b-267">Como se indicó anteriormente, Teams trabajará sin la total implementación de estos servicios, con capacidades limitadas.</span><span class="sxs-lookup"><span data-stu-id="f426b-267">As noted above, Teams will work without full deploying these services – with limited capabilities.</span></span> <span data-ttu-id="f426b-268">Puede obtener más información sobre Teams y sus requisitos previos aquí: [Bienvenido a teams](teams-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f426b-268">You can read more about Teams and its pre-requisites here: [Welcome to Teams](teams-overview.md).</span></span>

<span data-ttu-id="f426b-269">Para obtener información específica sobre cada uno de los servicios mencionados anteriormente, sigue los siguientes vínculos:</span><span class="sxs-lookup"><span data-stu-id="f426b-269">For specifics on each of the services listed above, please follow the links below:</span></span>

  - <span data-ttu-id="f426b-270">Exchange Online se usa para características de calendario y para almacenar mensajes de par a par en Teams.</span><span class="sxs-lookup"><span data-stu-id="f426b-270">Exchange Online is used for calendaring features and storing peer to peer messages in Teams.</span></span> <span data-ttu-id="f426b-271">Para obtener más información, lea [cómo interactúan Exchange y Teams](exchange-teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="f426b-271">To learn more, read [How Exchange and Teams interact](exchange-teams-interact.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f426b-272">Para la interoperabilidad de Teams con Exchange local, debe configurar el nuevo protocolo de autenticación OAuth de Exchange según se describe en [configurar la autenticación OAuth entre Exchange y las organizaciones de Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span><span class="sxs-lookup"><span data-stu-id="f426b-272">For Teams interop with Exchange on-premises, you must configure the new Exchange OAuth authentication protocol as described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span></span>

  - <span data-ttu-id="f426b-273">SharePoint se usa para el uso compartido de archivos en canales, mientras que/OneDrive para empresas se usa para compartir archivos en 1:1 o chat grupal.</span><span class="sxs-lookup"><span data-stu-id="f426b-273">SharePoint is used for file sharing in channels, while /OneDrive for Business is used for file sharing in 1:1 or group chat.</span></span> <span data-ttu-id="f426b-274">Para obtener más información, lea [Cómo SharePoint Online y OneDrive para la empresa interactúan con Microsoft Teams](sharepoint-onedrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="f426b-274">To learn more, read [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

  - <span data-ttu-id="f426b-275">Los [grupos de Microsoft 365](office-365-groups.md) se usan para la creación y administración de equipos y canales.</span><span class="sxs-lookup"><span data-stu-id="f426b-275">[Microsoft 365 Groups](office-365-groups.md) are used for team and channel creation/management.</span></span>


## <a name="related-topics"></a><span data-ttu-id="f426b-276">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="f426b-276">Related topics</span></span>

[<span data-ttu-id="f426b-277">Carteles de soluciones de telefonía y arquitectura de TI de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f426b-277">Microsoft Teams IT architecture and telephony solutions posters</span></span>](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[<span data-ttu-id="f426b-278">Planear la conectividad híbrida entre Skype Empresarial Server y Office 365</span><span class="sxs-lookup"><span data-stu-id="f426b-278">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[<span data-ttu-id="f426b-279">Soporte técnico de trabajadores remotos con Teams</span><span class="sxs-lookup"><span data-stu-id="f426b-279">Support remote workers using Teams</span></span>](support-remote-work-with-teams.md)

[<span data-ttu-id="f426b-280">Trabajar de forma remota con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f426b-280">Work remotely with Microsoft 365</span></span>](https://aka.ms/remote-work)
