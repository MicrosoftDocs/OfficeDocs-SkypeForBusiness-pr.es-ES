---
title: Configurar la página para unirse a la reunión
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: End User
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Cuando un usuario hace clic en un vínculo de reunión en una convocatoria de reunión, la página de la reunión detecta qué cliente ya está instalado en el equipo del usuario. Si un cliente ya está instalado, ese cliente se abre y se une a la reunión. De forma predeterminada, si un cliente no está instalado, se abre la aplicación Web.
ms.openlocfilehash: c5f6cd5b1d04b54f8db9f82080bc8dbabefdc11e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298280"
---
# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="3f732-105">Configurar la página para unirse a la reunión</span><span class="sxs-lookup"><span data-stu-id="3f732-105">Configure the meeting join page</span></span>

<span data-ttu-id="3f732-106">Cuando un usuario hace clic en un vínculo de reunión en una convocatoria de reunión, la página de la reunión detecta qué cliente ya está instalado en el equipo del usuario.</span><span class="sxs-lookup"><span data-stu-id="3f732-106">When a user clicks a meeting link in a meeting request, the meeting join page detects which client is already installed on the user's computer.</span></span> <span data-ttu-id="3f732-107">Si un cliente ya está instalado, ese cliente se abre y se une a la reunión.</span><span class="sxs-lookup"><span data-stu-id="3f732-107">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="3f732-108">De forma predeterminada, si un cliente no está instalado, se abre la aplicación Web.</span><span class="sxs-lookup"><span data-stu-id="3f732-108">If a client is not installed, by default the Web App opens.</span></span>
  
<span data-ttu-id="3f732-109">Puede modificar el comportamiento de la página de la combinación de reuniones si desea permitir que los usuarios se unan a las reuniones.</span><span class="sxs-lookup"><span data-stu-id="3f732-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings.</span></span> <span data-ttu-id="3f732-110">Estas opciones de configuración se han eliminado del panel de control, pero se configuran mediante el cmdlet CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="3f732-110">These configuration options have been removed from the Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="3f732-111">**Página de combinación de reuniones CsWebServiceConfiguration parámetros**</span><span class="sxs-lookup"><span data-stu-id="3f732-111">**Meeting Join Page CsWebServiceConfiguration Parameters**</span></span>

|<span data-ttu-id="3f732-112">**Parámetro CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="3f732-112">**CsWebServiceConfiguration Parameter**</span></span>|<span data-ttu-id="3f732-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="3f732-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3f732-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="3f732-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="3f732-115">Si se establece en true, los usuarios que se unan a una reunión mediante una aplicación cliente que no sea Lync tendrán la oportunidad de unirse a la reunión.</span><span class="sxs-lookup"><span data-stu-id="3f732-115">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting.</span></span> <span data-ttu-id="3f732-116">El valor predeterminado es False.</span><span class="sxs-lookup"><span data-stu-id="3f732-116">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="3f732-117">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="3f732-117">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="3f732-118">Si se establece en true, las opciones alternativas para unirse a una conferencia en línea se expandirán y se mostrarán automáticamente a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3f732-118">When set to True, alternate options for joining an online conference will automatically be expanded and shown to users.</span></span> <span data-ttu-id="3f732-119">Cuando se establece en false (el valor predeterminado), estas opciones estarán disponibles, pero el usuario tendrá que mostrar la lista de opciones por sí mismo.</span><span class="sxs-lookup"><span data-stu-id="3f732-119">When set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="3f732-120">Para configurar la página de la combinación de reuniones con el shell de administración de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="3f732-120">To configure the meeting join page by using Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="3f732-121">Inicie el shell de administración de Skype empresarial Server 2019: haga clic en **Inicio**, haga clic en **todos los programas**, **Microsoft Skype empresarial Server 2019**y, a continuación, haga clic en **consola de administración de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="3f732-121">Start the Skype for Business Server 2019 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="3f732-122">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3f732-122">Run the following cmdlet:</span></span> 
    
   ```
   Get-CsWebServiceConfiguration
   ```

    <span data-ttu-id="3f732-123">Este cmdlet devuelve los parámetros de configuración del servicio Web.</span><span class="sxs-lookup"><span data-stu-id="3f732-123">This cmdlet returns the web service configuration settings.</span></span>
    
3. <span data-ttu-id="3f732-124">Ejecute el siguiente comando, con los parámetros establecidos en true o false, en función de su preferencia (para obtener información detallada sobre los parámetros para este cmdlet, consulte la documentación del [Shell de administración de Skype empresarial](../../SfbServer/manage/management-shell.md) ):</span><span class="sxs-lookup"><span data-stu-id="3f732-124">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the [Skype for Business Server Management Shell](../../SfbServer/manage/management-shell.md) documentation):</span></span>
    
   ```
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


