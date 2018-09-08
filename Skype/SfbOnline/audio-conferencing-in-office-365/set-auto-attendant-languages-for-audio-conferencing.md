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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Vea cómo seleccionar los idiomas operador automático de audio conferencia para un número de audioconferencia en Skype for Business Online.
ms.openlocfilehash: f7b7357d38941ba8d7e1f586f32daa8e02b29012
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882213"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a><span data-ttu-id="0c053-103">Establecer los idiomas de operador automático para audioconferencias en Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="0c053-103">Set auto attendant languages for Audio Conferencing in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="0c053-104">Para obtener información acerca de cómo establecer el idioma de operador automático en Microsoft Teams, vea [Establecer idiomas de operador automático para audioconferencias en Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).</span><span class="sxs-lookup"><span data-stu-id="0c053-104">For information about setting the auto attendant language in Microsoft Teams, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).</span></span>

<span data-ttu-id="0c053-105">El operador automático de audioconferencias de Skype for Business puede saludar a los autores de llamadas de audioconferencias en un número de diferentes idiomas cuando se unan a una reunión.</span><span class="sxs-lookup"><span data-stu-id="0c053-105">The Audio Conferencing auto attendant for Skype for Business can greet audio callers in a number of different languages when they join a meeting.</span></span>
  
<span data-ttu-id="0c053-106">Elija un idioma principal y hasta cuatro idiomas secundarios.</span><span class="sxs-lookup"><span data-stu-id="0c053-106">Choose one primary language and up to four secondary languages.</span></span> <span data-ttu-id="0c053-107">El idioma principal que ha configurado en primer lugar se va a usar y los idiomas secundarios utilizará el operador automático de forma que seleccione.</span><span class="sxs-lookup"><span data-stu-id="0c053-107">The primary language that you set will be used first and the secondary languages will be used by the auto-attendant in order that you select.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="0c053-108">Puede configurar los idiomas en sólo los números de teléfono de acceso nacional de audio.</span><span class="sxs-lookup"><span data-stu-id="0c053-108">You can configure the languages on domestic audio access phone numbers only.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a><span data-ttu-id="0c053-109">Configurar la conferencia de idiomas de operador automático</span><span class="sxs-lookup"><span data-stu-id="0c053-109">Set the conferencing auto attendant languages</span></span>

<span data-ttu-id="0c053-110">Debe ser un [administrador global de Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) o [administrador de Skype for Business](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) para llevar a cabo este paso.</span><span class="sxs-lookup"><span data-stu-id="0c053-110">You must be an [Office 365 global admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) or [Skype for Business admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform this step.</span></span>
    
1. <span data-ttu-id="0c053-111">En el **centro de administración de Skype for Business**, en la navegación izquierda, vaya a **Audioconferencia** y a continuación haga clic en **Puente de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="0c053-111">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
2. <span data-ttu-id="0c053-112">Seleccione el número de teléfono de conferencia de audio de la lista y, en el panel de acciones, haga clic en **conjunto de idiomas**.</span><span class="sxs-lookup"><span data-stu-id="0c053-112">Select the audio conferencing phone number from the list, and in the Action pane, click **Set languages**.</span></span> 
    
3. <span data-ttu-id="0c053-113">En la página **conjunto de idiomas** , haga clic en la lista **idioma principal** para ver la lista completa de idiomas disponibles.</span><span class="sxs-lookup"><span data-stu-id="0c053-113">On the **Set languages** page, click the **Primary language** list to view the complete list of available languages.</span></span> <span data-ttu-id="0c053-114">Si necesita, haga clic en cada una de las listas de **idiomas secundarios** para seleccionar idioma secundario.</span><span class="sxs-lookup"><span data-stu-id="0c053-114">If you need to, click each of the **Secondary languages** lists to select secondary language.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0c053-115">Se enumeran el idioma principal y los secundarios que son compatibles.</span><span class="sxs-lookup"><span data-stu-id="0c053-115">The primary and secondary languages that are supported are listed.</span></span> <span data-ttu-id="0c053-116">El orden en que los seleccione en las listas de será el orden de los idiomas que se presentan a los autores de llamadas.</span><span class="sxs-lookup"><span data-stu-id="0c053-116">The order in which you select them in the lists will be the order of the languages presented to callers.</span></span> 
  
4. <span data-ttu-id="0c053-117">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0c053-117">Click **Save**.</span></span>
    
## <a name="want-else-should-i-know"></a><span data-ttu-id="0c053-118">¿Qué más debo saber?</span><span class="sxs-lookup"><span data-stu-id="0c053-118">Want else should I know?</span></span>

- <span data-ttu-id="0c053-119">Para ver la lista de los idiomas admitidos para audioconferencia, vea [Idiomas admitidos en audioconferencia](/MicrosoftTeams/audio-conferencing-supported-languages).</span><span class="sxs-lookup"><span data-stu-id="0c053-119">To see the list of supported languages for Audio Conferencing, see [Audio Conferencing supported languages](/MicrosoftTeams/audio-conferencing-supported-languages).</span></span>
    
- <span data-ttu-id="0c053-120">Los idiomas se pueden establecer para números de teléfono dedicados, pero no para compartidos.</span><span class="sxs-lookup"><span data-stu-id="0c053-120">Languages can be set for dedicated but not for shared phone numbers.</span></span>
    
- <span data-ttu-id="0c053-121">Para ver una lista de países o regiones en la que está disponible la audioconferencia en Office 365 con Microsoft como proveedor, vea [Números de teléfono para audioconferencias](phone-numbers-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="0c053-121">To see a list of countries/regions in which Audio Conferencing in Office 365 using Microsoft as the provider is available, see [Phone numbers for Audio Conferencing](phone-numbers-for-audio-conferencing.md).</span></span>
    
## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="0c053-122">¿Desea usar Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="0c053-122">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="0c053-123">Para automatizar este paso, puede usar los cmdlets [Set-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) y [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) .</span><span class="sxs-lookup"><span data-stu-id="0c053-123">To automate this step, you can use the [Set-CsOnlineDialInConferencingServiceNumber ](https://go.microsoft.com/fwlink/?LinkId=617689) and [Get-CsOnlineDialInConferencingLanguagesSupported ](https://go.microsoft.com/fwlink/?LinkId=617684) cmdlets.</span></span>
  
<span data-ttu-id="0c053-124">Para obtener más información, vea [Uso de Windows PowerShell para hacer Skype comunes para las tareas de administración en línea de negocio](https://go.microsoft.com/fwlink/?LinkId=525038)</span><span class="sxs-lookup"><span data-stu-id="0c053-124">To learn more, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="0c053-125">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="0c053-125">Related topics</span></span>

[<span data-ttu-id="0c053-126">Probar o comprar Audioconferencia en Office 365</span><span class="sxs-lookup"><span data-stu-id="0c053-126">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
