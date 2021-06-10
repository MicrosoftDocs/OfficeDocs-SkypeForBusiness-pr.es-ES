---
title: Experiencia de actualización de aplicaciones en Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo actualizar aplicaciones en Microsoft Teams.
ms.openlocfilehash: b39b831b644b19038b8f4574acf3e5bc5c50d73c
ms.sourcegitcommit: 40f76bc6b5e304faea8516a78f8576ba1cdb7f7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "52337834"
---
# <a name="update-apps-in-microsoft-teams"></a><span data-ttu-id="35923-103">Actualizar aplicaciones en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="35923-103">Update apps in Microsoft Teams</span></span>

<span data-ttu-id="35923-104">En la mayoría de los casos, después de que los desarrolladores de aplicaciones publiquen una actualización de la aplicación, la nueva versión aparecerá automáticamente para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="35923-104">In most cases, after app developers publish an app update, the new version automatically appears for users.</span></span> <span data-ttu-id="35923-105">Sin embargo, hay algunas actualizaciones del manifiesto <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams que</a> requieren la aceptación del usuario para completar:</span><span class="sxs-lookup"><span data-stu-id="35923-105">However, there are some updates to the <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams manifest</a> that require user acceptance to complete:</span></span>

* <span data-ttu-id="35923-106">Se ha agregado o quitado un bot</span><span class="sxs-lookup"><span data-stu-id="35923-106">A bot was added or removed</span></span>
* <span data-ttu-id="35923-107">Se ha cambiado la propiedad "botId" de un bot existente</span><span class="sxs-lookup"><span data-stu-id="35923-107">An existing bot's "botId" property changed</span></span>
* <span data-ttu-id="35923-108">Se ha cambiado la propiedad "isNotificationOnly" de un bot existente</span><span class="sxs-lookup"><span data-stu-id="35923-108">An existing bot's "isNotificationOnly" property changed</span></span>
* <span data-ttu-id="35923-109">La propiedad "supportsFiles" del bot ha cambiado</span><span class="sxs-lookup"><span data-stu-id="35923-109">The bot's "supportsFiles" property changed</span></span>
* <span data-ttu-id="35923-110">Se ha agregado o quitado una extensión de mensajería</span><span class="sxs-lookup"><span data-stu-id="35923-110">A messaging extension was added or removed</span></span>
* <span data-ttu-id="35923-111">Se ha agregado un nuevo conector</span><span class="sxs-lookup"><span data-stu-id="35923-111">A new connector was added</span></span>
* <span data-ttu-id="35923-112">Se ha agregado una nueva pestaña estática</span><span class="sxs-lookup"><span data-stu-id="35923-112">A new static tab was added</span></span>
* <span data-ttu-id="35923-113">Se ha agregado una nueva pestaña configurable</span><span class="sxs-lookup"><span data-stu-id="35923-113">A new configurable tab was added</span></span>
* <span data-ttu-id="35923-114">Se han cambiado las propiedades dentro de "webApplicationInfo"</span><span class="sxs-lookup"><span data-stu-id="35923-114">Properties inside "webApplicationInfo" changed</span></span>

![nueva versión disponible](media/manage-your-custom-apps-update1.png)

![opción de actualización para una aplicación](media/manage-your-custom-apps-update2.png)

> [!NOTE] 
> <span data-ttu-id="35923-117">El proceso de actualización se aplica a todas las actualizaciones de aplicaciones de Microsoft, aplicaciones personalizadas y aplicaciones de terceros.</span><span class="sxs-lookup"><span data-stu-id="35923-117">The update process applies to all app updates for Microsoft apps, custom apps, and third-party apps.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="35923-118">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="35923-118">Related topics</span></span>

[<span data-ttu-id="35923-119">Administrar aplicaciones</span><span class="sxs-lookup"><span data-stu-id="35923-119">Manage apps</span></span>](manage-apps.md)