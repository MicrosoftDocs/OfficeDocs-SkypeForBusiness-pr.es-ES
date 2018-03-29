---
title: Eliminar una directiva de PIN en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: 'Resumen: Eliminar de acceso telefónico conferencias de un usuario de PIN de Skype para Business Server 2015.'
ms.openlocfilehash: b64a4509105214358549f320cf8885d6386986f7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="delete-a-pin-policy-in-skype-for-business-server-2015"></a><span data-ttu-id="90bd5-103">Eliminar una directiva de PIN en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="90bd5-103">Delete a PIN policy in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="90bd5-104">**Resumen:** Eliminar de acceso telefónico conferencias de un usuario de PIN de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="90bd5-104">**Summary:** Delete a user's dial-in conferencing PIN for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="90bd5-105">Siga estos pasos para eliminar una directiva de número de identificación personal (PIN).</span><span class="sxs-lookup"><span data-stu-id="90bd5-105">Follow these steps to delete a personal identification number (PIN) policy.</span></span>
  
> [!NOTE]
> <span data-ttu-id="90bd5-106">No puede eliminar la directiva global de PIN.</span><span class="sxs-lookup"><span data-stu-id="90bd5-106">You cannot delete the global PIN policy.</span></span> 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="90bd5-107">Para eliminar una directiva de NIP en Skype para Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="90bd5-107">To delete a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="90bd5-108">Desde una cuenta de usuario que es miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en el que implementa Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="90bd5-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="90bd5-109">Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="90bd5-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="90bd5-110">En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Directiva de PIN**.</span><span class="sxs-lookup"><span data-stu-id="90bd5-110">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="90bd5-111">En la página **Directiva de PIN**, escriba en el campo de búsqueda el nombre completo o parcial de la directiva que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="90bd5-111">On the **PIN Policy** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="90bd5-112">En la lista de directivas, haga clic en la directiva que desea, en **Editar** y en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="90bd5-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="90bd5-113">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="90bd5-113">Click **OK**.</span></span>
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="90bd5-114">Quitar directivas de NIP mediante Cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="90bd5-114">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="90bd5-115">Puede eliminar directivas de NIP mediante Windows PowerShell y el cmdlet Remove-CsPinPolicy.</span><span class="sxs-lookup"><span data-stu-id="90bd5-115">You can delete PIN policies by using Windows PowerShell and the Remove-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="90bd5-116">Este cmdlet se puede ejecutar desde el Skype para el Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90bd5-116">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="90bd5-117">Para obtener más información acerca del uso de Windows PowerShell remoto para conectar con Skype para Business Server, consulte el artículo de blog ["rápido inicio: administración de Microsoft Lync Server 2010 utilizando remoto PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="90bd5-117">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="90bd5-118">El proceso es el mismo en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="90bd5-118">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-pin-policy"></a><span data-ttu-id="90bd5-119">Quitar una directiva de PIN específica</span><span class="sxs-lookup"><span data-stu-id="90bd5-119">To remove a specific PIN policy</span></span>

- <span data-ttu-id="90bd5-120">Este comando quita la Directiva de PIN con la RedmondPinPolicy de identidad:</span><span class="sxs-lookup"><span data-stu-id="90bd5-120">This command removes the PIN policy with the Identity RedmondPinPolicy:</span></span>
    
  ```
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a><span data-ttu-id="90bd5-121">Quitar todas las directivas de PIN que se aplican al ámbito del sitio</span><span class="sxs-lookup"><span data-stu-id="90bd5-121">To remove all the PIN policies applied to the site scope</span></span>

- <span data-ttu-id="90bd5-122">Este comando quita todas las directivas de PIN configuradas en el ámbito del sitio:</span><span class="sxs-lookup"><span data-stu-id="90bd5-122">This command removes all the PIN policies configured at the site scope:</span></span>
    
  ```
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a><span data-ttu-id="90bd5-123">Quitar todas las directivas de PIN que permiten el uso de patrones comunes</span><span class="sxs-lookup"><span data-stu-id="90bd5-123">To remove all the PIN policies that allow the use of common patterns</span></span>

- <span data-ttu-id="90bd5-124">Y este elimina todas las Directivas de PIN que permiten el uso de patrones comunes:G</span><span class="sxs-lookup"><span data-stu-id="90bd5-124">And this one removes all the PIN policies that allow the use of common patterns:G</span></span>
    
  ```
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

<span data-ttu-id="90bd5-125">Para obtener más información, vea el tema de ayuda para el cmdlet [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="90bd5-125">For more information, see the help topic for the [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  

