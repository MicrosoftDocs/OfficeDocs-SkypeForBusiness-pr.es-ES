---
title: Realizar una investigación de contenido en eDiscovery
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
f1.keywords:
- NOCSH
description: Obtenga información sobre qué hacer cuando necesite realizar una exhibición de datos electrónicos, como cuando necesite enviar toda la información almacenada electrónicamente para procedimientos legales.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 955fbf6ba937ca0fc11270cb58c12a0349d46330
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136690"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="18afa-103">Realizar una investigación de eDiscovery en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="18afa-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>

<span data-ttu-id="18afa-104">Las grandes empresas suelen estar expuestas a un procedimiento legal de alta multa que exige el envío de toda la información almacenada electrónicamente (ESI).</span><span class="sxs-lookup"><span data-stu-id="18afa-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span>

<span data-ttu-id="18afa-105">Todos los equipos 1:1 o chats grupales se registran en el diario de los buzones de los usuarios respectivos, y todos los mensajes de canal estándar se registran en el buzón del grupo que representa al equipo.</span><span class="sxs-lookup"><span data-stu-id="18afa-105">All Teams 1:1 or group chats are journaled through to the respective users' mailboxes, and all standard channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="18afa-106">Los archivos cargados en canales estándar están cubiertos por la funcionalidad de eDiscovery para SharePoint Online y OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="18afa-106">Files uploaded in standard channels are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="18afa-107">eDiscovery de los mensajes y los archivos de los [canales privados](private-channels.md) funcionan de manera diferente que en los canales estándar.</span><span class="sxs-lookup"><span data-stu-id="18afa-107">eDiscovery of messages and files in [private channels](private-channels.md) work differently than in standard channels.</span></span> <span data-ttu-id="18afa-108">Para obtener más información, consulte [eDiscovery of Private Channels](#ediscovery-of-private-channels).</span><span class="sxs-lookup"><span data-stu-id="18afa-108">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

> [!NOTE]
> <span data-ttu-id="18afa-109">En este momento, no admitimos eDiscovery de mensajes instantáneos en escenarios en los que los usuarios invitados son los únicos participantes de una conversación de 1:1 o 1: N.</span><span class="sxs-lookup"><span data-stu-id="18afa-109">At this time, we don't support eDiscovery of chat messages in scenarios where guest users are the only participants in a 1:1 or 1:N chat.</span></span> <span data-ttu-id="18afa-110">Estos tipos de chats también se denominan chats de *invitado a invitado* porque no incluyen usuarios de inquilinos domésticos.</span><span class="sxs-lookup"><span data-stu-id="18afa-110">These types of chats are also called *guest-to-guest* chats because they don't include home tenant users.</span></span>

1. <span data-ttu-id="18afa-111">Para realizar una investigación de eDiscovery con el contenido de Microsoft Teams, revise el paso 1 de [este](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) vínculo.</span><span class="sxs-lookup"><span data-stu-id="18afa-111">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [this](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) link.</span></span>

2. <span data-ttu-id="18afa-112">Los datos de Microsoft Teams aparecerán como mensajes instantáneos o conversaciones en la salida de la exportación de eDiscovery de Excel y puede abrir el archivo PST en Outlook para ver los mensajes después de la exportación.</span><span class="sxs-lookup"><span data-stu-id="18afa-112">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output, and you can open the PST in Outlook to view those messages post export.</span></span>

    <span data-ttu-id="18afa-113">Cuando vea el PST del equipo, tenga en cuenta que todas las conversaciones se guardan en la carpeta chat de equipo en historial de conversaciones.</span><span class="sxs-lookup"><span data-stu-id="18afa-113">When viewing the PST for the Team, note that all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="18afa-114">El título del mensaje se alinea con el equipo y el canal.</span><span class="sxs-lookup"><span data-stu-id="18afa-114">The title of the message aligns to Team and Channel.</span></span> <span data-ttu-id="18afa-115">Desde revisar la imagen a continuación, puede ver este mensaje de Bob que ha expuesto el canal de Project 7 Standard del equipo de especificaciones de fabricación.</span><span class="sxs-lookup"><span data-stu-id="18afa-115">From reviewing the image below, you can see this message from Bob who messaged the Project 7 standard channel of the Manufacturing Specs team.</span></span>

    ![Captura de pantalla de una carpeta de chat de equipo en el buzón de un usuario en Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3. <span data-ttu-id="18afa-117">Para ver los chats privados en el buzón de un usuario, también se encuentran en la carpeta chat de equipo en historial de conversaciones.</span><span class="sxs-lookup"><span data-stu-id="18afa-117">To see private chats in a user's mailbox, they are also located in the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-private-channels"></a><span data-ttu-id="18afa-118">eDiscovery de canales privados</span><span class="sxs-lookup"><span data-stu-id="18afa-118">eDiscovery of private channels</span></span>

<span data-ttu-id="18afa-119">Los registros de los mensajes enviados en un canal privado se entregan en el buzón de todos los miembros del canal privado, en lugar de hacerlo en un buzón de grupo.</span><span class="sxs-lookup"><span data-stu-id="18afa-119">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="18afa-120">Los títulos de los registros tienen un formato que indica desde qué canal privado fueron enviados.</span><span class="sxs-lookup"><span data-stu-id="18afa-120">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="18afa-121">Como cada canal privado tiene su propia colección de sitios de SharePoint que es independiente del sitio de grupo primario, los archivos de un canal privado se administran independientemente del equipo principal.</span><span class="sxs-lookup"><span data-stu-id="18afa-121">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="18afa-122">Teams no admite eDiscovery de un solo canal, de modo que se debe buscar en todo el equipo.</span><span class="sxs-lookup"><span data-stu-id="18afa-122">Teams doesn't support eDiscovery of a single channel, so the whole team must be searched.</span></span> <span data-ttu-id="18afa-123">Para realizar una búsqueda en eDiscovery de contenido en un canal privado, busque en el equipo, la colección de sitios asociada al canal privado (para incluir archivos) y buzones de miembros de canales privados (para incluir mensajes).</span><span class="sxs-lookup"><span data-stu-id="18afa-123">To perform an eDiscovery search of content in a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="18afa-124">Siga estos pasos para identificar los archivos y mensajes de un canal privado para incluirlos en la búsqueda de eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="18afa-124">Use the following steps to identify files and messages in a private channel to include in  your eDiscovery search.</span></span>

### <a name="include-private-channel-files-in-an-ediscovery-search"></a><span data-ttu-id="18afa-125">Incluir archivos de canal privado en una búsqueda de eDiscovery</span><span class="sxs-lookup"><span data-stu-id="18afa-125">Include private channel files in an eDiscovery search</span></span>

<span data-ttu-id="18afa-126">Antes de realizar estos pasos, instale el [Shell de administración de SharePoint Online y conéctese a SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="18afa-126">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="18afa-127">Ejecute lo siguiente para obtener una lista de todas las colecciones de sitios de SharePoint asociadas a los canales privados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="18afa-127">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```

2. <span data-ttu-id="18afa-128">Ejecute el siguiente script de PowerShell para obtener una lista de todas las direcciones URL de la colección de sitios de SharePoint asociadas a los canales privados en el equipo y el identificador del grupo de equipos primario.</span><span class="sxs-lookup"><span data-stu-id="18afa-128">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```

3. <span data-ttu-id="18afa-129">Para cada uno de los IDENTIFICADOres de grupo o equipo, ejecute el siguiente script de PowerShell para identificar todos los sitios de canal privado pertinentes, donde $groupID es el identificador de grupo del equipo.</span><span class="sxs-lookup"><span data-stu-id="18afa-129">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites, where $groupID is the group ID of the team.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a><span data-ttu-id="18afa-130">Incluir mensajes de canal privado en una búsqueda de eDiscovery</span><span class="sxs-lookup"><span data-stu-id="18afa-130">Include private channel messages in an eDiscovery search</span></span>

<span data-ttu-id="18afa-131">Antes de realizar estos pasos, asegúrese de que tiene instalada la [última versión del módulo de PowerShell de Teams](teams-powershell-overview.md) .</span><span class="sxs-lookup"><span data-stu-id="18afa-131">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="18afa-132">Ejecute lo siguiente para obtener una lista de canales privados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="18afa-132">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. <span data-ttu-id="18afa-133">Ejecute lo siguiente para obtener una lista de miembros del canal privado.</span><span class="sxs-lookup"><span data-stu-id="18afa-133">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. <span data-ttu-id="18afa-134">Incluya los buzones de todos los miembros de cada canal privado del equipo como parte de la consulta de búsqueda de eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="18afa-134">Include the mailboxes of all members from each private channel in the team as part of your eDiscovery search query.</span></span>

## <a name="related-topics"></a><span data-ttu-id="18afa-135">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="18afa-135">Related topics</span></span>

- [<span data-ttu-id="18afa-136">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="18afa-136">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
