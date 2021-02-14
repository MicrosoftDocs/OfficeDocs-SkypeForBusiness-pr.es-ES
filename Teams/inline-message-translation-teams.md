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
description: Obtenga información sobre cómo activar la traducción directa en Microsoft Teams mediante el Centro de administración de Microsoft Teams o PowerShell.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 012f2431ec7fb249a2f2e3b963c41166c4649a5c
ms.sourcegitcommit: 2e6b0930645cd97dbd597e9346a6fe1788c6facf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2020
ms.locfileid: "47395389"
---
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="3049e-103">Desactivar la traducción de mensajes en línea en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3049e-103">Turn off inline message translation in Microsoft Teams</span></span>
=================================================

<span data-ttu-id="3049e-104">La traducción de mensajes en línea es una característica [](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) de Microsoft Teams que permite a los usuarios traducir mensajes de Teams al idioma especificado por su configuración de idioma personal.</span><span class="sxs-lookup"><span data-stu-id="3049e-104">Inline message translation is a Microsoft Teams feature that lets users translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings.</span></span>

<span data-ttu-id="3049e-105">La traducción de los mensajes en línea se ofrece de forma predeterminada para su organización.</span><span class="sxs-lookup"><span data-stu-id="3049e-105">Inline message translation is rolled out by default for your organization.</span></span> <span data-ttu-id="3049e-106">No es necesario realizar cambios si desea permitir que los usuarios usen esta característica en el cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="3049e-106">You don't need to make changes if you want to allow users to use this feature within the Teams client.</span></span>

> [!NOTE]
><span data-ttu-id="3049e-107">Esta implementación se excluye de las suscripciones de Office 365 en nuestros entornos de Nube de la comunidad de la administración pública de Office 365 y Office 365 Germany.</span><span class="sxs-lookup"><span data-stu-id="3049e-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-off-inline-message-translation"></a><span data-ttu-id="3049e-108">Usar PowerShell para desactivar la traducción de mensajes en línea</span><span class="sxs-lookup"><span data-stu-id="3049e-108">Use PowerShell to turn off inline message translation</span></span>

<span data-ttu-id="3049e-109">Puede usar la directiva de mensajería para desactivar la traducción de mensajes en línea.</span><span class="sxs-lookup"><span data-stu-id="3049e-109">You can use the messaging policy to turn off the inline message translation.</span></span>

<span data-ttu-id="3049e-110">Desactive la directiva mediante el cmdlet [Set-CsTeamsMessagingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="3049e-110">Turn off the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="3049e-111">La directiva tarda unos minutos en aplicarse.</span><span class="sxs-lookup"><span data-stu-id="3049e-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="3049e-112">Es posible que los usuarios necesiten cerrar sesión y volver a iniciar sesión en Teams.</span><span class="sxs-lookup"><span data-stu-id="3049e-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a><span data-ttu-id="3049e-113">Usar el Centro de administración de Microsoft Teams para desactivar la traducción de mensajes en línea</span><span class="sxs-lookup"><span data-stu-id="3049e-113">Use the Microsoft Teams admin center to turn off inline message translation</span></span>

<span data-ttu-id="3049e-114">En el Centro de  administración de **Microsoft Teams,** seleccione Directivas de mensajería en el panel  de navegación izquierdo, cree una directiva o edite una directiva existente y establezca la opción Traducir mensajes en **Desactivado.**</span><span class="sxs-lookup"><span data-stu-id="3049e-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Translate messages** option to **Off**.</span></span>

> [!NOTE]
> <span data-ttu-id="3049e-115">El servicio realiza la traducción y lo entrega al cliente sin ningún efecto en el contenido capturado en los registros de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="3049e-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="3049e-116">Para obtener más información sobre la traducción, vea [¿Qué es Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)</span><span class="sxs-lookup"><span data-stu-id="3049e-116">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)</span></span>
