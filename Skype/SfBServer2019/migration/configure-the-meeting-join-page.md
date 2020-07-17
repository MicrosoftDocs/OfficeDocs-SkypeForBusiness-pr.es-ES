---
title: Configurar la página para unirse a la reunión
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Cuando un usuario hace clic en un vínculo de reunión en una convocatoria de reunión, la página de participación en la reunión detecta el cliente que ya está instalado en el equipo del usuario. Si un cliente ya está instalado, ese cliente se abre y se une a la reunión. Si un cliente no está instalado, se abre de forma predeterminada la aplicación Web.
ms.openlocfilehash: a7bb0983438708bbc0d30cd527eb494491c3cbf2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754030"
---
# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="a0928-105">Configurar la página para unirse a la reunión</span><span class="sxs-lookup"><span data-stu-id="a0928-105">Configure the meeting join page</span></span>

<span data-ttu-id="a0928-106">Cuando un usuario hace clic en un vínculo de reunión en una convocatoria de reunión, la página de participación en la reunión detecta el cliente que ya está instalado en el equipo del usuario.</span><span class="sxs-lookup"><span data-stu-id="a0928-106">When a user clicks a meeting link in a meeting request, the meeting join page detects which client is already installed on the user's computer.</span></span> <span data-ttu-id="a0928-107">Si un cliente ya está instalado, ese cliente se abre y se une a la reunión.</span><span class="sxs-lookup"><span data-stu-id="a0928-107">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="a0928-108">Si un cliente no está instalado, se abre de forma predeterminada la aplicación Web.</span><span class="sxs-lookup"><span data-stu-id="a0928-108">If a client is not installed, by default the Web App opens.</span></span>
  
<span data-ttu-id="a0928-109">Puede modificar el comportamiento de la página de participación en la reunión si desea permitir que los usuarios se unan a reuniones.</span><span class="sxs-lookup"><span data-stu-id="a0928-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings.</span></span> <span data-ttu-id="a0928-110">Estas opciones de configuración se han quitado del panel de control, pero puede configurarlas mediante el cmdlet CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="a0928-110">These configuration options have been removed from the Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="a0928-111">**Parámetros de CsWebServiceConfiguration de la página para unirse a la reunión**</span><span class="sxs-lookup"><span data-stu-id="a0928-111">**Meeting Join Page CsWebServiceConfiguration Parameters**</span></span>

|<span data-ttu-id="a0928-112">**Parámetro de CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="a0928-112">**CsWebServiceConfiguration Parameter**</span></span>|<span data-ttu-id="a0928-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a0928-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a0928-114">Showjoinusinglegacyclientlink establecidos</span><span class="sxs-lookup"><span data-stu-id="a0928-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="a0928-115">Si se establece en true, los usuarios que se unan a una reunión con una aplicación cliente distinta de Lync tendrán la oportunidad de unirse a la reunión.</span><span class="sxs-lookup"><span data-stu-id="a0928-115">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting.</span></span> <span data-ttu-id="a0928-116">El valor predeterminado es False.</span><span class="sxs-lookup"><span data-stu-id="a0928-116">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="a0928-117">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="a0928-117">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="a0928-118">Cuando se establece en true, las opciones alternativas para unirse a una conferencia en línea se expanden automáticamente y se muestran a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="a0928-118">When set to True, alternate options for joining an online conference will automatically be expanded and shown to users.</span></span> <span data-ttu-id="a0928-119">Cuando se establece en false (el valor predeterminado), estas opciones estarán disponibles, pero el usuario tendrá que mostrar la lista de opciones por sí mismos.</span><span class="sxs-lookup"><span data-stu-id="a0928-119">When set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="a0928-120">Para configurar la página de participación en la reunión con el shell de administración de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="a0928-120">To configure the meeting join page by using Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="a0928-121">Inicie el shell de administración de Skype empresarial Server 2019: haga clic en **Inicio**, **todos los programas**, **Microsoft Skype empresarial Server 2019**y, a continuación, haga clic en **Shell de administración de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="a0928-121">Start the Skype for Business Server 2019 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="a0928-122">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a0928-122">Run the following cmdlet:</span></span> 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    <span data-ttu-id="a0928-123">Este cmdlet devuelve las opciones de configuración del servicio web.</span><span class="sxs-lookup"><span data-stu-id="a0928-123">This cmdlet returns the web service configuration settings.</span></span>
    
3. <span data-ttu-id="a0928-124">Ejecute el siguiente comando, con los parámetros establecidos en true o false, en función de sus preferencias (para obtener información detallada sobre los parámetros de este cmdlet, consulte la documentación del [Shell de administración de Skype empresarial Server](../../SfbServer/manage/management-shell.md) ):</span><span class="sxs-lookup"><span data-stu-id="a0928-124">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the [Skype for Business Server Management Shell](../../SfbServer/manage/management-shell.md) documentation):</span></span>
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


