---
title: Usar la traducción de mensajes en línea en Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 10/30/2018
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
ms.openlocfilehash: 2afc1d0374333fdbb0bec9246d04224c6a82f032
ms.sourcegitcommit: afc415ad4d0c2ed013eaf5f68a72418e66734ff0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2018
ms.locfileid: "25898122"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="77cf6-103">Usar la traducción de mensajes en línea en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="77cf6-103">Use inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="77cf6-104">La traducción de mensajes en línea es una característica nueva de Microsoft Teams con la que los usuarios pueden traducir automáticamente los mensajes de Teams en el [idioma](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) que se especifique en su configuración de idioma personal de Office 365.</span><span class="sxs-lookup"><span data-stu-id="77cf6-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="77cf6-105">La traducción de mensajes en línea se está implantando de forma predeterminada en su organización.</span><span class="sxs-lookup"><span data-stu-id="77cf6-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="77cf6-106">Si desea permitir a los usuarios usar esta característica en el cliente de los equipos, debe activar esta configuración.</span><span class="sxs-lookup"><span data-stu-id="77cf6-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on.</span></span>

> [!NOTE]
><span data-ttu-id="77cf6-107">Esta implantación se excluye de suscripciones a Office 365 en nuestros entornos de nube de la Comunidad de Office 365 gubernamentales y Office 365 Alemania.</span><span class="sxs-lookup"><span data-stu-id="77cf6-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="enable-by-using-powershell"></a><span data-ttu-id="77cf6-108">Habilitar mediante el uso de PowerShell</span><span class="sxs-lookup"><span data-stu-id="77cf6-108">Enable by using PowerShell</span></span>

<span data-ttu-id="77cf6-109">Puede activar la característica de traducción de mensaje en línea mediante el uso de la directiva de mensajería.</span><span class="sxs-lookup"><span data-stu-id="77cf6-109">You can turn on the inline message translation feature by using the Messaging Policy.</span></span>

1. <span data-ttu-id="77cf6-110">Activar la directiva mediante el cmdlet [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="77cf6-110">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span>
2. <span data-ttu-id="77cf6-111">La directiva tarda unos minutos que se debe aplicar.</span><span class="sxs-lookup"><span data-stu-id="77cf6-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="77cf6-112">Los usuarios podrían deben cerrar la sesión e iniciar una sesión en los equipos.</span><span class="sxs-lookup"><span data-stu-id="77cf6-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="enable-by-using-the-microsoft-teams--skype-for-business-admin-center"></a><span data-ttu-id="77cf6-113">Habilitar mediante el uso de la Microsoft Teams & Skype para el centro de administración de negocio</span><span class="sxs-lookup"><span data-stu-id="77cf6-113">Enable by using the Microsoft Teams & Skype for Business Admin Center</span></span>

<span data-ttu-id="77cf6-114">En los **equipos de Microsoft & Skype para el centro de administración de negocio**, seleccione **Las directivas de mensajería** de la barra de la izquierda, a continuación, ya sea crear una nueva directiva o editar una directiva existente y establezca la opción de **Permitir a los usuarios para traducir los mensajes** a \*\*en \*\*.</span><span class="sxs-lookup"><span data-stu-id="77cf6-114">In the **Microsoft Teams & Skype for Business Admin Center**, select **Messaging Policies** from the left-hand bar, then either create a new policy or edit an existing policy, and set the **Allow users to translate messages** option to **On**.</span></span>

> [!NOTE]
><span data-ttu-id="77cf6-115">Traducción se realiza mediante el servicio de y entrega al cliente con ningún efecto en el contenido que se capturan en los registros de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="77cf6-115">Translation is done by the service and delivered to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="77cf6-116">Para obtener más información acerca de la traducción, vea [¿Qué es Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span><span class="sxs-lookup"><span data-stu-id="77cf6-116">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>