---
title: Realizar una investigación de eDiscovery en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Conozca los pasos que debe seguir cuando necesite realizar una investigación de eDiscovery, como por ejemplo, cuando debe entregar toda la información almacenada electrónicamente para procedimientos legales.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 42a9f9cc011d050e540eef3ff87d9cd839cc2819
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37564035"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="64bc4-103">Realizar una investigación de eDiscovery en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="64bc4-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>
============================

<span data-ttu-id="64bc4-104">Las grandes empresas suelen estar expuestas a un procedimiento legal de alta multa que exige el envío de toda la información almacenada electrónicamente (ESI).</span><span class="sxs-lookup"><span data-stu-id="64bc4-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span>

<span data-ttu-id="64bc4-p101">Todos los equipos 1:1 o chats grupales se registran en el diario de los buzones de los usuarios respectivos, y todos los mensajes de canal se registran en el buzón del grupo que representa al equipo. Los archivos cargados están cubiertos por la funcionalidad de eDiscovery para SharePoint Online y OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="64bc4-p101">All Teams 1:1 or group chats are journaled through to the respective users’ mailboxes, and all channel messages are journaled through to the group mailbox representing the team. Files uploaded are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

1.  <span data-ttu-id="64bc4-107">Para realizar una investigación de eDiscovery con el contenido de Microsoft Teams, revise el paso 1 de [este](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) vínculo.</span><span class="sxs-lookup"><span data-stu-id="64bc4-107">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [this](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) link.</span></span>

2.  <span data-ttu-id="64bc4-108">Los datos de Microsoft Teams aparecerán como mensajes instantáneos o conversaciones en la salida de la exportación de eDiscovery de Excel, y puede montar el. PST en Outlook para ver los mensajes después de la exportación.</span><span class="sxs-lookup"><span data-stu-id="64bc4-108">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output, and you can mount the .PST in Outlook to view those messages post export.</span></span>

    <span data-ttu-id="64bc4-p102">Al montar el. PST para el equipo, tenga en cuenta que todas las conversaciones se guardan en la carpeta chat de equipo en historial de conversaciones. El título del mensaje se alinea con el equipo y el canal. Desde revisar la imagen a continuación, puede ver este mensaje de Bob que ha expuesto el canal 7 del equipo de especificaciones de fabricación.</span><span class="sxs-lookup"><span data-stu-id="64bc4-p102">When mounting the .PST for the Team, note that all conversations are kept in the Team Chat folder under Conversation History. The title of the message aligns to Team and Channel. From reviewing the image below, you can see this message from Bob who messaged the Project 7 channel of the Manufacturing Specs team.</span></span>

    ![Captura de pantalla de una carpeta de chat de equipo en el buzón de un usuario en Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  <span data-ttu-id="64bc4-113">Para ver chats privados en el buzón de un usuario, tenga en cuenta que también se encuentran en la carpeta Chat de equipo en Historial de conversaciones.</span><span class="sxs-lookup"><span data-stu-id="64bc4-113">To see private chats in a user’s Mailbox, they are also located inside the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-guest-to-guest-chats"></a><span data-ttu-id="64bc4-114">eDiscovery de conversaciones de invitado a invitado</span><span class="sxs-lookup"><span data-stu-id="64bc4-114">eDiscovery of guest-to-guest chats</span></span>

<span data-ttu-id="64bc4-115">Sin un buzón de correo, los chats entre invitados (1xN chats en los que no hay usuarios de inquilinos domésticos) no se indizarán y, como resultado, no se incluirían en eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="64bc4-115">Without a mailbox, guest-to-guest chats (1xN chats in which there are no home tenant users) would not be indexed, and as a result, would not be included in eDiscovery.</span></span> <span data-ttu-id="64bc4-116">Para facilitar la exhibición de mensajes instantáneos a los chats entre invitados, se crea un buzón de correo basado en la nube (o un buzón de correo fantasma) para almacenar los datos de 1xN.</span><span class="sxs-lookup"><span data-stu-id="64bc4-116">To facilitate eDiscovery for guest-to-guest chats, a cloud-based mailbox (or phantom mailbox) is created to store the 1xN data.</span></span> <span data-ttu-id="64bc4-117">Una vez que los datos de la conversación de equipos se almacenan en el buzón basado en la nube, están indizados para eDiscovery y la búsqueda de contenido de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="64bc4-117">After the Teams chat data is stored in the cloud-based mailbox, it is indexed for eDiscovery and compliance content search.</span></span>

<span data-ttu-id="64bc4-118">En la ilustración siguiente se muestra cómo funciona eDiscovery para los chats entre invitados en los que no hay un buzón.</span><span class="sxs-lookup"><span data-stu-id="64bc4-118">The following illustration shows how eDiscovery works for guest-to-guest chats in which there isn’t a mailbox.</span></span>

![invitado a invitado: chats con sin buzón de correo](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)
