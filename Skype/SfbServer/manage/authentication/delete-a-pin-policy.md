---
title: Eliminar una directiva de PIN en Skype Empresarial Server
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
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: 'Resumen: elimine el PIN de conferencia de acceso telefónico local de un usuario para Skype Empresarial Server.'
ms.openlocfilehash: b85d2bb29f8a1a28279a59f72957d201886d1dc4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096796"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="e606e-103">Eliminar una directiva de PIN en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e606e-103">Delete a PIN policy in Skype for Business Server</span></span>
 
<span data-ttu-id="e606e-104">**Resumen:** Elimine el PIN de conferencia de acceso telefónico local de un usuario para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e606e-104">**Summary:** Delete a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="e606e-105">Siga estos pasos para eliminar una directiva de número de identificación personal (PIN).</span><span class="sxs-lookup"><span data-stu-id="e606e-105">Follow these steps to delete a personal identification number (PIN) policy.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e606e-106">No puede eliminar la directiva global de PIN.</span><span class="sxs-lookup"><span data-stu-id="e606e-106">You cannot delete the global PIN policy.</span></span> 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="e606e-107">Para eliminar una directiva de PIN en el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e606e-107">To delete a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="e606e-108">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e606e-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="e606e-109">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e606e-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="e606e-110">En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Directiva de PIN**.</span><span class="sxs-lookup"><span data-stu-id="e606e-110">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="e606e-111">En la página **Directiva de PIN**, escriba en el campo de búsqueda el nombre completo o parcial de la directiva que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="e606e-111">On the **PIN Policy** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="e606e-112">En la lista de directivas, seleccione la directiva que desee, haga clic en **Editar** y, a continuación, en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="e606e-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="e606e-113">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e606e-113">Click **OK**.</span></span>
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e606e-114">Quitar directivas de PIN mediante cmdlets Windows PowerShell de datos</span><span class="sxs-lookup"><span data-stu-id="e606e-114">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e606e-115">Puede eliminar directivas de PIN mediante Windows PowerShell y el cmdlet Remove-CsPinPolicy.</span><span class="sxs-lookup"><span data-stu-id="e606e-115">You can delete PIN policies by using Windows PowerShell and the Remove-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="e606e-116">Puede ejecutar este cmdlet desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e606e-116">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e606e-117">Para obtener más información acerca del Windows PowerShell remoto para conectarse a Skype Empresarial Server, vea el artículo de blog "Inicio rápido: Administración de [Microsoft Lync Server 2010 mediante PowerShell remoto".](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="e606e-117">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="e606e-118">El proceso es el mismo en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e606e-118">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-pin-policy"></a><span data-ttu-id="e606e-119">Para quitar una directiva de PIN específica</span><span class="sxs-lookup"><span data-stu-id="e606e-119">To remove a specific PIN policy</span></span>

- <span data-ttu-id="e606e-120">Este comando elimina la Directiva de PIN con la RedmondPinPolicy de identidad:</span><span class="sxs-lookup"><span data-stu-id="e606e-120">This command removes the PIN policy with the Identity RedmondPinPolicy:</span></span>
    
  ```PowerShell
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a><span data-ttu-id="e606e-121">Para quitar todas las directivas de PIN aplicadas al ámbito del sitio</span><span class="sxs-lookup"><span data-stu-id="e606e-121">To remove all the PIN policies applied to the site scope</span></span>

- <span data-ttu-id="e606e-122">Este comando elimina todas las Directivas de PIN configuradas en el ámbito del sitio:</span><span class="sxs-lookup"><span data-stu-id="e606e-122">This command removes all the PIN policies configured at the site scope:</span></span>
    
  ```PowerShell
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a><span data-ttu-id="e606e-123">Para quitar todas las directivas de PIN que permiten el uso de patrones comunes</span><span class="sxs-lookup"><span data-stu-id="e606e-123">To remove all the PIN policies that allow the use of common patterns</span></span>

- <span data-ttu-id="e606e-124">Y este elimina todas las Directivas de PIN que permiten el uso de patrones comunes:G</span><span class="sxs-lookup"><span data-stu-id="e606e-124">And this one removes all the PIN policies that allow the use of common patterns:G</span></span>
    
  ```PowerShell
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

<span data-ttu-id="e606e-125">Para obtener más información, consulte el tema de ayuda del cmdlet [Remove-CsPinPolicy.](/powershell/module/skype/remove-cspinpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="e606e-125">For more information, see the help topic for the [Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy?view=skype-ps) cmdlet.</span></span>
