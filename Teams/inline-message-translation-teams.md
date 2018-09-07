---
title: Usar la traducción de mensaje en línea en Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/16/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: salilda
localization_priority: Priority
search.appverid: MET150
description: Obtenga información sobre cómo usar la traducción en línea de Microsoft Teams.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb7876d015fb736785fdaab99b1ed71b8e05b9dc
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23855824"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="53982-103">Usar la traducción de mensaje en línea en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="53982-103">Use inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="53982-104">Traducción de mensaje en línea es una característica nueva de Microsoft Teams que permite a los usuarios traducir automáticamente los mensajes de los equipos en el [idioma](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) especificado por su configuración personal de idioma para Office 365.</span><span class="sxs-lookup"><span data-stu-id="53982-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="53982-105">Traducción de mensaje en línea se van a ejecutar de forma predeterminada para la organización.</span><span class="sxs-lookup"><span data-stu-id="53982-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="53982-106">Si desea permitir a los usuarios usar esta característica en el cliente de los equipos, debe activar esta opción de configuración mediante el uso de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="53982-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on by using PowerShell.</span></span> <span data-ttu-id="53982-107">Actualmente, esta opción no está disponible en el Microsoft Teams y Skype para el centro de administración de negocio, pero pronto.</span><span class="sxs-lookup"><span data-stu-id="53982-107">Currently, this option is not available in the Microsoft Teams and Skype for Business Admin Center, but will be soon.</span></span>

> [!NOTE]
><span data-ttu-id="53982-108">Esta implantación se excluye de suscripciones a Office 365 en nuestros entornos de nube de la Comunidad de Office 365 gubernamentales y Office 365 Alemania.</span><span class="sxs-lookup"><span data-stu-id="53982-108">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span> 

## <a name="enable-by-using-powershell"></a><span data-ttu-id="53982-109">Habilitar mediante el uso de PowerShell</span><span class="sxs-lookup"><span data-stu-id="53982-109">Enable by using PowerShell</span></span>

<span data-ttu-id="53982-110">Puede activar la característica de traducción de mensaje en línea mediante el uso de la directiva de mensajería.</span><span class="sxs-lookup"><span data-stu-id="53982-110">You can turn on the inline message translation feature by using the Messaging Policy.</span></span> 

1. <span data-ttu-id="53982-111">Activar la directiva mediante el cmdlet [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="53982-111">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span>
2. <span data-ttu-id="53982-112">La directiva tarda unos minutos que se debe aplicar.</span><span class="sxs-lookup"><span data-stu-id="53982-112">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="53982-113">Los usuarios podrían deben cerrar la sesión e iniciar una sesión en los equipos.</span><span class="sxs-lookup"><span data-stu-id="53982-113">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="enable-by-using-the-teams-admin-center"></a><span data-ttu-id="53982-114">Habilitar mediante el centro de administración de equipos</span><span class="sxs-lookup"><span data-stu-id="53982-114">Enable by using the Teams Admin Center</span></span>

<span data-ttu-id="53982-115">La opción para activar la característica de traducción de mensaje en línea mediante el centro de administración de equipos es muy pronto.</span><span class="sxs-lookup"><span data-stu-id="53982-115">The option to turn on the inline message translation feature by using the Teams Admin Center is coming soon.</span></span>

> [!NOTE]
><span data-ttu-id="53982-116">Traducción es estrictamente de cliente y no ha capturado ningún efecto en el contenido en los registros de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="53982-116">Translation is strictly client-side and has no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="53982-117">Para obtener más información acerca de la traducción, vea [¿Qué es Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span><span class="sxs-lookup"><span data-stu-id="53982-117">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>