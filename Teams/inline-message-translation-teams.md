---
title: Usar la traducción de mensajes en línea en Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/16/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Descubra cómo se usa la traducción en línea en Microsoft Teams.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9097e7421bb65b1a9ce0900df097080a6cfc2023
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296399"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="cce84-103">Usar la traducción de mensajes en línea en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cce84-103">Use inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="cce84-104">La traducción de mensajes en línea es una característica nueva de Microsoft Teams con la que los usuarios pueden traducir automáticamente los mensajes de Teams en el [idioma](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) que se especifique en su configuración de idioma personal de Office 365.</span><span class="sxs-lookup"><span data-stu-id="cce84-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="cce84-105">La traducción de mensajes en línea se está implantando de forma predeterminada en su organización.</span><span class="sxs-lookup"><span data-stu-id="cce84-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="cce84-106">Si quiere que los usuarios puedan usarla dentro del cliente de Teams, debe activar esta opción mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cce84-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on by using PowerShell.</span></span> <span data-ttu-id="cce84-107">En este momento, la opción no está disponible en el Centro de administración de Skype Empresarial y Microsoft Teams, pero lo estará muy pronto.</span><span class="sxs-lookup"><span data-stu-id="cce84-107">Currently, this option is not available in the Microsoft Teams and Skype for Business Admin Center, but will be soon.</span></span>

> [!NOTE]
><span data-ttu-id="cce84-108">Este lanzamiento no se incluye en las suscripciones de Office 365 de nuestros entornos de Office 365 Government Community Cloud y Office 365 Germany.</span><span class="sxs-lookup"><span data-stu-id="cce84-108">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span> 

## <a name="enable-by-using-powershell"></a><span data-ttu-id="cce84-109">Habilitar mediante PowerShell</span><span class="sxs-lookup"><span data-stu-id="cce84-109">Enable by using PowerShell</span></span>

<span data-ttu-id="cce84-110">La característica de traducción de mensajes en línea se puede activar mediante la directiva de mensajería.</span><span class="sxs-lookup"><span data-stu-id="cce84-110">You can turn on the inline message translation feature by using the Messaging Policy.</span></span> 

1. <span data-ttu-id="cce84-111">Active la directiva con el cmdlet [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="cce84-111">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span>
2. <span data-ttu-id="cce84-112">La directiva tardará unos minutos en aplicarse.</span><span class="sxs-lookup"><span data-stu-id="cce84-112">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="cce84-113">Es posible que los usuarios tengan que cerrar la sesión y volver a iniciarla en Teams.</span><span class="sxs-lookup"><span data-stu-id="cce84-113">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="enable-by-using-the-teams-admin-center"></a><span data-ttu-id="cce84-114">Habilitar mediante el Centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="cce84-114">Enable by using the Teams Admin Center</span></span>

<span data-ttu-id="cce84-115">La opción para activar la característica de traducción de mensajes en línea mediante el Centro de administración de Teams estará disponible muy pronto.</span><span class="sxs-lookup"><span data-stu-id="cce84-115">The option to turn on the inline message translation feature by using the Teams Admin Center is coming soon.</span></span>

> [!NOTE]
><span data-ttu-id="cce84-116">La traducción se produce únicamente en el cliente y no afecta al contenido que se captura en los registros de cumplimiento normativo.</span><span class="sxs-lookup"><span data-stu-id="cce84-116">Translation is strictly client-side and has no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="cce84-117">Para obtener más información sobre la traducción, consulte [¿Qué es Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span><span class="sxs-lookup"><span data-stu-id="cce84-117">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>