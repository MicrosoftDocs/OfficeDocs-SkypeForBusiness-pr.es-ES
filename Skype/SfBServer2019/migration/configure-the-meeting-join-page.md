---
title: Configuración de la reunión de la página de participación
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: End User
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Cuando un usuario hace clic en un vínculo de la reunión en una convocatoria de reunión, la reunión detecta de la página de participación de cliente que ya esté instalado en el equipo del usuario. Si ya está instalado un cliente, que el cliente se abre y se une a la reunión. Si un cliente no está instalado, de forma predeterminada que se abre la aplicación Web.
ms.openlocfilehash: f7c66b7e7171e9d7f0dc39f30a7e99059e53a0c2
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374065"
---
# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="25611-105">Configuración de la reunión de la página de participación</span><span class="sxs-lookup"><span data-stu-id="25611-105">Configure the meeting join page</span></span>

<span data-ttu-id="25611-106">Cuando un usuario hace clic en un vínculo de la reunión en una convocatoria de reunión, la reunión detecta de la página de participación de cliente que ya esté instalado en el equipo del usuario.</span><span class="sxs-lookup"><span data-stu-id="25611-106">When a user clicks a meeting link in a meeting request, the meeting join page detects which client is already installed on the user's computer.</span></span> <span data-ttu-id="25611-107">Si ya está instalado un cliente, que el cliente se abre y se une a la reunión.</span><span class="sxs-lookup"><span data-stu-id="25611-107">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="25611-108">Si un cliente no está instalado, de forma predeterminada que se abre la aplicación Web.</span><span class="sxs-lookup"><span data-stu-id="25611-108">If a client is not installed, by default the Web App opens.</span></span>
  
<span data-ttu-id="25611-109">Puede modificar el comportamiento de la participación en reuniones de página si desea permitir a los usuarios participar en reuniones.</span><span class="sxs-lookup"><span data-stu-id="25611-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings.</span></span> <span data-ttu-id="25611-110">Estas opciones de configuración se han quitado del Panel de Control, pero se configuran mediante el cmdlet de CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="25611-110">These configuration options have been removed from the Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="25611-111">**Parámetros CsWebServiceConfiguration de la página unirse a la reunión**</span><span class="sxs-lookup"><span data-stu-id="25611-111">**Meeting Join Page CsWebServiceConfiguration Parameters**</span></span>

|<span data-ttu-id="25611-112">**Parámetro CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="25611-112">**CsWebServiceConfiguration Parameter**</span></span>|<span data-ttu-id="25611-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="25611-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="25611-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="25611-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="25611-115">Si se establece en True, los usuarios unirse a una reunión mediante el uso de una aplicación de cliente que no sea Lync se le dará la oportunidad de unirse a la reunión.</span><span class="sxs-lookup"><span data-stu-id="25611-115">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting.</span></span> <span data-ttu-id="25611-116">El valor predeterminado es False.</span><span class="sxs-lookup"><span data-stu-id="25611-116">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="25611-117">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="25611-117">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="25611-118">Cuando se establece en True, se alternan las opciones para unirse a una conferencia en línea automáticamente que se expande y se muestra a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="25611-118">When set to True, alternate options for joining an online conference will automatically be expanded and shown to users.</span></span> <span data-ttu-id="25611-119">Cuando se establece en False (el valor predeterminado), estas opciones estarán disponibles, pero el usuario tendrá que mostrar la lista de opciones para sí mismos.</span><span class="sxs-lookup"><span data-stu-id="25611-119">When set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="25611-120">Para configurar la reunión mediante el uso de Skype para Shell de administración de Business Server 2019 la página de participación</span><span class="sxs-lookup"><span data-stu-id="25611-120">To configure the meeting join page by using Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="25611-121">Iniciar el Skype para Shell de administración de Business Server 2019: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Microsoft Skype para Business Server 2019**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**.</span><span class="sxs-lookup"><span data-stu-id="25611-121">Start the Skype for Business Server 2019 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="25611-122">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="25611-122">Run the following cmdlet:</span></span> 
    
   ```
   Get-CsWebServiceConfiguration
   ```

    <span data-ttu-id="25611-123">Este cmdlet devuelve la configuración del servicio de la web.</span><span class="sxs-lookup"><span data-stu-id="25611-123">This cmdlet returns the web service configuration settings.</span></span>
    
3. <span data-ttu-id="25611-124">Ejecute el siguiente comando, con el conjunto de parámetros en True o False, según su preferencia (para obtener información detallada sobre los parámetros de este cmdlet, vea la documentación de [Skype para Business Server Management Shell](../../SfbServer/manage/management-shell.md) ):</span><span class="sxs-lookup"><span data-stu-id="25611-124">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the [Skype for Business Server Management Shell](../../SfbServer/manage/management-shell.md) documentation):</span></span>
    
   ```
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


