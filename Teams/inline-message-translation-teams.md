---
title: Activar la traducción de mensajes en línea
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Descubra cómo se usa la traducción en línea en Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4de799959e5e387ad768c3f82e379e464f42191c
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141103"
---
<a name="turn-on-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="c5806-103">Activar la traducción de mensajes en línea en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c5806-103">Turn on inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="c5806-104">La traducción de mensajes en línea es una nueva característica de Microsoft teams que permite a los usuarios traducir los mensajes de los equipos en el [idioma](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) especificado por la configuración de Idioma personal de Office 365.</span><span class="sxs-lookup"><span data-stu-id="c5806-104">Inline message translation is a new Microsoft Teams feature that lets users translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="c5806-105">La traducción de mensajes en línea se está implantando de forma predeterminada en su organización.</span><span class="sxs-lookup"><span data-stu-id="c5806-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="c5806-106">Si desea permitir que los usuarios usen esta característica en el cliente de Teams, debe activar esta configuración.</span><span class="sxs-lookup"><span data-stu-id="c5806-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on.</span></span>

> [!NOTE]
><span data-ttu-id="c5806-107">Este lanzamiento se ha excluido de los planes de Office 365 en la nube de la comunidad de administración pública de Office 365 y en entornos de Office 365 Germany.</span><span class="sxs-lookup"><span data-stu-id="c5806-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-on-inline-message-translation"></a><span data-ttu-id="c5806-108">Usar PowerShell para activar la traducción de mensajes en línea</span><span class="sxs-lookup"><span data-stu-id="c5806-108">Use PowerShell to turn on inline message translation</span></span>

<span data-ttu-id="c5806-109">Puede usar la Directiva de mensajería para activar la traducción de mensajes en línea.</span><span class="sxs-lookup"><span data-stu-id="c5806-109">You can use the messaging policy to turn on the inline message translation.</span></span>

<span data-ttu-id="c5806-110">Active la Directiva con el cmdlet [set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="c5806-110">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="c5806-111">La política tarda unos minutos en aplicarse.</span><span class="sxs-lookup"><span data-stu-id="c5806-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="c5806-112">Es posible que los usuarios tengan que cerrar sesión e iniciarla de nuevo en Teams.</span><span class="sxs-lookup"><span data-stu-id="c5806-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-on-inline-message-translation"></a><span data-ttu-id="c5806-113">Usar el centro de administración de Microsoft Teams para activar la traducción de mensajes en línea</span><span class="sxs-lookup"><span data-stu-id="c5806-113">Use the Microsoft Teams admin center to turn on inline message translation</span></span>

<span data-ttu-id="c5806-114">En el **centro de administración de Microsoft Teams**, seleccione **directivas de mensajería** en el navegación izquierdo y, a continuación, cree una directiva nueva o edite una existente y establezca la opción **permitir que los usuarios traduzcan mensajes** a **activado**.</span><span class="sxs-lookup"><span data-stu-id="c5806-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Allow users to translate messages** option to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="c5806-115">El servicio realiza la traducción y lo entrega al cliente sin ningún efecto en el contenido capturado en los registros de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="c5806-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="c5806-116">Para obtener más información sobre la traducción, consulte [¿Qué es Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span><span class="sxs-lookup"><span data-stu-id="c5806-116">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>