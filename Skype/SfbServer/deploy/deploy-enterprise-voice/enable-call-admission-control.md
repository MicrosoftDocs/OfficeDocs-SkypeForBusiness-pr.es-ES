---
title: Habilitar el control de admisión de llamadas en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: Habilitar control de admisión de llamadas en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 321b7838a2a818a9791b72e3851312006eb8dc7e
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="enable-call-admission-control-in-skype-for-business-server-2015"></a><span data-ttu-id="4d29d-103">Habilitar el control de admisión de llamadas en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="4d29d-103">Enable call admission control in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4d29d-104">Habilitar control de admisión de llamadas en Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="4d29d-104">Enable call admission control in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="4d29d-105">Después de configurar las opciones de red para la implementación del control de admisión de llamadas, debe habilitar el CAC para que se apliquen las directivas de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="4d29d-105">After you have configured your network settings for call admission control deployment, you must enable CAC to put your bandwidth policies into effect.</span></span>
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="4d29d-106">Para habilitar el control de admisión de llamadas mediante el uso de Skype para Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="4d29d-106">To enable call admission control by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="4d29d-107">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="4d29d-107">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="4d29d-p101">Ejecute el cmdlet Set-CsNetworkConfiguration para habilitar el CAC en su red. Por ejemplo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4d29d-p101">Run the Set-CsNetworkConfiguration cmdlet to enable CAC in your network. For example, run:</span></span>
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    <span data-ttu-id="4d29d-110">Si desea deshabilitar el CAC en la red, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4d29d-110">If you want to disable CAC in your network, run the following:</span></span>
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="4d29d-111">Para habilitar el control de admisión de llamadas mediante el uso de Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="4d29d-111">To enable call admission control by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="4d29d-112">Abra Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="4d29d-112">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="4d29d-113">En la barra de navegación izquierda, haga clic en **Configuración de red**.</span><span class="sxs-lookup"><span data-stu-id="4d29d-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="4d29d-114">Haga clic en el botón de navegación **Global**.</span><span class="sxs-lookup"><span data-stu-id="4d29d-114">Click the **Global** navigation button.</span></span>
    
4. <span data-ttu-id="4d29d-115">Haga clic en **Global** en la lista y, a continuación, seleccione **Mostrar detalles** en el menú **Editar**.</span><span class="sxs-lookup"><span data-stu-id="4d29d-115">Click **Global** in the list, and then select **Show Details** on the **Edit** menu.</span></span>
    
5. <span data-ttu-id="4d29d-116">En la página **Editar configuración global**, active la casilla **Habilitar control de admisión de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="4d29d-116">On the **Edit Global Settings** page, select the **Enable call admission control** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4d29d-117">Si desea deshabilitar el control de admisión de llamadas en toda la implementación, desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="4d29d-117">If you want to disable call admission control throughout your deployment, clear this check box.</span></span> 
  
6. <span data-ttu-id="4d29d-118">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="4d29d-118">Click **Commit**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="4d29d-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d29d-119">See also</span></span>

#### 

[<span data-ttu-id="4d29d-120">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="4d29d-120">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="4d29d-121">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="4d29d-121">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="4d29d-122">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="4d29d-122">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)

