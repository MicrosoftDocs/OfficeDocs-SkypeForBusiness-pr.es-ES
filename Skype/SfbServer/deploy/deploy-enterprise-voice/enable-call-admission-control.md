---
title: Habilitar el control de admisión de llamadas en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: Habilitar el control de admisión de llamadas en Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: a1a2259c754af0275e473e6c0d175039450cecf7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240498"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="0a286-103">Habilitar el control de admisión de llamadas en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="0a286-103">Enable call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="0a286-104">Habilitar el control de admisión de llamadas en Skype empresarial Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="0a286-104">Enable call admission control in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="0a286-105">Después de configurar las opciones de red para la implementación del control de admisión de llamadas, debe habilitar el CAC para que se apliquen las directivas de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="0a286-105">After you have configured your network settings for call admission control deployment, you must enable CAC to put your bandwidth policies into effect.</span></span>
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="0a286-106">Para habilitar el control de admisión de llamadas mediante el shell de administración de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="0a286-106">To enable call admission control by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="0a286-107">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="0a286-107">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="0a286-p101">Ejecute el cmdlet Set-CsNetworkConfiguration para habilitar el CAC en su red. Por ejemplo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0a286-p101">Run the Set-CsNetworkConfiguration cmdlet to enable CAC in your network. For example, run:</span></span>
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    <span data-ttu-id="0a286-110">Si desea deshabilitar el CAC en la red, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0a286-110">If you want to disable CAC in your network, run the following:</span></span>
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="0a286-111">Para habilitar el control de admisión de llamadas con el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="0a286-111">To enable call admission control by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="0a286-112">Abra el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="0a286-112">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="0a286-113">En la barra de navegación izquierda, haga clic en **Configuración de red**.</span><span class="sxs-lookup"><span data-stu-id="0a286-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="0a286-114">Haga clic en el botón de navegación **Global**.</span><span class="sxs-lookup"><span data-stu-id="0a286-114">Click the **Global** navigation button.</span></span>
    
4. <span data-ttu-id="0a286-115">Haga clic en **Global** en la lista y, a continuación, seleccione **Mostrar detalles** en el menú **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0a286-115">Click **Global** in the list, and then select **Show Details** on the **Edit** menu.</span></span>
    
5. <span data-ttu-id="0a286-116">En la página **Editar configuración global**, active la casilla **Habilitar control de admisión de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="0a286-116">On the **Edit Global Settings** page, select the **Enable call admission control** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0a286-117">Si desea deshabilitar el control de admisión de llamadas en toda la implementación, desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="0a286-117">If you want to disable call admission control throughout your deployment, clear this check box.</span></span> 
  
6. <span data-ttu-id="0a286-118">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="0a286-118">Click **Commit**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="0a286-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a286-119">See also</span></span>

[<span data-ttu-id="0a286-120">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="0a286-120">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="0a286-121">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="0a286-121">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="0a286-122">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="0a286-122">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)
