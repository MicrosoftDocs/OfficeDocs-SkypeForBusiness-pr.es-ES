---
title: Compartir archivos en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
search.appverid: MET150
description: Microsoft Teams usa la configuración de OneDrive y SharePoint para controlar el uso compartido.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8ddb342af669f710bfd9d05c8b21290ebc6e0451
ms.sourcegitcommit: da87a3c4c781223ab7de2fb539bb0796dc27ea9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2019
ms.locfileid: "35821056"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="006a1-103">Compartir archivos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="006a1-103">Sharing files in Microsoft Teams</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-article.md)]

<span data-ttu-id="006a1-104">Las características de uso compartido de archivos de Teams permiten a los usuarios compartir contenido con otros usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="006a1-104">The file sharing features in Teams let users share content with other Teams users in their organization.</span></span> <span data-ttu-id="006a1-105">El uso compartido en Teams se basa en la configuración establecida en SharePoint y OneDrive, por lo que todo lo que configure para SharePoint y OneDrive controlará también el uso compartido en Teams.</span><span class="sxs-lookup"><span data-stu-id="006a1-105">Sharing in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will control sharing in Teams as well.</span></span>
<span data-ttu-id="006a1-106">![Diagrama que indica cómo funciona el uso compartido de archivos entre Teams y OneDrive para la empresa y SharePoint](media/sharing-files-in-teams-image1.png)</span><span class="sxs-lookup"><span data-stu-id="006a1-106">![Diagram indicating how file sharing works between Teams and OneDrive for Business and SharePoint](media/sharing-files-in-teams-image1.png)</span></span>

<span data-ttu-id="006a1-107">El uso compartido de equipos permite a los usuarios hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="006a1-107">Teams sharing lets users do the following:</span></span>

- <span data-ttu-id="006a1-108">Compartir archivos desde OneDrive.</span><span class="sxs-lookup"><span data-stu-id="006a1-108">Share files from OneDrive.</span></span>

- <span data-ttu-id="006a1-109">Establezca permisos para los archivos que desee compartir con otras personas.</span><span class="sxs-lookup"><span data-stu-id="006a1-109">Set permissions for files they want to share with others.</span></span>

- <span data-ttu-id="006a1-110">Compartir archivos entre equipos.</span><span class="sxs-lookup"><span data-stu-id="006a1-110">Share files across Teams.</span></span>

- <span data-ttu-id="006a1-111">Compartir archivos de la lista de archivos usados recientemente (normalmente, estos son los archivos que los usuarios están más interesados en compartir).</span><span class="sxs-lookup"><span data-stu-id="006a1-111">Share files from their list of recently accessed files (typically, these are the files users are most interested in sharing).</span></span>

- <span data-ttu-id="006a1-112">Mantente dentro de los equipos cuando hacen clic en un nombre de archivo para abrir un archivo.</span><span class="sxs-lookup"><span data-stu-id="006a1-112">Stay within Teams when they click a file name to open a file.</span></span>

<span data-ttu-id="006a1-113">Teams acorta las direcciones URL de SharePoint y las direcciones URL de explorador que apuntan a un archivo.</span><span class="sxs-lookup"><span data-stu-id="006a1-113">Teams shortens long SharePoint URLS and browser URLS that point to a file.</span></span> <span data-ttu-id="006a1-114">Teams usa solo el nombre de archivo para vincular a un archivo.</span><span class="sxs-lookup"><span data-stu-id="006a1-114">Teams uses just the file name to link to a file.</span></span> <span data-ttu-id="006a1-115">Además, la opción **obtener vínculo** se ha cambiado a **Copiar vínculo** para eliminar cualquier confusión que los usuarios podrían tener acerca de conceder acceso a un archivo a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="006a1-115">Additionally, the **Get link** option has been changed to **Copy link** to eliminate any confusion that users might have about giving others access to a file.</span></span>

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a><span data-ttu-id="006a1-116">Configurar el uso compartido en OneDrive y SharePoint</span><span class="sxs-lookup"><span data-stu-id="006a1-116">Configure sharing in OneDrive and SharePoint</span></span>

<span data-ttu-id="006a1-117">Para obtener más información sobre cómo compartir archivos en OneDrive y SharePoint, incluido cómo configurar el uso compartido y cómo activar y desactivar el uso compartido, vea:</span><span class="sxs-lookup"><span data-stu-id="006a1-117">For more information about sharing files in OneDrive and SharePoint, including how to configure sharing and how to turn sharing on and off, see:</span></span>

- <span data-ttu-id="006a1-118">[Información general sobre el uso compartido externo](https://docs.microsoft.com/sharepoint/external-sharing-overview) : describe lo que ocurre cuando los usuarios comparten, en función de lo que estén compartiendo y con quién.</span><span class="sxs-lookup"><span data-stu-id="006a1-118">[External sharing overview](https://docs.microsoft.com/sharepoint/external-sharing-overview) - describes what happens when users share, depending on what they're sharing and with whom.</span></span>

- <span data-ttu-id="006a1-119">[Activar o desactivar el uso compartido externo](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) : describe cómo los administradores globales y de SharePoint pueden cambiar la configuración de uso compartido en el nivel de organización para SharePoint y OneDrive.</span><span class="sxs-lookup"><span data-stu-id="006a1-119">[Turn external sharing on or off](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) - describes how global and SharePoint admins can change their organization-level sharing settings for SharePoint and OneDrive.</span></span>

- <span data-ttu-id="006a1-120">[Cambiar el uso compartido externo de un sitio](https://docs.microsoft.com/sharepoint/change-external-sharing-site) : describe cómo los administradores globales y de SharePoint pueden activar o desactivar el uso compartido externo en un sitio.</span><span class="sxs-lookup"><span data-stu-id="006a1-120">[Change external sharing for a site](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – describes how global and SharePoint admins can turn external sharing on or off for a site.</span></span>

- <span data-ttu-id="006a1-121">[Cambiar el tipo de vínculo predeterminado cuando los usuarios obtienen vínculos para compartir](https://docs.microsoft.com/sharepoint/change-default-sharing-link) : describe cómo establecer el tipo de vínculo predeterminado para que sea más restrictivo.</span><span class="sxs-lookup"><span data-stu-id="006a1-121">[Change the default link type when users get links for sharing](https://docs.microsoft.com/sharepoint/change-default-sharing-link) - describes how to set the default link type so that it is more restrictive.</span></span>

## <a name="more-information"></a><span data-ttu-id="006a1-122">Más información</span><span class="sxs-lookup"><span data-stu-id="006a1-122">More information</span></span>

- [<span data-ttu-id="006a1-123">Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="006a1-123">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

- <span data-ttu-id="006a1-124">[SharePoint y Teams: mejor juntos](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span><span class="sxs-lookup"><span data-stu-id="006a1-124">[SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

- [<span data-ttu-id="006a1-125">Compartir archivos y carpetas de OneDrive</span><span class="sxs-lookup"><span data-stu-id="006a1-125">Share OneDrive files and folders</span></span>](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [<span data-ttu-id="006a1-126">Compartir archivos o carpetas de SharePoint</span><span class="sxs-lookup"><span data-stu-id="006a1-126">Share SharePoint files or folders</span></span>](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)

