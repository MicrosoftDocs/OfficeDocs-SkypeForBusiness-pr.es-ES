---
title: Configurar la página para unirse a la reunión
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: End User
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Cuando un usuario hace clic en un vínculo de la reunión en una convocatoria de reunión, la reunión detecta de la página de participación de cliente que ya esté instalado en el equipo del usuario. Si ya está instalado un cliente, que el cliente se abre y se une a la reunión. Si un cliente no está instalado, de forma predeterminada que se abre la aplicación Web.
ms.openlocfilehash: 88ae915318505efef6ae716a17217aaa1e7b12df
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238719"
---
# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="6d91d-105">Configurar la página para unirse a la reunión</span><span class="sxs-lookup"><span data-stu-id="6d91d-105">Configure the meeting join page</span></span>

<span data-ttu-id="6d91d-106">Cuando un usuario hace clic en un vínculo de la reunión en una convocatoria de reunión, la reunión detecta de la página de participación de cliente que ya esté instalado en el equipo del usuario.</span><span class="sxs-lookup"><span data-stu-id="6d91d-106">When a user clicks a meeting link in a meeting request, the meeting join page detects which client is already installed on the user's computer.</span></span> <span data-ttu-id="6d91d-107">Si ya está instalado un cliente, que el cliente se abre y se une a la reunión.</span><span class="sxs-lookup"><span data-stu-id="6d91d-107">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="6d91d-108">Si un cliente no está instalado, de forma predeterminada que se abre la aplicación Web.</span><span class="sxs-lookup"><span data-stu-id="6d91d-108">If a client is not installed, by default the Web App opens.</span></span>
  
<span data-ttu-id="6d91d-109">Puede modificar el comportamiento de la participación en reuniones de página si desea permitir a los usuarios participar en reuniones.</span><span class="sxs-lookup"><span data-stu-id="6d91d-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings.</span></span> <span data-ttu-id="6d91d-110">Estas opciones de configuración se han quitado del Panel de Control, pero se configuran mediante el cmdlet de CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="6d91d-110">These configuration options have been removed from the Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="6d91d-111">**Parámetros CsWebServiceConfiguration de la página unirse a la reunión**</span><span class="sxs-lookup"><span data-stu-id="6d91d-111">**Meeting Join Page CsWebServiceConfiguration Parameters**</span></span>

|<span data-ttu-id="6d91d-112">**Parámetro CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="6d91d-112">**CsWebServiceConfiguration Parameter**</span></span>|<span data-ttu-id="6d91d-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="6d91d-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6d91d-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="6d91d-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="6d91d-115">Si se establece en True, los usuarios unirse a una reunión mediante el uso de una aplicación de cliente que no sea Lync se le dará la oportunidad de unirse a la reunión.</span><span class="sxs-lookup"><span data-stu-id="6d91d-115">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting.</span></span> <span data-ttu-id="6d91d-116">El valor predeterminado es False.</span><span class="sxs-lookup"><span data-stu-id="6d91d-116">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="6d91d-117">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="6d91d-117">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="6d91d-118">Cuando se establece en True, se alternan las opciones para unirse a una conferencia en línea automáticamente que se expande y se muestra a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6d91d-118">When set to True, alternate options for joining an online conference will automatically be expanded and shown to users.</span></span> <span data-ttu-id="6d91d-119">Cuando se establece en False (el valor predeterminado), estas opciones estarán disponibles, pero el usuario tendrá que mostrar la lista de opciones para sí mismos.</span><span class="sxs-lookup"><span data-stu-id="6d91d-119">When set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="6d91d-120">Para configurar la reunión mediante el uso de Skype para Shell de administración de Business Server 2019 la página de participación</span><span class="sxs-lookup"><span data-stu-id="6d91d-120">To configure the meeting join page by using Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="6d91d-121">Iniciar el Skype para Shell de administración de Business Server 2019: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Microsoft Skype para Business Server 2019**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**.</span><span class="sxs-lookup"><span data-stu-id="6d91d-121">Start the Skype for Business Server 2019 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="6d91d-122">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6d91d-122">Run the following cmdlet:</span></span> 
    
   ```
   Get-CsWebServiceConfiguration
   ```

    <span data-ttu-id="6d91d-123">Este cmdlet devuelve la configuración del servicio de la web.</span><span class="sxs-lookup"><span data-stu-id="6d91d-123">This cmdlet returns the web service configuration settings.</span></span>
    
3. <span data-ttu-id="6d91d-124">Ejecute el siguiente comando, con el conjunto de parámetros en True o False, según su preferencia (para obtener información detallada sobre los parámetros de este cmdlet, vea la documentación de [Skype para Business Server Management Shell](../../SfbServer/manage/management-shell.md) ):</span><span class="sxs-lookup"><span data-stu-id="6d91d-124">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the [Skype for Business Server Management Shell](../../SfbServer/manage/management-shell.md) documentation):</span></span>
    
   ```
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


