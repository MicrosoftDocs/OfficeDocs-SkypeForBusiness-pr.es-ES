---
title: Realizar una investigación de eDiscovery en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: anach
search.appverid: MET150
description: Conozca los pasos que debe seguir cuando necesite realizar una investigación de eDiscovery, como por ejemplo, cuando debe entregar toda la información almacenada electrónicamente para procedimientos legales.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a903e67417cfb24f388c2d194f5f5136f1224cdd
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25011908"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="47a23-103">Realizar una investigación de eDiscovery en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="47a23-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>
============================

<span data-ttu-id="47a23-104">Las grandes empresas a menudo se exponen en el procedimiento legal alta penalización que exigen el envío de todos los electrónicamente almacenan información (ESI).</span><span class="sxs-lookup"><span data-stu-id="47a23-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span>

<span data-ttu-id="47a23-p101">Todos los equipos de 1:1 o charlas de grupo están registrados en el diario a través de los buzones de los usuarios respectivos y están registrados en el diario a través de para el buzón de correo de grupo que representa el equipo de todos los mensajes del canal. Se tratan los archivos cargados en la funcionalidad de exhibición de documentos electrónicos para SharePoint Online y OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="47a23-p101">All Teams 1:1 or group chats are journaled through to the respective users’ mailboxes, and all channel messages are journaled through to the group mailbox representing the team. Files uploaded are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

1.  <span data-ttu-id="47a23-107">Para realizar una investigación de exhibición de documentos electrónicos con el contenido de Microsoft Teams, revise el paso 1 de [este](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) vínculo.</span><span class="sxs-lookup"><span data-stu-id="47a23-107">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [this](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) link.</span></span>

2.  <span data-ttu-id="47a23-108">Datos de Microsoft Teams aparecerán como mensajería instantánea o las conversaciones de la exhibición de documentos de Excel exportación resultados y puede montar la. PST de Outlook para ver los mensajes post de exportación.</span><span class="sxs-lookup"><span data-stu-id="47a23-108">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output, and you can mount the .PST in Outlook to view those messages post export.</span></span>

    <span data-ttu-id="47a23-109">Al montar la. PST para el equipo, tenga en cuenta que todas las conversaciones se guardan en la carpeta Historial de conversaciones de conversaciones en grupo.</span><span class="sxs-lookup"><span data-stu-id="47a23-109">When mounting the .PST for the Team, note that all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="47a23-110">El título del mensaje se alinea a equipo y canal.</span><span class="sxs-lookup"><span data-stu-id="47a23-110">The title of the message aligns to Team and Channel.</span></span> <span data-ttu-id="47a23-111">En revisión de la imagen que aparece a continuación, puede ver este mensaje de Bob que mensajes del canal 7 de proyecto del equipo de especificaciones de fabricación.</span><span class="sxs-lookup"><span data-stu-id="47a23-111">From reviewing the image below, you can see this message from Bob who messaged the Project 7 channel of the Manufacturing Specs team.</span></span>

    ![Captura de pantalla de una carpeta de conversaciones en grupo en el buzón del usuario en Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  <span data-ttu-id="47a23-113">Para ver chats privados en el buzón de un usuario, tenga en cuenta que también se encuentran en la carpeta Chat de equipo en Historial de conversaciones.</span><span class="sxs-lookup"><span data-stu-id="47a23-113">To see private chats in a user’s Mailbox, they are also located inside the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-guest-to-guest-chats"></a><span data-ttu-id="47a23-114">exhibición de documentos electrónicos de chats de invitado a invitado</span><span class="sxs-lookup"><span data-stu-id="47a23-114">eDiscovery of guest-to-guest chats</span></span>

<span data-ttu-id="47a23-115">Sin un buzón de correo, chats invitado a invitado (en el que no hay ningún usuario particular inquilinos de chats 1xN) no se puede indizar y como resultado, no se incluirá en la exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="47a23-115">Without a mailbox, guest-to-guest chats (1xN chats in which there are no home tenant users) would not be indexed, and as a result, would not be included in eDiscovery.</span></span> <span data-ttu-id="47a23-116">Para facilitar la exhibición de documentos electrónicos para chats de invitado a invitado, se crea un buzón de correo basados en la nube (o buzón fantasma) para almacenar los datos de 1xN.</span><span class="sxs-lookup"><span data-stu-id="47a23-116">To facilitate eDiscovery for guest-to-guest chats, a cloud-based mailbox (or phantom mailbox) is created to store the 1xN data.</span></span> <span data-ttu-id="47a23-117">Después de que los datos de chat de los equipos se almacenan en el buzón de correo basados en la nube, se indizan para la búsqueda de contenido de exhibición de documentos electrónicos y cumplimiento de normas.</span><span class="sxs-lookup"><span data-stu-id="47a23-117">After the Teams chat data is stored in the cloud-based mailbox, it is indexed for eDiscovery and compliance content search.</span></span>

<span data-ttu-id="47a23-118">En la siguiente ilustración se muestra cómo funciona la exhibición de documentos electrónicos para chats de invitado a invitado en el que no hay un buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="47a23-118">The following illustration shows how eDiscovery works for guest-to-guest chats in which there isn’t a mailbox.</span></span>

![guest-to-guest-chats-with-no-Mailbox](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)
