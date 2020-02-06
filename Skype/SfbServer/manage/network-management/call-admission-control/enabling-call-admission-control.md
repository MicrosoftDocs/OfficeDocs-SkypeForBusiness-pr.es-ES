---
title: Habilitar el control de admisión de llamadas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: " Después de configurar la red de control de admisión de llamadas (CAC), debe habilitar CAC para exigir las limitaciones de ancho de banda."
ms.openlocfilehash: 4f9f3f09f943b417ec589f26dc5c6505d30831f9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817539"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="eccc5-103">Habilitar el control de admisión de llamadas en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="eccc5-103">Enabling call admission control in Skype for Business Server</span></span>

<span data-ttu-id="eccc5-104">El control de admisión de llamadas (CAC) es una red de regiones, sitios y subredes que permiten colocar restricciones en las transmisiones de audio y vídeo según el ancho de banda disponible.</span><span class="sxs-lookup"><span data-stu-id="eccc5-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="eccc5-105">Después de configurar la red CAC, debe habilitar CAC para exigir las limitaciones de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="eccc5-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="eccc5-106">Puede usar el panel de control de Skype empresarial Server para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="eccc5-106">You can use the Skype for Business Server Control Panel to do this.</span></span>


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a><span data-ttu-id="eccc5-107">Para habilitar CAC desde el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="eccc5-107">To enable CAC from the Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="eccc5-108">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="eccc5-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="eccc5-109">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="eccc5-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="eccc5-110">En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **global**.</span><span class="sxs-lookup"><span data-stu-id="eccc5-110">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="eccc5-111">En la página **global** , haga clic en la configuración **global** .</span><span class="sxs-lookup"><span data-stu-id="eccc5-111">On the **Global** page, click the **Global** configuration.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="eccc5-112">Solo se puede configurar una red para cualquier implementación de Skype empresarial Server, por lo que nunca habrá más de una configuración de red en la lista.</span><span class="sxs-lookup"><span data-stu-id="eccc5-112">Only one network can be configured for any Skype for Business Server deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="eccc5-113">No puede cambiar el nombre de la configuración global.</span><span class="sxs-lookup"><span data-stu-id="eccc5-113">You cannot rename the Global configuration.</span></span>

5.  <span data-ttu-id="eccc5-114">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="eccc5-114">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="eccc5-115">En la página **Editar configuración global** , active la casilla **Habilitar control de admisión de llamadas** y, a continuación, haga clic en **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="eccc5-115">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="eccc5-116">Al hacer clic en **confirmar**, se ejecuta una prueba de la configuración.</span><span class="sxs-lookup"><span data-stu-id="eccc5-116">When you click **Commit**, you run a test of the configuration.</span></span> <span data-ttu-id="eccc5-117">Se cerrará el cuadro de diálogo **Editar configuración global** y volverá a la página **global** .</span><span class="sxs-lookup"><span data-stu-id="eccc5-117">The **Edit Global Settings** dialog box closes, returning you to the **Global** page.</span></span> <span data-ttu-id="eccc5-118">Recibirá una advertencia si se detectan errores o incoherencias en la configuración de red que le impedirán que funcione correctamente (por ejemplo, si cada región no está conectada a ninguna otra región a través de una ruta interregion).</span><span class="sxs-lookup"><span data-stu-id="eccc5-118">You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="eccc5-119">Si realiza cambios en la configuración de red, puede volver a ejecutar la comprobación de validación abriendo la configuración global y haciendo clic en **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="eccc5-119">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**.</span></span> <span data-ttu-id="eccc5-120">No es necesario deshabilitar CAC en primer lugar: deje la casilla activada y haga clic en **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="eccc5-120">You do not need to disable CAC first: leave the check box checked and click **Commit**.</span></span> <span data-ttu-id="eccc5-121">Puede hacerlo en cualquier momento sin realizar cambios en la configuración.</span><span class="sxs-lookup"><span data-stu-id="eccc5-121">You can do this at any time without making any configuration changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="eccc5-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="eccc5-122">See Also</span></span>

[<span data-ttu-id="eccc5-123">Planificar el servicio de control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="eccc5-123">Plan for call admission control</span></span>](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[<span data-ttu-id="eccc5-124">Implementar el control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="eccc5-124">Deploy call admission control</span></span>](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[<span data-ttu-id="eccc5-125">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="eccc5-125">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[<span data-ttu-id="eccc5-126">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="eccc5-126">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[<span data-ttu-id="eccc5-127">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="eccc5-127">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
