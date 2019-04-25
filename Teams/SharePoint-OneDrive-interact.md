---
title: Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 11/12/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
search.appverid: MET150
description: Conozca cómo SharePoint Online y OneDrive para la Empresa interaccionan con Microsoft Teams (por ejemplo, cómo se almacenan los chats privados) y la relación entre el equipo, el canal y la biblioteca de documentos.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 169008f7af8f52be60c7f15d7a4613f77ed161df
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32226462"
---
<a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="a4f91-103">Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a4f91-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>
=============================================================================

> [!Tip]
> <span data-ttu-id="a4f91-104">Vea la sesión siguiente para obtener información sobre cómo los equipos interactúa con Azure Active Directory (AAD), grupos de Office 365, Exchange, SharePoint y OneDrive para la empresa: [Fundamentos de los equipos de Microsoft](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="a4f91-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Office 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="a4f91-p101">Cada equipo de Microsoft Teams tiene un sitio de grupo en SharePoint Online y cada canal de un equipo tiene una carpeta dentro de la biblioteca de documentos del sitio de grupo predeterminado. Los archivos compartidos en un chat se agregan automáticamente a la biblioteca de documentos y los permisos y opciones de seguridad configurados en SharePonit se reflejan automáticamente en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a4f91-p101">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="a4f91-107">Los archivos de chats privados se almacenan en la carpeta de OneDrive para la Empresa del remitente y se conceden permisos automáticamente a todos los participantes como parte del proceso de compartir archivos.</span><span class="sxs-lookup"><span data-stu-id="a4f91-107">Private chat files are stored in the sender’s OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="a4f91-108">Si los usuarios no están asignados y habilitados con licencias de SharePoint Online, no tienen OneDrive para el almacenamiento de negocio en Office 365.</span><span class="sxs-lookup"><span data-stu-id="a4f91-108">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Office 365.</span></span> <span data-ttu-id="a4f91-109">Uso compartido de archivos seguirán funcionando en canales, pero los usuarios no podrán compartir archivos en chats sin OneDrive para el almacenamiento de negocio en Office 365.</span><span class="sxs-lookup"><span data-stu-id="a4f91-109">File sharing will continue to work in channels, but users won't be able to share files in chats without OneDrive for Business storage in Office 365.</span></span>

<span data-ttu-id="a4f91-110">Al almacenar archivos en la biblioteca de documentos de SharePoint Online y OneDrive para la Empresa, se siguen todas las reglas de cumplimiento configuradas en el nivel de inquilino.</span><span class="sxs-lookup"><span data-stu-id="a4f91-110">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="a4f91-111">No se admite la integración con Sharepoint local para Microsoft Teams en este momento.</span><span class="sxs-lookup"><span data-stu-id="a4f91-111">Integration with Sharepoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="a4f91-112">Este es un ejemplo de las relaciones entre el equipo, el canal y la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="a4f91-112">The following is the example of relationships between team, channel, and document library.</span></span>

<span data-ttu-id="a4f91-p103">Se crea un sitio de SharePoint para cada equipo y la carpeta **Documentos compartidos** es la carpeta predeterminada que se crea para el equipo. Cada canal, incluido el canal **General** (que es un canal predeterminado para cada equipo) tiene una carpeta en **Documentos compartidos**.</span><span class="sxs-lookup"><span data-stu-id="a4f91-p103">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team. Each channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![Diagrama de las carpetas Documentos compartidos de SharePoint Online para un equipo y sus canales de Microsoft Teams.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="a4f91-116">En este momento no es posible reemplazar el sitio de SharePoint predeterminado y la biblioteca de documentos con otro.</span><span class="sxs-lookup"><span data-stu-id="a4f91-116">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="a4f91-117">Nos han comentado que les gustaría, por lo que estamos pensando en esa posibilidad.</span><span class="sxs-lookup"><span data-stu-id="a4f91-117">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="a4f91-118">Revise el [mapa de ruta de Teams](https://aka.ms/teamsroadmap) o [Teams UserVoice](https://aka.ms/TeamsUserVoice) para estar al tanto de las próximas características.</span><span class="sxs-lookup"><span data-stu-id="a4f91-118">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

> [!TIP]
> <span data-ttu-id="a4f91-119">Para agregar una ficha a su equipo que vincula a una página del sitio de SharePoint existente o a la biblioteca de documentos de SharePoint existente:</span><span class="sxs-lookup"><span data-stu-id="a4f91-119">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="a4f91-120">Seleccione el signo más junto a las fichas.</span><span class="sxs-lookup"><span data-stu-id="a4f91-120">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="a4f91-121">Seleccione **Biblioteca de documentos** para una biblioteca de documentos existente o **SharePoint** para una página del sitio de SharePoint existente.</span><span class="sxs-lookup"><span data-stu-id="a4f91-121">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="a4f91-122">Seleccione la biblioteca de documentos o página adecuada.</span><span class="sxs-lookup"><span data-stu-id="a4f91-122">Select the appropriate page or document library.</span></span>

<span data-ttu-id="a4f91-123">Para cada usuario, la carpeta de OneDrive **Archivos de chat de Microsoft Teams** se usa para almacenar todos los archivos compartidos en los chat privados con otros usuarios (1:1 o 1:varios), y los permisos se configuran automáticamente para restringir el acceso sólo a usuarios autorizados.</span><span class="sxs-lookup"><span data-stu-id="a4f91-123">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Diagrama de la carpeta de OneDrive denominada Archivos de chat de Microsoft Teams de los chats de cada usuario.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

<a name="more-information"></a><span data-ttu-id="a4f91-125">Más información</span><span class="sxs-lookup"><span data-stu-id="a4f91-125">More information</span></span>
----------------

<span data-ttu-id="a4f91-126">Para obtener más información acerca del funcionamiento de SharePoint con los equipos, vea [SharePoint y equipos: mejor juntos](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span><span class="sxs-lookup"><span data-stu-id="a4f91-126">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

<span data-ttu-id="a4f91-127">Para obtener más información acerca de la experiencia de invitado en los equipos, lea [¿Qué es la experiencia de invitado como](guest-experience.md).</span><span class="sxs-lookup"><span data-stu-id="a4f91-127">To learn more about the guest experience in Teams, read [What the guest experience is like](guest-experience.md).</span></span>

