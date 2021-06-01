---
title: Establecer los idiomas de operador automático para audioconferencias en Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Vea cómo seleccionar los idiomas operador automático de audio conferencia para un número de audioconferencia en Skype for Business Online.
ms.openlocfilehash: 714312989bc3898fea2ed0d335fed8f5f2eebbb3
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237026"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a><span data-ttu-id="7c623-103">Establecer los idiomas de operador automático para audioconferencias en Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7c623-103">Set auto attendant languages for Audio Conferencing in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> <span data-ttu-id="7c623-104">Para obtener información acerca de cómo establecer el idioma de operador automático en Microsoft Teams, vea [Establecer idiomas de operador automático para audioconferencias en Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).</span><span class="sxs-lookup"><span data-stu-id="7c623-104">For information about setting the auto attendant language in Microsoft Teams, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).</span></span>

<span data-ttu-id="7c623-105">El operador automático de audioconferencias de Skype for Business puede saludar a los autores de llamadas de audioconferencias en un número de diferentes idiomas cuando se unan a una reunión.</span><span class="sxs-lookup"><span data-stu-id="7c623-105">The Audio Conferencing auto attendant for Skype for Business can greet audio callers in a number of different languages when they join a meeting.</span></span>
  
<span data-ttu-id="7c623-106">Elija un idioma principal y hasta cuatro idiomas secundarios.</span><span class="sxs-lookup"><span data-stu-id="7c623-106">Choose one primary language and up to four secondary languages.</span></span> <span data-ttu-id="7c623-107">El idioma principal que establezca se usará primero y los idiomas secundarios los usará el operador automático en el orden que seleccione.</span><span class="sxs-lookup"><span data-stu-id="7c623-107">The primary language that you set will be used first and the secondary languages will be used by the auto-attendant in order that you select.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="7c623-108">Solo puede cambiar los idiomas de los números de audioconferencia que son de la categoría Dedicado.</span><span class="sxs-lookup"><span data-stu-id="7c623-108">You can only change the languages of audio conferencing numbers that are of the Dedicated category.</span></span> <span data-ttu-id="7c623-109">Los idiomas del número de audioconferencia compartida no se pueden cambiar.</span><span class="sxs-lookup"><span data-stu-id="7c623-109">The languages of Shared audio conferencing number can't be changed.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a><span data-ttu-id="7c623-110">Configurar la conferencia de idiomas de operador automático</span><span class="sxs-lookup"><span data-stu-id="7c623-110">Set the conferencing auto attendant languages</span></span>

<span data-ttu-id="7c623-111">Debe ser administrador [global o administrador Skype Empresarial](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) [para](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) realizar este paso.</span><span class="sxs-lookup"><span data-stu-id="7c623-111">You must be a [global admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) or [Skype for Business admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform this step.</span></span>
    
1. <span data-ttu-id="7c623-112">En el **Skype Empresarial de administración**, en el panel de navegación izquierdo, vaya a Portal **heredado.**</span><span class="sxs-lookup"><span data-stu-id="7c623-112">In the **Skype for Business admin center**, in the left navigation, go to **Legacy portal**.</span></span> <span data-ttu-id="7c623-113">Una vez en el portal heredado, seleccione **Audioconferencia y,** a continuación, haga clic en **Puente de Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="7c623-113">Once in the legacy portal, select **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
2. <span data-ttu-id="7c623-114">Seleccione el número de teléfono de audioconferencia de la lista y, en el panel Acción, haga clic **en Establecer idiomas.**</span><span class="sxs-lookup"><span data-stu-id="7c623-114">Select the audio conferencing phone number from the list, and in the Action pane, click **Set languages**.</span></span> <span data-ttu-id="7c623-115">Solo es posible cambiar los idiomas de los números de audioconferencia dedicados.</span><span class="sxs-lookup"><span data-stu-id="7c623-115">It is only possible to change the languages of Dedicated audio conferencing numbers.</span></span>  
    
3. <span data-ttu-id="7c623-116">En la **página Establecer idiomas,** haga clic en **la lista Idioma** principal para ver la lista completa de idiomas disponibles.</span><span class="sxs-lookup"><span data-stu-id="7c623-116">On the **Set languages** page, click the **Primary language** list to view the complete list of available languages.</span></span> <span data-ttu-id="7c623-117">Si es necesario, haga clic en cada una de las listas **idiomas secundarios** para seleccionar el idioma secundario.</span><span class="sxs-lookup"><span data-stu-id="7c623-117">If you need to, click each of the **Secondary languages** lists to select secondary language.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7c623-118">Se enumeran el idioma principal y los secundarios que son compatibles.</span><span class="sxs-lookup"><span data-stu-id="7c623-118">The primary and secondary languages that are supported are listed.</span></span> <span data-ttu-id="7c623-119">El orden en que los seleccione en las listas será el orden de los idiomas presentados a los autores de llamadas.</span><span class="sxs-lookup"><span data-stu-id="7c623-119">The order in which you select them in the lists will be the order of the languages presented to callers.</span></span> 
  
4. <span data-ttu-id="7c623-120">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="7c623-120">Click **Save**.</span></span>
    
## <a name="want-else-should-i-know"></a><span data-ttu-id="7c623-121">¿Qué más debo saber?</span><span class="sxs-lookup"><span data-stu-id="7c623-121">Want else should I know?</span></span>

- <span data-ttu-id="7c623-122">Para ver la lista de los idiomas admitidos para audioconferencia, vea [Idiomas admitidos en audioconferencia](/MicrosoftTeams/audio-conferencing-supported-languages).</span><span class="sxs-lookup"><span data-stu-id="7c623-122">To see the list of supported languages for Audio Conferencing, see [Audio Conferencing supported languages](/MicrosoftTeams/audio-conferencing-supported-languages).</span></span>
    
- <span data-ttu-id="7c623-123">Los idiomas se pueden establecer para números de teléfono dedicados, pero no para compartidos.</span><span class="sxs-lookup"><span data-stu-id="7c623-123">Languages can be set for dedicated but not for shared phone numbers.</span></span>
    
- <span data-ttu-id="7c623-124">Para ver una lista de países o regiones en los que las audioconferencias en Microsoft 365 [](phone-numbers-for-audio-conferencing.md)o Office 365 que usan Microsoft como proveedor están disponibles, vea Teléfono números de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="7c623-124">To see a list of countries/regions in which Audio Conferencing in Microsoft 365 or Office 365 using Microsoft as the provider is available, see [Phone numbers for Audio Conferencing](phone-numbers-for-audio-conferencing.md).</span></span>
    
## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="7c623-125">¿Desea usar Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="7c623-125">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="7c623-126">Para automatizar este paso, puede usar los [cmdlets Set-CsOnlineDialInConferencingServiceNumber](/powershell/module/skype/Set-CsOnlineDialInConferencingServiceNumber) y [Get-CsOnlineDialInConferencingLanguagesSupported.](/powershell/module/skype/Get-CsOnlineDialInConferencingLanguagesSupported)</span><span class="sxs-lookup"><span data-stu-id="7c623-126">To automate this step, you can use the [Set-CsOnlineDialInConferencingServiceNumber](/powershell/module/skype/Set-CsOnlineDialInConferencingServiceNumber) and [Get-CsOnlineDialInConferencingLanguagesSupported](/powershell/module/skype/Get-CsOnlineDialInConferencingLanguagesSupported) cmdlets.</span></span>
  
<span data-ttu-id="7c623-127">Para obtener más información, vea [Usar Windows PowerShell para realizar tareas comunes Skype Empresarial administración en línea](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="7c623-127">To learn more, see [Using Windows PowerShell to do common Skype for Business Online management tasks](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="7c623-128">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="7c623-128">Related topics</span></span>

[<span data-ttu-id="7c623-129">Pruebe o compre Audioconferencia en Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="7c623-129">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
