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
description: Obtenga información sobre cómo activar la traducción en línea en Microsoft Teams con el Centro de administración de Microsoft Teams o PowerShell.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5c9e34c5e539d32b25259098973e9bfe6795ad7c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120631"
---
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="53f1b-103">Desactivar la traducción de mensajes en línea en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="53f1b-103">Turn off inline message translation in Microsoft Teams</span></span>
=================================================

<span data-ttu-id="53f1b-104">La traducción de mensajes en línea es una característica de Microsoft Teams que permite a los usuarios traducir mensajes de Teams al [idioma](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) especificado por su configuración de idioma personal.</span><span class="sxs-lookup"><span data-stu-id="53f1b-104">Inline message translation is a Microsoft Teams feature that lets users translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings.</span></span>

<span data-ttu-id="53f1b-105">La traducción de mensajes en línea se ha desarrollado de forma predeterminada para su organización.</span><span class="sxs-lookup"><span data-stu-id="53f1b-105">Inline message translation is rolled out by default for your organization.</span></span> <span data-ttu-id="53f1b-106">No es necesario realizar cambios si desea permitir que los usuarios usen esta característica en el cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="53f1b-106">You don't need to make changes if you want to allow users to use this feature within the Teams client.</span></span>

> [!NOTE]
><span data-ttu-id="53f1b-107">Esta implementación se excluye de las suscripciones de Office 365 en nuestros entornos de Office 365 Government Community Cloud y Office 365 Germany.</span><span class="sxs-lookup"><span data-stu-id="53f1b-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-off-inline-message-translation"></a><span data-ttu-id="53f1b-108">Usar PowerShell para desactivar la traducción de mensajes en línea</span><span class="sxs-lookup"><span data-stu-id="53f1b-108">Use PowerShell to turn off inline message translation</span></span>

<span data-ttu-id="53f1b-109">Puede usar la directiva de mensajería para desactivar la traducción de mensajes en línea.</span><span class="sxs-lookup"><span data-stu-id="53f1b-109">You can use the messaging policy to turn off the inline message translation.</span></span>

<span data-ttu-id="53f1b-110">Desactive la directiva con el cmdlet [Set-CsTeamsMessagingPolicy.](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="53f1b-110">Turn off the policy by using the [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="53f1b-111">La directiva tarda unos minutos en aplicarse.</span><span class="sxs-lookup"><span data-stu-id="53f1b-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="53f1b-112">Es posible que los usuarios deba cerrar sesión y volver a iniciar sesión en Teams.</span><span class="sxs-lookup"><span data-stu-id="53f1b-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a><span data-ttu-id="53f1b-113">Usar el Centro de administración de Microsoft Teams para desactivar la traducción de mensajes en línea</span><span class="sxs-lookup"><span data-stu-id="53f1b-113">Use the Microsoft Teams admin center to turn off inline message translation</span></span>

<span data-ttu-id="53f1b-114">En el Centro de  administración de **Microsoft Teams,** seleccione Directivas de mensajería en el panel de navegación izquierdo, cree una nueva directiva o edite una directiva existente y establezca la opción Traducir **mensajes** en **Desactivado.**</span><span class="sxs-lookup"><span data-stu-id="53f1b-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Translate messages** option to **Off**.</span></span>

> [!NOTE]
> <span data-ttu-id="53f1b-115">El servicio realiza la traducción y la entrega al cliente sin ningún efecto en el contenido capturado en los registros de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="53f1b-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="53f1b-116">Para obtener más información sobre la traducción, vea [¿Qué es Microsoft Translator?](/azure/cognitive-services/translator/translator-info-overview)</span><span class="sxs-lookup"><span data-stu-id="53f1b-116">To learn more about translation, see [What is Microsoft Translator?](/azure/cognitive-services/translator/translator-info-overview)</span></span>