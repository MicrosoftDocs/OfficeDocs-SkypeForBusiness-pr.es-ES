---
title: Administración de directivas de mensajería
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.messagingpolicies.overview
description: Descubra más cosas sobre las directivas de mensajería y cómo se pueden usar para controlar los mensajes de chats en Teams.
ms.openlocfilehash: 3b360be09f8e35d560b13b40ef25a72a060e6033
ms.sourcegitcommit: 4e6b39e7421ea6eb03c524bb6b8e597c1966bad1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2019
ms.locfileid: "30056590"
---
# <a name="what-are-messaging-policies-in-teams"></a><span data-ttu-id="5ad74-103">¿Cuáles son las directivas de mensajería de Teams?</span><span class="sxs-lookup"><span data-stu-id="5ad74-103">What are Messaging policies in Teams?</span></span>

<span data-ttu-id="5ad74-104">Messaging policies are used to control which chat and channel messaging features are available to users in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5ad74-104">Messaging policies are used to control which chat and channel messaging features are available to users in Microsoft Teams.</span></span> <span data-ttu-id="5ad74-105">You can use the default policy that is created or create one or more custom messaging policies for people in your organization.</span><span class="sxs-lookup"><span data-stu-id="5ad74-105">You can use the default policy that is created or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="5ad74-106">After you create a policy, you will assign it a user or groups of users in your organization.</span><span class="sxs-lookup"><span data-stu-id="5ad74-106">After you create a policy, you will assign it a user or groups of users in your organization.</span></span>

<span data-ttu-id="5ad74-107">Policies can be easily managed in the Teams Admin Center (http://admin.teams.microsoft.com) by logging in with administrator credentials and clicking **Messaging Policies** in the left navigation.</span><span class="sxs-lookup"><span data-stu-id="5ad74-107">Policies can be easily managed in the Teams Admin Center (http://admin.teams.microsoft.com) by logging in with administrator credentials and clicking **Messaging Policies** in the left navigation.</span></span> <span data-ttu-id="5ad74-108">To edit the existing default policy for your organization, select the **Global (Org-wide default)** row and click **Edit**.</span><span class="sxs-lookup"><span data-stu-id="5ad74-108">To edit the existing default policy for your organization, select the **Global (Org-wide default)** row and click **Edit**.</span></span> <span data-ttu-id="5ad74-109">To create a new messaging policy, click **New policy**.</span><span class="sxs-lookup"><span data-stu-id="5ad74-109">To create a new messaging policy, click **New policy**.</span></span>

![Directivas de mensajería en Teams](media/messaging-policies.png)

<span data-ttu-id="5ad74-111">A continuación se describe la configuración disponible para la directiva:</span><span class="sxs-lookup"><span data-stu-id="5ad74-111">The available settings for the policy are described below:</span></span> 

- <span data-ttu-id="5ad74-112">**Los propietarios pueden eliminar los mensajes enviados** Use esta opción para permitir que los propietarios eliminen los mensajes que envían los usuarios en un chat.</span><span class="sxs-lookup"><span data-stu-id="5ad74-112">**Owners can delete sent messages**  Use this setting to let owners delete messages that users send in chat.</span></span>
- <span data-ttu-id="5ad74-113">**Los usuarios pueden eliminar los mensajes enviados** Use esta opción para permitir que los usuarios eliminen los mensajes que envían en un chat.</span><span class="sxs-lookup"><span data-stu-id="5ad74-113">**Users can delete sent messages** Use this setting to let users delete messages that they send in chat.</span></span>
- <span data-ttu-id="5ad74-114">**Los usuarios pueden editar los mensajes enviados** Use esta opción para permitir que los usuarios editen los mensajes que envían en un chat.</span><span class="sxs-lookup"><span data-stu-id="5ad74-114">**Users can edit sent messages** Use this setting to let users edit the messages that they send in chat.</span></span>
- <span data-ttu-id="5ad74-115">**Read receipts** Use this setting to specify whether read receipts are user controlled, enabled for everyone, or disabled.</span><span class="sxs-lookup"><span data-stu-id="5ad74-115">**Read receipts** Use this setting to specify whether read receipts are user controlled, enabled for everyone, or disabled.</span></span>
<span data-ttu-id="5ad74-116"><a name="bkchat"> </a></span><span class="sxs-lookup"><span data-stu-id="5ad74-116"><a name="bkchat"> </a></span></span>

- <span data-ttu-id="5ad74-117">**Chat** Active esta opción si desea que los usuarios de su organización puedan chatear con otras personas con la aplicación de Teams.</span><span class="sxs-lookup"><span data-stu-id="5ad74-117">**Chat**  Turn this setting on if you want users in your organization to be able to use the Teams app to chat with other people.</span></span>
- <span data-ttu-id="5ad74-118">**Use Giphys in conversations**  If you turn this on, users can include Giphys in chat conversations with other people.</span><span class="sxs-lookup"><span data-stu-id="5ad74-118">**Use Giphys in conversations**  If you turn this on, users can include Giphys in chat conversations with other people.</span></span> <span data-ttu-id="5ad74-119">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span><span class="sxs-lookup"><span data-stu-id="5ad74-119">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="5ad74-120">Each Giphy is assigned a content rating.</span><span class="sxs-lookup"><span data-stu-id="5ad74-120">Each Giphy is assigned a content rating.</span></span>
- <span data-ttu-id="5ad74-121">**Clasificación de contenido de Giphy**</span><span class="sxs-lookup"><span data-stu-id="5ad74-121">**Giphy content rating**</span></span> 
    - <span data-ttu-id="5ad74-122">**Sin restricción** Indica que los usuarios pueden insertar todas las imágenes Giphy en los chats, independientemente de la clasificación de contenido que tengan.</span><span class="sxs-lookup"><span data-stu-id="5ad74-122">**No restriction** This means that your users will be able to insert all Giphys in chats regardless of the content rating.</span></span>
    - <span data-ttu-id="5ad74-123">**Moderado** Indica que los usuarios pueden insertar imágenes Giphy en los chats, pero el contenido para adultos estará restringido de forma moderada.</span><span class="sxs-lookup"><span data-stu-id="5ad74-123">**Moderate**  This means that your users will be able to insert Giphys in chats but will be moderately restricted from adult content.</span></span>
    - <span data-ttu-id="5ad74-124">**Estricto** Indica que los usuarios pueden insertar imágenes Giphy en los chats, pero el contenido para adultos estará restringido de forma estricta.</span><span class="sxs-lookup"><span data-stu-id="5ad74-124">**Strict**  This means that your users will be able to insert Giphys in chats but will be strictly restricted from adult content.</span></span>
- <span data-ttu-id="5ad74-125">**Usar Memes en las conversaciones** Si activa esta opción, los usuarios podrán incluir Memes en las conversaciones de chat que mantengan con otras personas.</span><span class="sxs-lookup"><span data-stu-id="5ad74-125">**Use Memes in conversations** If you turn this on, users can include Memes in chat conversations with other people.</span></span> 
- <span data-ttu-id="5ad74-126">**Usar adhesivos en las conversaciones** Si activa esta opción, los usuarios podrán incluir adhesivos en las conversaciones de chat que mantengan con otras personas.</span><span class="sxs-lookup"><span data-stu-id="5ad74-126">**Use Stickers in conversations** If you turn this on, users can include Stickers in chat conversations with other people.</span></span>
- <span data-ttu-id="5ad74-127">**Permitir vistas previas de URL** Use esta opción si desea activar o desactivar la visualización previa automática de direcciones URL en los mensajes.</span><span class="sxs-lookup"><span data-stu-id="5ad74-127">**Allow URL previews** Use this setting to turn automatic URL previewing on or off in messages.</span></span>
- <span data-ttu-id="5ad74-128">**Permitir a los usuarios traducir mensajes** Active esta opción para que los usuarios pueden traducir automáticamente los mensajes de Teams en el idioma que se especifique en su configuración de idioma personal de Office 365.</span><span class="sxs-lookup"><span data-stu-id="5ad74-128">**Allow users to translate messages** Turn this setting on to let users automatically translate Teams messages into the language specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="5ad74-129">If you have created a custom Messaging policy, it will only be active for a user if that policy is assigned to a user.</span><span class="sxs-lookup"><span data-stu-id="5ad74-129">If you have created a custom Messaging policy, it will only be active for a user if that policy is assigned to a user.</span></span>  <span data-ttu-id="5ad74-130">To assign a custom policy to a user in the Teams Admin Center, click **Users** in the left navigation, select the user you want to assign the policy to, and then choose **Edit** under **Assigned Policies**.</span><span class="sxs-lookup"><span data-stu-id="5ad74-130">To assign a custom policy to a user in the Teams Admin Center, click **Users** in the left navigation, select the user you want to assign the policy to, and then choose **Edit** under **Assigned Policies**.</span></span>

### <a name="related-topics"></a><span data-ttu-id="5ad74-131">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="5ad74-131">Related topics</span></span>
[<span data-ttu-id="5ad74-132">Directivas de reuniones en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5ad74-132">Meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
