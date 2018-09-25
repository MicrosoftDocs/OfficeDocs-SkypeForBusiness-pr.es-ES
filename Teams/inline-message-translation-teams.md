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
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016840"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="b3ea5-103">Usar la traducción de mensajes en línea en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b3ea5-103">Use inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="b3ea5-104">La traducción de mensajes en línea es una característica nueva de Microsoft Teams con la que los usuarios pueden traducir automáticamente los mensajes de Teams en el [idioma](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) que se especifique en su configuración de idioma personal de Office 365.</span><span class="sxs-lookup"><span data-stu-id="b3ea5-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="b3ea5-105">Traducción de mensaje en línea se van a ejecutar de forma predeterminada para la organización.</span><span class="sxs-lookup"><span data-stu-id="b3ea5-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="b3ea5-106">Si desea permitir a los usuarios usar esta característica en el cliente de los equipos, debe activar esta opción de configuración mediante el uso de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b3ea5-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on by using PowerShell.</span></span> <span data-ttu-id="b3ea5-107">Actualmente, esta opción no está disponible en el Microsoft Teams y Skype para el centro de administración de negocio, pero pronto.</span><span class="sxs-lookup"><span data-stu-id="b3ea5-107">Currently, this option is not available in the Microsoft Teams and Skype for Business Admin Center, but will be soon.</span></span>

> [!NOTE]
><span data-ttu-id="b3ea5-108">Este lanzamiento no se incluye en las suscripciones de Office 365 de nuestros entornos de Office 365 Government Community Cloud y Office 365 Germany.</span><span class="sxs-lookup"><span data-stu-id="b3ea5-108">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span> 

## <a name="enable-by-using-powershell"></a><span data-ttu-id="b3ea5-109">Habilitar mediante PowerShell</span><span class="sxs-lookup"><span data-stu-id="b3ea5-109">Enable by using PowerShell</span></span>

<span data-ttu-id="b3ea5-110">La característica de traducción de mensajes en línea se puede activar mediante la directiva de mensajería.</span><span class="sxs-lookup"><span data-stu-id="b3ea5-110">You can turn on the inline message translation feature by using the Messaging Policy.</span></span> 

1. <span data-ttu-id="b3ea5-111">Active la directiva con el cmdlet [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b3ea5-111">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span>
2. <span data-ttu-id="b3ea5-112">La directiva tarda unos minutos que se debe aplicar.</span><span class="sxs-lookup"><span data-stu-id="b3ea5-112">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="b3ea5-113">Los usuarios podrían deben cerrar la sesión e iniciar una sesión en los equipos.</span><span class="sxs-lookup"><span data-stu-id="b3ea5-113">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="enable-by-using-the-teams-admin-center"></a><span data-ttu-id="b3ea5-114">Habilitar mediante el Centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="b3ea5-114">Enable by using the Teams Admin Center</span></span>

<span data-ttu-id="b3ea5-115">La opción para activar la característica de traducción de mensajes en línea mediante el Centro de administración de Teams estará disponible muy pronto.</span><span class="sxs-lookup"><span data-stu-id="b3ea5-115">The option to turn on the inline message translation feature by using the Teams Admin Center is coming soon.</span></span>

> [!NOTE]
><span data-ttu-id="b3ea5-116">Traducción es estrictamente de cliente y no ha capturado ningún efecto en el contenido en los registros de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="b3ea5-116">Translation is strictly client-side and has no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="b3ea5-117">Para obtener más información acerca de la traducción, vea [¿Qué es Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span><span class="sxs-lookup"><span data-stu-id="b3ea5-117">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>