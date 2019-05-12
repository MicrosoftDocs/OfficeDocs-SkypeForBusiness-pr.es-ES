---
title: Eliminar una directiva de PIN en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: 'Resumen: Eliminar telefónico un usuario PIN para Skype para Business Server.'
ms.openlocfilehash: b281716c2e0560936ea2f94b773c8191f3e8987e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919650"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="7970f-103">Eliminar una directiva de PIN en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="7970f-103">Delete a PIN policy in Skype for Business Server</span></span>
 
<span data-ttu-id="7970f-104">**Resumen:** Eliminar telefónico un usuario PIN para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="7970f-104">**Summary:** Delete a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="7970f-105">Siga estos pasos para eliminar una directiva de número de identificación personal (PIN).</span><span class="sxs-lookup"><span data-stu-id="7970f-105">Follow these steps to delete a personal identification number (PIN) policy.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7970f-106">No puede eliminar la directiva global de PIN.</span><span class="sxs-lookup"><span data-stu-id="7970f-106">You cannot delete the global PIN policy.</span></span> 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="7970f-107">Para eliminar una directiva de PIN en Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="7970f-107">To delete a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="7970f-108">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que implementa Skype para Business Server .</span><span class="sxs-lookup"><span data-stu-id="7970f-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="7970f-109">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="7970f-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="7970f-110">En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Directiva de PIN**.</span><span class="sxs-lookup"><span data-stu-id="7970f-110">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="7970f-111">En la página **Directiva de PIN**, escriba en el campo de búsqueda el nombre completo o parcial de la directiva que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="7970f-111">On the **PIN Policy** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="7970f-112">En la lista de directivas, haga clic en la directiva que desea, en **Editar** y en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="7970f-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="7970f-113">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7970f-113">Click **OK**.</span></span>
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7970f-114">Eliminación de directivas de PIN mediante el uso de Cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7970f-114">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7970f-115">Puede eliminar las directivas de PIN mediante el uso de Windows PowerShell y el cmdlet Remove-CsPinPolicy.</span><span class="sxs-lookup"><span data-stu-id="7970f-115">You can delete PIN policies by using Windows PowerShell and the Remove-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="7970f-116">Se puede ejecutar este cmdlet, ya sea desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7970f-116">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7970f-117">Para obtener información detallada acerca del uso de Windows PowerShell remoto para conectarse a Skype para Business Server, vea el artículo del blog ["rápido iniciar: administración de Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="7970f-117">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="7970f-118">El proceso es el mismo en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="7970f-118">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-pin-policy"></a><span data-ttu-id="7970f-119">Quitar una directiva de PIN específica</span><span class="sxs-lookup"><span data-stu-id="7970f-119">To remove a specific PIN policy</span></span>

- <span data-ttu-id="7970f-120">Este comando quita la Directiva de PIN con la RedmondPinPolicy de identidad:</span><span class="sxs-lookup"><span data-stu-id="7970f-120">This command removes the PIN policy with the Identity RedmondPinPolicy:</span></span>
    
  ```
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a><span data-ttu-id="7970f-121">Quitar todas las directivas de PIN que se aplican al ámbito del sitio</span><span class="sxs-lookup"><span data-stu-id="7970f-121">To remove all the PIN policies applied to the site scope</span></span>

- <span data-ttu-id="7970f-122">Este comando quita todas las directivas de PIN configuradas en el ámbito del sitio:</span><span class="sxs-lookup"><span data-stu-id="7970f-122">This command removes all the PIN policies configured at the site scope:</span></span>
    
  ```
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a><span data-ttu-id="7970f-123">Quitar todas las directivas de PIN que permiten el uso de patrones comunes</span><span class="sxs-lookup"><span data-stu-id="7970f-123">To remove all the PIN policies that allow the use of common patterns</span></span>

- <span data-ttu-id="7970f-124">Y este elimina todas las Directivas de PIN que permiten el uso de patrones comunes:G</span><span class="sxs-lookup"><span data-stu-id="7970f-124">And this one removes all the PIN policies that allow the use of common patterns:G</span></span>
    
  ```
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

<span data-ttu-id="7970f-125">Para obtener más información, vea el tema de ayuda para el cmdlet [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="7970f-125">For more information, see the help topic for the [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  

