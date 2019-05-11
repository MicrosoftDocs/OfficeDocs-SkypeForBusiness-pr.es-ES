---
title: Modificar las directivas de conferencia en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 'Resumen: Obtenga información sobre cómo modificar las directivas de conferencia en Skype para Business Server.'
ms.openlocfilehash: 0ca232398c9133c3340cbae909ac43d44ba641dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911990"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="e5e89-103">Modificar las directivas de conferencia en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="e5e89-103">Modify conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="e5e89-104">**Resumen:** Obtenga información sobre cómo modificar las directivas de conferencia en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="e5e89-104">**Summary:** Learn how to modify conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="e5e89-105">Puede modificar las directivas de conferencia mediante el uso de Skype para el Panel de Control de servidor empresarial o mediante el uso de Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="e5e89-105">You can modify conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="e5e89-106">Modificar las directivas de conferencia mediante Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="e5e89-106">Modify conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="e5e89-107">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="e5e89-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="e5e89-108">Abra Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="e5e89-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="e5e89-109">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="e5e89-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="e5e89-110">En la lista de directivas de conferencia, haga clic en la directiva que desee cambiar y luego haga clic en **Editar** y en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="e5e89-110">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="e5e89-111">En **Editar directiva de conferencia**, modifique cualquier configuración de directivas, salvo el nombre de la directiva, que no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="e5e89-111">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="e5e89-112">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e5e89-112">Click **Commit**.</span></span>
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="e5e89-113">Modificar las directivas de conferencia mediante Skype para Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="e5e89-113">Modify conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="e5e89-114">Para modificar las directivas de conferencia, use el cmdlet **Set-CsConferencingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="e5e89-114">To modify conferencing policies, use the **Set-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="e5e89-115">El siguiente ejemplo modifica un valor de propiedad de la directiva de conferencia SalesConferencingPolicy.</span><span class="sxs-lookup"><span data-stu-id="e5e89-115">The following example modifies a property value of the conferencing policy SalesConferencingPolicy.</span></span> <span data-ttu-id="e5e89-116">El comando establece el valor de la propiedad AllowConferenceRecording en False:</span><span class="sxs-lookup"><span data-stu-id="e5e89-116">The command sets the value of the AllowConferenceRecording property to False:</span></span>
  
```
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

<span data-ttu-id="e5e89-117">Para obtener más información, incluida la sintaxis completa y una lista de parámetros, consulte [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="e5e89-117">For more information, including complete syntax and a list of parameters, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

