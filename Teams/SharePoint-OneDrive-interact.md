---
title: "Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: snigdhav
description: "Conozca cómo SharePoint Online y OneDrive para la Empresa interaccionan con Microsoft Teams (por ejemplo, cómo se almacenan los chats privados) y la relación entre el equipo, el canal y la biblioteca de documentos."
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef80cf3f52e9a661bca8694bd679ba18dd4cf04e
ms.sourcegitcommit: 9094c87dec3f8d7d05c7e879d357a6ed428d7cdf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2018
---
<a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="9c656-103">Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9c656-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>
=============================================================================

<span data-ttu-id="9c656-p101">Cada equipo de Microsoft Teams tiene un sitio de grupo en SharePoint Online y cada canal de un equipo tiene una carpeta dentro de la biblioteca de documentos del sitio de grupo predeterminado. Los archivos compartidos en un chat se agregan automáticamente a la biblioteca de documentos y los permisos y opciones de seguridad configurados en SharePonit se reflejan automáticamente en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9c656-p101">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="9c656-106">Los archivos de chats privados se almacenan en la carpeta de OneDrive para la Empresa del remitente y se conceden permisos automáticamente a todos los participantes como parte del proceso de compartir archivos.</span><span class="sxs-lookup"><span data-stu-id="9c656-106">Private chat files are stored in the sender’s OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="9c656-p102">Si no tiene habilitado SharePoint Online en su inquilino, los usuarios de Teams no podrán compartir archivos en los equipos. Los usuarios de chats privados tampoco podrán compartir archivos, porque se necesita OneDrive para la Empresa (que está ligado a la licencia de SharePoint) para esa funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="9c656-p102">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams’ users can't share files in teams. Users in private chat also can't share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="9c656-109">Al almacenar archivos en la biblioteca de documentos de SharePoint Online y OneDrive para la Empresa, se siguen todas las reglas de cumplimiento configuradas en el nivel de inquilino.</span><span class="sxs-lookup"><span data-stu-id="9c656-109">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span>

<span data-ttu-id="9c656-110">Este es un ejemplo de las relaciones entre el equipo, el canal y la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="9c656-110">The following is the example of relationships between team, channel, and document library.</span></span>

<span data-ttu-id="9c656-p103">Se crea un sitio de SharePoint para cada equipo y la carpeta **Documentos compartidos** es la carpeta predeterminada que se crea para el equipo. Cada canal, incluido el canal **General** (que es un canal predeterminado para cada equipo) tiene una carpeta en **Documentos compartidos**.</span><span class="sxs-lookup"><span data-stu-id="9c656-p103">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team. Each channel, including the **General** channel, the default channel for each team, has a folder under the **Shared Documents** folder.</span></span>

![Diagrama de las carpetas Documentos compartidos de SharePoint Online para un equipo y sus canales de Microsoft Teams.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="9c656-114">En este momento no es posible reemplazar el sitio de SharePoint predeterminado y la biblioteca de documentos con otro.</span><span class="sxs-lookup"><span data-stu-id="9c656-114">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="9c656-115">Nos han comentado que les gustaría, por lo que estamos pensando en esa posibilidad.</span><span class="sxs-lookup"><span data-stu-id="9c656-115">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="9c656-116">Revise el [mapa de ruta de Teams](https://aka.ms/teamsroadmap) o [Teams UserVoice](https://aka.ms/TeamsUserVoice) para estar al tanto de las próximas características.</span><span class="sxs-lookup"><span data-stu-id="9c656-116">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

<span data-ttu-id="9c656-117">Para cada usuario, la carpeta de OneDrive **Archivos de chat de Microsoft Teams** se usa para almacenar todos los archivos compartidos en los chat privados con otros usuarios (1:1 o 1:varios), y los permisos se configuran automáticamente para restringir el acceso sólo a usuarios autorizados.</span><span class="sxs-lookup"><span data-stu-id="9c656-117">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Diagrama de la carpeta de OneDrive denominada Archivos de chat de Microsoft Teams de los chats de cada usuario.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)
