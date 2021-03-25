---
title: Modificar directivas de conferencia en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 'Resumen: obtenga información sobre cómo modificar directivas de conferencia en Skype Empresarial Server.'
ms.openlocfilehash: 6bbba82c9785e074da492eb66cbdd943dc0cea35
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119429"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="917c6-103">Modificar directivas de conferencia en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="917c6-103">Modify conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="917c6-104">**Resumen:** Obtenga información sobre cómo modificar directivas de conferencia en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="917c6-104">**Summary:** Learn how to modify conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="917c6-105">Puede modificar directivas de conferencia mediante el Panel de control de Skype Empresarial Server o mediante el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="917c6-105">You can modify conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="917c6-106">Modificar directivas de conferencia mediante el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="917c6-106">Modify conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="917c6-107">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="917c6-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="917c6-108">Abra el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="917c6-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="917c6-109">En la barra de navegación izquierda, haga clic **en Conferencia** y, a continuación, haga clic en Directiva **de conferencia.**</span><span class="sxs-lookup"><span data-stu-id="917c6-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="917c6-110">En la lista de directivas de conferencia, haga clic en la directiva que desee cambiar y luego haga clic en **Editar** y en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="917c6-110">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="917c6-111">En **Editar directiva de conferencia**, modifique cualquier configuración de directivas, salvo el nombre de la directiva, que no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="917c6-111">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="917c6-112">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="917c6-112">Click **Commit**.</span></span>
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="917c6-113">Modificar directivas de conferencia mediante el Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="917c6-113">Modify conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="917c6-114">Para modificar directivas de conferencia, use el cmdlet **Set-CsConferencingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="917c6-114">To modify conferencing policies, use the **Set-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="917c6-115">En el siguiente ejemplo se modifica un valor de propiedad de la directiva de conferencia SalesConferencingPolicy.</span><span class="sxs-lookup"><span data-stu-id="917c6-115">The following example modifies a property value of the conferencing policy SalesConferencingPolicy.</span></span> <span data-ttu-id="917c6-116">El comando establece el valor de la propiedad AllowConferenceRecording en False:</span><span class="sxs-lookup"><span data-stu-id="917c6-116">The command sets the value of the AllowConferenceRecording property to False:</span></span>
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

<span data-ttu-id="917c6-117">Para obtener más información, incluida la sintaxis completa y una lista de parámetros, vea [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="917c6-117">For more information, including complete syntax and a list of parameters, see [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
