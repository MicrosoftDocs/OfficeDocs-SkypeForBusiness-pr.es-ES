---
title: Realizar una investigación de eDiscovery en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anach
search.appverid: MET150
description: Conozca los pasos que debe seguir cuando necesite realizar una investigación de eDiscovery, como por ejemplo, cuando debe entregar toda la información almacenada electrónicamente para procedimientos legales.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43105db9a4e12d658bf5cf2e9c2c8897fdc918e3
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989795"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="097fc-103">Realizar una investigación de eDiscovery en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="097fc-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>
============================

<span data-ttu-id="097fc-104">Las grandes empresas suelen estar expuestas a un procedimiento legal de alta multa que exige el envío de toda la información almacenada electrónicamente (ESI).</span><span class="sxs-lookup"><span data-stu-id="097fc-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span>

<span data-ttu-id="097fc-p101">Todos los equipos 1:1 o chats grupales se registran en el diario de los buzones de los usuarios respectivos, y todos los mensajes de canal estándar se registran en el buzón del grupo que representa al equipo. Los archivos cargados en canales estándar están cubiertos por la funcionalidad de eDiscovery para SharePoint Online y OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="097fc-p101">All Teams 1:1 or group chats are journaled through to the respective users’ mailboxes, and all standard channel messages are journaled through to the group mailbox representing the team. Files uploaded in standard channels are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="097fc-107">eDiscovery de los mensajes y los archivos de los [canales privados](private-channels.md) funcionan de manera diferente que en los canales estándar.</span><span class="sxs-lookup"><span data-stu-id="097fc-107">eDiscovery of messages and files in [private channels](private-channels.md) work differently than in standard channels.</span></span> <span data-ttu-id="097fc-108">Para obtener más información, consulte [eDiscovery of Private Channels](#ediscovery-of-private-channels).</span><span class="sxs-lookup"><span data-stu-id="097fc-108">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

1.  <span data-ttu-id="097fc-109">Para realizar una investigación de eDiscovery con el contenido de Microsoft Teams, revise el paso 1 de [este](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) vínculo.</span><span class="sxs-lookup"><span data-stu-id="097fc-109">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [this](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) link.</span></span>

2.  <span data-ttu-id="097fc-110">Los datos de Microsoft Teams aparecerán como mensajes instantáneos o conversaciones en la salida de la exportación de eDiscovery de Excel, y puede montar el. PST en Outlook para ver los mensajes después de la exportación.</span><span class="sxs-lookup"><span data-stu-id="097fc-110">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output, and you can mount the .PST in Outlook to view those messages post export.</span></span>

    <span data-ttu-id="097fc-111">Al montar el. PST para el equipo, tenga en cuenta que todas las conversaciones se guardan en la carpeta chat de equipo en historial de conversaciones.</span><span class="sxs-lookup"><span data-stu-id="097fc-111">When mounting the .PST for the Team, note that all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="097fc-112">El título del mensaje se alinea con el equipo y el canal.</span><span class="sxs-lookup"><span data-stu-id="097fc-112">The title of the message aligns to Team and Channel.</span></span> <span data-ttu-id="097fc-113">Desde revisar la imagen a continuación, puede ver este mensaje de Bob que ha expuesto el canal de Project 7 Standard del equipo de especificaciones de fabricación.</span><span class="sxs-lookup"><span data-stu-id="097fc-113">From reviewing the image below, you can see this message from Bob who messaged the Project 7 standard channel of the Manufacturing Specs team.</span></span>

    ![Captura de pantalla de una carpeta de chat de equipo en el buzón de un usuario en Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  <span data-ttu-id="097fc-115">Para ver las conversaciones privadas en el buzón de un usuario, también se encuentran dentro de la carpeta chat de equipo en historial de conversaciones.</span><span class="sxs-lookup"><span data-stu-id="097fc-115">To see private chats in a user’s mailbox, they are also located inside the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-guest-to-guest-chats"></a><span data-ttu-id="097fc-116">eDiscovery de conversaciones de invitado a invitado</span><span class="sxs-lookup"><span data-stu-id="097fc-116">eDiscovery of guest-to-guest chats</span></span>

<span data-ttu-id="097fc-117">Por el momento, en el caso de que solo los invitados participen en una conversación de 1:1 o de 1: N, no admitimos eDiscovery de esos mensajes.</span><span class="sxs-lookup"><span data-stu-id="097fc-117">Presently, for a scenario where only guests are participating in 1:1 or 1:N chat, we don't support eDiscovery of those chat messages.</span></span> 

<span data-ttu-id="097fc-118">Sin un buzón de correo, los chats entre invitados (1xN chats en los que no hay usuarios de inquilinos domésticos) no se indizarán y, como resultado, no se incluirían en eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="097fc-118">Without a mailbox, guest-to-guest chats (1xN chats in which there are no home tenant users) would not be indexed, and as a result, would not be included in eDiscovery.</span></span> <span data-ttu-id="097fc-119">Para facilitar la exhibición de mensajes instantáneos a los chats entre invitados, se crea un buzón de correo basado en la nube (o un buzón de correo fantasma) para almacenar los datos de 1xN.</span><span class="sxs-lookup"><span data-stu-id="097fc-119">To facilitate eDiscovery for guest-to-guest chats, a cloud-based mailbox (or phantom mailbox) is created to store the 1xN data.</span></span> <span data-ttu-id="097fc-120">Una vez que los datos de la conversación de equipos se almacenan en el buzón basado en la nube, están indizados para eDiscovery y la búsqueda de contenido de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="097fc-120">After the Teams chat data is stored in the cloud-based mailbox, it is indexed for eDiscovery and compliance content search.</span></span>

<span data-ttu-id="097fc-121">En la ilustración siguiente se muestra cómo funciona eDiscovery para los chats entre invitados en los que no hay un buzón.</span><span class="sxs-lookup"><span data-stu-id="097fc-121">The following illustration shows how eDiscovery works for guest-to-guest chats in which there isn’t a mailbox.</span></span>

![invitado a invitado: chats con sin buzón de correo](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)

## <a name="ediscovery-of-private-channels"></a><span data-ttu-id="097fc-123">eDiscovery de canales privados</span><span class="sxs-lookup"><span data-stu-id="097fc-123">eDiscovery of private channels</span></span>

<span data-ttu-id="097fc-124">Los registros de los mensajes enviados en un canal privado se entregan en el buzón de todos los miembros del canal privado, en lugar de hacerlo en un buzón de grupo.</span><span class="sxs-lookup"><span data-stu-id="097fc-124">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="097fc-125">El formato de los títulos de los registros indica el canal privado desde el que se enviaron.</span><span class="sxs-lookup"><span data-stu-id="097fc-125">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="097fc-126">Como cada canal privado tiene su propia colección de sitios de SharePoint que es independiente del sitio de grupo primario, los archivos de un canal privado se administran independientemente del equipo principal.</span><span class="sxs-lookup"><span data-stu-id="097fc-126">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="097fc-127">Teams no admite eDiscovery de un solo canal, de modo que se debe buscar en todo el equipo.</span><span class="sxs-lookup"><span data-stu-id="097fc-127">Teams doesn't support eDiscovery of a single channel, so the whole team must be searched.</span></span> <span data-ttu-id="097fc-128">Para realizar una búsqueda en eDiscovery de contenido en un canal privado, busque en el equipo, la colección de sitios asociada al canal privado (para incluir archivos) y buzones de miembros de canales privados (para incluir mensajes).</span><span class="sxs-lookup"><span data-stu-id="097fc-128">To perform an eDiscovery search of content in a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="097fc-129">Siga estos pasos para identificar los archivos y mensajes de un canal privado para incluirlos en la búsqueda de eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="097fc-129">Use the following steps to identify files and messages in a private channel to include in  your eDiscovery search.</span></span>

### <a name="include-private-channel-files-in-an-ediscovery-search"></a><span data-ttu-id="097fc-130">Incluir archivos de canal privado en una búsqueda de eDiscovery</span><span class="sxs-lookup"><span data-stu-id="097fc-130">Include private channel files in an eDiscovery search</span></span>

<span data-ttu-id="097fc-131">Antes de realizar estos pasos, instale el [Shell de administración de SharePoint Online y conéctese a SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="097fc-131">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="097fc-132">Ejecute lo siguiente para obtener una lista de todas las colecciones de sitios de SharePoint asociadas a los canales privados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="097fc-132">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```
2. <span data-ttu-id="097fc-133">Ejecute el siguiente script de PowerShell para obtener una lista de todas las direcciones URL de la colección de sitios de SharePoint asociadas a los canales privados en el equipo y el identificador del grupo de equipos primario.</span><span class="sxs-lookup"><span data-stu-id="097fc-133">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. <span data-ttu-id="097fc-134">Para cada uno de los IDENTIFICADOres de grupo o equipo, ejecute el siguiente script de PowerShell para identificar todos los sitios de canal privado pertinentes, donde $groupID es el identificador de grupo del equipo.</span><span class="sxs-lookup"><span data-stu-id="097fc-134">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites, where $groupID is the group ID of the team.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “e8195240-4a70-4830-9106-80193cf717cb“
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a><span data-ttu-id="097fc-135">Incluir mensajes de canal privado en una búsqueda de eDiscovery</span><span class="sxs-lookup"><span data-stu-id="097fc-135">Include private channel messages in an eDiscovery search</span></span>

<span data-ttu-id="097fc-136">Antes de realizar estos pasos, asegúrese de que tiene instalada la [última versión del módulo de PowerShell de Teams](teams-powershell-overview.md) .</span><span class="sxs-lookup"><span data-stu-id="097fc-136">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="097fc-137">Ejecute lo siguiente para obtener una lista de canales privados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="097fc-137">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. <span data-ttu-id="097fc-138">Ejecute lo siguiente para obtener una lista de miembros del canal privado.</span><span class="sxs-lookup"><span data-stu-id="097fc-138">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. <span data-ttu-id="097fc-139">Incluya los buzones de todos los miembros de cada canal privado del equipo como parte de la consulta de búsqueda de eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="097fc-139">Include the mailboxes of all members from each private channel in the team as part of your eDiscovery search query.</span></span>

## <a name="related-topics"></a><span data-ttu-id="097fc-140">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="097fc-140">Related topics</span></span>

- [<span data-ttu-id="097fc-141">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="097fc-141">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
