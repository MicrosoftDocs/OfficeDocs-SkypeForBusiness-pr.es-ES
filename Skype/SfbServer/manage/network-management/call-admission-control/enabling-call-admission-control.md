---
title: Habilitar el control de admisión de llamadas
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
description: " Después de configurar la red de control de admisión de llamadas (CAC), debe habilitar el CAC para aplicar las limitaciones de ancho de banda."
ms.openlocfilehash: 8e996b4d2272144a35f667a5d6987b2cb91af708
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816510"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="9b8c2-103">Habilitar el control de admisión de llamadas en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9b8c2-103">Enabling call admission control in Skype for Business Server</span></span>

<span data-ttu-id="9b8c2-104">El control de admisión de llamadas (CAC) consiste en una red de regiones, sitios y subredes que permiten aplicar restricciones en las transmisiones de audio y vídeo según el ancho de banda disponible.</span><span class="sxs-lookup"><span data-stu-id="9b8c2-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="9b8c2-105">Una vez configurada la red CAC, debe habilitar el CAC para aplicar las limitaciones de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="9b8c2-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="9b8c2-106">Para ello, puede usar el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="9b8c2-106">You can use the Skype for Business Server Control Panel to do this.</span></span>


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a><span data-ttu-id="9b8c2-107">Para habilitar el CAC desde el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9b8c2-107">To enable CAC from the Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="9b8c2-108">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="9b8c2-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9b8c2-109">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="9b8c2-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9b8c2-110">En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic **en Global**.</span><span class="sxs-lookup"><span data-stu-id="9b8c2-110">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="9b8c2-111">En la página **Global**, haga clic en la configuración **Global**.</span><span class="sxs-lookup"><span data-stu-id="9b8c2-111">On the **Global** page, click the **Global** configuration.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="9b8c2-112">Solo se puede configurar una red para cualquier implementación de Skype Empresarial Server, por lo que nunca habrá más de una configuración de red en la lista.</span><span class="sxs-lookup"><span data-stu-id="9b8c2-112">Only one network can be configured for any Skype for Business Server deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="9b8c2-113">No podrá cambiar el nombre de la configuración Global.</span><span class="sxs-lookup"><span data-stu-id="9b8c2-113">You cannot rename the Global configuration.</span></span>

5.  <span data-ttu-id="9b8c2-114">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="9b8c2-114">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="9b8c2-115">En la página **Editar configuración global**, active la casilla **Habilitar control de admisión de llamadas** y, a continuación, haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="9b8c2-115">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="9b8c2-p103">Al hacer clic en **Confirmar**, realizará una prueba de la configuración. Se cerrará el cuadro de diálogo **Editar configuración global** y el programa le devolverá a la página **Global**. Recibirá una advertencia si se descubren errores o incoherencias en la configuración de red que pudieran impedir el buen funcionamiento de la red (por ejemplo, si cada región no está conectada a otra región en una ruta interregional).</span><span class="sxs-lookup"><span data-stu-id="9b8c2-p103">When you click **Commit**, you run a test of the configuration. The **Edit Global Settings** dialog box closes, returning you to the **Global** page. You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="9b8c2-p104">Si hace cambios en la configuración de red, puede volver a ejecutar la comprobación de validación abriendo la configuración Global y haciendo clic en **Confirmar**. No es necesario deshabilitar previamente el CAC: deje activada la casilla y haga clic en **Confirmar**. Puede hacerlo en cualquier momento aunque no haga cambios en la configuración.</span><span class="sxs-lookup"><span data-stu-id="9b8c2-p104">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**. You do not need to disable CAC first: leave the check box checked and click **Commit**. You can do this at any time without making any configuration changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="9b8c2-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9b8c2-122">See Also</span></span>

[<span data-ttu-id="9b8c2-123">Planeación del control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="9b8c2-123">Plan for call admission control</span></span>](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[<span data-ttu-id="9b8c2-124">Implementar el control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="9b8c2-124">Deploy call admission control</span></span>](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[<span data-ttu-id="9b8c2-125">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="9b8c2-125">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[<span data-ttu-id="9b8c2-126">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="9b8c2-126">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[<span data-ttu-id="9b8c2-127">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="9b8c2-127">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
