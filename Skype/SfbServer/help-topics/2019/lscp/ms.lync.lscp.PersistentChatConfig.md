---
title: Configuración de chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3f2891e6-bad3-4a23-a345-b7de4cae3bd9
ROBOTS: NOINDEX, NOFOLLOW
description: La implementación de servidor de Chat persistente puede hospedar muchos salones de Chat persistente simultáneas. Los salones de chat pueden estar organizados jerárquicamente en un conjunto de categorías en el servidor. Cada salón de chat pertenece a una categoría y hereda parte de la configuración de dicha categoría. Esta organización crea una estructura útil para identificar conversaciones según el fin del negocio y, asimismo, facilita la delegación y simplificación de la administración.
ms.openlocfilehash: bac5a19e621f2641b1bdd7b9f8216cdff5e99135
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33891442"
---
# <a name="persistent-chat-configuration"></a><span data-ttu-id="dd22d-106">Configuración de chat persistente</span><span class="sxs-lookup"><span data-stu-id="dd22d-106">Persistent Chat Configuration</span></span>

> [!NOTE] 
> <span data-ttu-id="dd22d-107">Chat persistente está disponible en Skype para Business Server 2015, pero ya no se admite en Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="dd22d-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="dd22d-108">La misma funcionalidad está disponible en los equipos.</span><span class="sxs-lookup"><span data-stu-id="dd22d-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="dd22d-109">Para obtener más información, consulte [actualización de Skype para la empresa a los equipos de Microsoft](https://docs.microsoft.com/MicrosoftTeams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="dd22d-109">For more information, see [Skype for Business to Microsoft Teams upgrade](https://docs.microsoft.com/MicrosoftTeams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="dd22d-110">Si necesita usar chat en grupo, las opciones son migrar los usuarios que requieren esta funcionalidad a los equipos o continuar usando Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="dd22d-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams or continue using Skype for Business Server 2015.</span></span>
