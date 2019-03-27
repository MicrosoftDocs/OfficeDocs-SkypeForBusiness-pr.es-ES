---
title: Habilitar control de admisión de llamadas en Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: Habilitar control de admisión de llamadas en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 7e4c444b5aa0b0e4d3c3517b9d242c839f6ecda5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30872762"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="6bf2b-103">Habilitar control de admisión de llamadas en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="6bf2b-103">Enable call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="6bf2b-104">Habilitar control de admisión de llamadas en Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-104">Enable call admission control in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="6bf2b-105">Después de configurar las opciones de red para la implementación del control de admisión de llamadas, debe habilitar el CAC para que se apliquen las directivas de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-105">After you have configured your network settings for call admission control deployment, you must enable CAC to put your bandwidth policies into effect.</span></span>
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6bf2b-106">Para habilitar el control de admisión de llamadas mediante el uso de Skype para Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="6bf2b-106">To enable call admission control by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="6bf2b-107">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-107">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="6bf2b-p101">Ejecute el cmdlet Set-CsNetworkConfiguration para habilitar el CAC en su red. Por ejemplo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6bf2b-p101">Run the Set-CsNetworkConfiguration cmdlet to enable CAC in your network. For example, run:</span></span>
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    <span data-ttu-id="6bf2b-110">Si desea deshabilitar el CAC en la red, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6bf2b-110">If you want to disable CAC in your network, run the following:</span></span>
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6bf2b-111">Para habilitar el control de admisión de llamadas mediante el uso de Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="6bf2b-111">To enable call admission control by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6bf2b-112">Abra Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-112">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="6bf2b-113">En la barra de navegación izquierda, haga clic en **Configuración de red**.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="6bf2b-114">Haga clic en el botón de navegación **Global**.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-114">Click the **Global** navigation button.</span></span>
    
4. <span data-ttu-id="6bf2b-115">Haga clic en **Global** en la lista y, a continuación, seleccione **Mostrar detalles** en el menú **Editar**.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-115">Click **Global** in the list, and then select **Show Details** on the **Edit** menu.</span></span>
    
5. <span data-ttu-id="6bf2b-116">En la página **Editar configuración global**, active la casilla **Habilitar control de admisión de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-116">On the **Edit Global Settings** page, select the **Enable call admission control** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6bf2b-117">Si desea deshabilitar el control de admisión de llamadas en toda la implementación, desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-117">If you want to disable call admission control throughout your deployment, clear this check box.</span></span> 
  
6. <span data-ttu-id="6bf2b-118">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-118">Click **Commit**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="6bf2b-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6bf2b-119">See also</span></span>

[<span data-ttu-id="6bf2b-120">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="6bf2b-120">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="6bf2b-121">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="6bf2b-121">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="6bf2b-122">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="6bf2b-122">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)
